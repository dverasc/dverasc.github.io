+++
title = "CI/CD with DigitalOcean & Github Actions"
date = "2021-05-26"
description = "Brief look at CI/CD concepts and a practical pipeline for small // prototype projects"

+++

# Introduction
I've been working on a three tier web application with a js front ent (sveltekit) & golang backend (GraphQL) and have containerized both. Early in development, we did manual deployments since it was a small team hacking together a starting prototype. As the product strategy & design developed, we started looking for ways to increase our development speed and practices and a natural point to improve was our deployment process (or lack thereof). With that in mind, I realized we needed to take advantage of the containerized nature of our application and the fact that we already had other projects running on DigitalOcean, so support was not an issue. The rest of this piece will go over the different parts of the CI/CD pipeline but at a highlevel the pipeline is based on Gitbub Actions with scripts to ssh into our DigitalOcean droplet, clean the resources & build a Docker inage, & then run the image, all in an automated fashion after a developer pushes into the main branch.

# CI/CD
CI/CD refers to "Continuous Integration and Continuous Development" which are core concepts behind schools of thoughts and best practices surrouding DevOps, Cloud-Native development, & Agile software development. 

Continuous Integration is 

# DigitalOcean

# GithubActions

# What You Care About

# Conclusion

