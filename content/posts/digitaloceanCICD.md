+++
title = "Digital Ocean & CI/CD"
date = "2022-02-21"
description = "Brief look at CI/CD concepts and a practical pipeline for small // prototype projects"

+++

# Introduction & DevOps

[We've](https://arcvale.com) been working on a three tier web application with a js front ent (sveltekit) & golang backend (GraphQL) and have containerized both. Early in development, we did manual deployments since it was a small team hacking together a starting prototype. As the product strategy & design developed, we started looking for ways to increase our development speed and practices and a natural point to improve was our deployment process (or lack thereof). With that in mind, I realized we needed to take advantage of the containerized nature of our application and the fact that we already had other projects running on DigitalOcean, so support was not an issue. The rest of this piece will go over the different parts of the CI/CD pipeline, but at a high level, the pipeline is based on Gitbub Actions with scripts to ssh into our DigitalOcean droplet, clean the resources & build a Docker inage, & then run the image, all in an automated fashion after a developer pushes into the main branch (look at all those buzzwords).

What is DevOps? Basically, in the giant constellation of cults and schools of thoughts in technology (you know Agile, Scrum, etc), there is a relatively new player called DevOps. This new school is focused on how the people that write the code (dev) and the people who launch // deploy the code work (ops) work together. While this is a somewhat simplistic definition, it's really the main idea. There tends to be a lot of friction and handoffs that happens in teams that are building digital products and since our brains are always trying to OPTIMIZE, DevOps rose to address a lot of that friction. There's a lot that goes into the specific rules and artifacts and etc, but it all starts with an attitude & desire to improve the transition between code to shipping with a focus on automation.

# CI/CD

Okay DevOps makes sense I think...but...then....what is CI/CD?
Glad you asked! One of the core pillars of DevOps is the concept of CI (Continous Integration) & CD (Continous Deployment), hence CI/CD. Here's how it breaks down:

- CI: this is the part of integrating the different branches and versions of code into the "main" branch or whatever is considered the centralized, most up to date, source of truth version of the code. This is typically done by some variation of comitting, pushing, reviwewing and is associated with things like pull & merge requests, Github, Gitlab, and general chaos.

- CD: this is the part of deploying the most up to date version of the code to whatever environment is considered the final stage that end users interact with. This involves testing code and making sure that it will not break or destroy the product that end users are using. There are many variations and best practices on how different teams do this, but all deployment practices consist of automated testing & usually involve some interplay with either on-prem servers or a cloud provider.

When teams integrate CI/CD into their practices, release cycles tend to speed up and overall shipping cadence improves.
CI/CD is one of the pillars behind schools of thoughts and best practices surrouding DevOps, Cloud-Native development, & Agile software development. Different teams have different components, but proper DevOps adoption tends to lead to a CI/CD pipeline, which is the end-to-end system with all the different components that make up its steps to integrate and deploy application code.

# Digital Ocean

For this particular use case, the cloud provider is DigitalOcean. While DigitalOcean isn't one of the big 3 cloud platforms (Google, Azure, or AWS), it offers a better user experience built with developers in mind. They don't offer the full portfolio of services like the big 3, but they have everything anyone needs to build a web application with very solid documentation and ease of use. Basically, they get you what you need for most situations, have transparent pricing, and you won't end up smashing the screen at the UX of it all. I'm a fan and the application this piece is based on is currently running on a Digital Ocean droplet [NOTE: they didn't pay me to say nice things about them, but they should...hit my line DigitalOcean]. 

# Github Actions
GitHub Actions is a feature offered by Github that allows you to create a CI/CD pipeline based on config files, but with a nice user interface that plays well with other Github features like depoyment keys and secrets for information like passwords and user creds. I've worked with Azure DevOps before, and while Actions isn't as comprehensive (not that I blame them for it, I mean its feature vs platform here), I did note a similar interface from a GUI perspective which felt familiar to me.

# The Pipeline

The pipeline starts with a push to a Github repo that contains the code, which then activates the Actions script to run, ssh into our DigitalOcean server, and run several Docker commands that will build and deploy our containerized application.

# The SetUp

A couple components must be set for the scrip to be able to run:

A) You will need to set Github secrets for your ssh server credentials (in this case, Username, Key, and IP)

- Github Secrets are encrypted environment variables that are encrypted before they reach [Github] (https://libsodium.gitbook.io/doc/public-key_cryptography/sealed_boxes). You can set them up by clicking on the Settings tab for the repo that is storing your application code and looking on the left hand menu for the Secrets section.


![image alt text](/secrets.png)



 *You can set up secrets at the repo level*

B) After setting up the secrets, you are going to need to activate Github Actions and add the script from the section below to run the pipeline.

- Similar to secrets, you can configure the actions by finding the Actions tab on the same repo top level menu that has the Settings tab. Once you've landed on the secrets page, you're gonna click 'set up a workflow yourself' in order to create your own actions script (aka the one you'll copy and paste from here).

![image alt text](/actions.png)



 *you're gonna click 'set up a workflow yourself'*


C) Once you've hit set up workflow yourself, Github will take you to a new file being created within your project structure called 'main.yml' (this is the file you'll be editing the script into)

![image alt text](/actionsyml.png)



 *this is the file you'll be editing the script into*




# The Script (what you're here for)

The script below will do the following:

- SSH into your DigitalOcean server using the IP, Username, and Key variables you've stored as environment variables (NOTE: you can use the root user for this but you should NOT..instead create a new user in your server with ssh priviliges and use those creds instead)

- Once in, script will navigate to your project directory and pull for changes

- After updating the code files in the directory, it will clean the current resources, and build the new, latest image

- It will then deploy // run & publish a container based on the most up to date image build


    name: CI

    #Controls when the workflow will run
    on:
    #Triggers the workflow on push or pull request events but only for the master branch
    push:
        branches: [ main ]


    #Allows you to run this workflow manually from the Actions tab
    workflow_dispatch:

    #A workflow run is made up of one or more jobs that can run sequentially or in parallel
    jobs:
    #This workflow contains a single job called "build"
    deploy-to-digital-ocean-droplet:
        # The type of runner that the job will run on
        runs-on: ubuntu-latest
        name: Deploy Application

        # Steps represent a sequence of tasks that will be executed as part of the job
        steps:
        # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
        - name: Checkour repo
            uses: actions/checkout@v2

        # pulls latest
        - name: Pull from GitHub
            uses: appleboy/ssh-action@master
            with:
            host: ${{ secrets.HOST_IP }}
            username: ${{ secrets.HOST_USERNAME }}
            key: ${{ secrets.KEY }}
            script: cd ~/directory && git pull 

        # build docker container
        - name: Docker Build
            uses: appleboy/ssh-action@master
            with:
            host: ${{ secrets.HOST_IP }}
            username: ${{ secrets.HOST_USERNAME }}
            key: ${{ secrets.KEY }}
            script: cd ~/directory && docker rm containername -f && docker build --platform linux/amd64 --no-cache -t appname .
            
        # run docker container
        - name: Docker Build
            uses: appleboy/ssh-action@master
            with:
            host: ${{ secrets.HOST_IP }}
            username: ${{ secrets.HOST_USERNAME }}
            key: ${{ secrets.KEY }}
            script: cd ~/directory && docker run --restart=always --publish 3000:3000 --name=appname -d appname


# Final GUI & Conclusion

After the script is comitted, this should trigger the first run of your pipeline with the following interface allowing you to control the pipeline and find out status and other data points on your runs.

![image alt text](/mainactions.png)



 *Main Actions Screen*

 ![image alt text](/drilldownactions.png)



 *Drill Down into Run*


And that pretty much wraps up the pipeline. This could work on other cloud providers or on-prem since we're essentially just ssh-ing into servers, but the cool thing about [Github Actions](https://github.com/marketplace?category=&query=&type=actions&verification=) is that there are template for all sorts of use cases and platforms for deployments, so there's a good chance that someone has already covered a stack and has posted a config file for it. The important bits here are the general concepts and ideas behind CI/CD and building a practical pipeline for small // prototype projects.