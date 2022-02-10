+++
title = "DockerFile for SvelteKit Application"
date = "2022-01-28"
description = "Containerize a SvelteKit app (node) "

+++

# DockerFile for SvelteKit

Are you working with SvelteKit and ready to deploy? Having issues with containerizing your application for said deployment? Well, look no further, here’s a Dockerfile that works for SvelteKit apps that I’ve used on Digital Ocean, GCP, and AWS


    FROM node:14-alpine as builder
    WORKDIR /app
    COPY package.json package-lock.json ./
    RUN npm install
    COPY . .
    RUN npm run build
    
    FROM node:14-alpine
    
    USER node:node
    
    WORKDIR /app
    COPY — from=builder — chown=node:node /app/build ./build
    COPY — from=builder — chown=node:node /app/node_modules ./node_modules
    COPY — chown=node:node package.json .
    ENV PORT 3000
    EXPOSE 3000
    CMD [“node”,”build”]



# Building & Running

**sudo docker build — no-cache -t nameofthing .**

or

**sudo docker build — platform linux/amd64 — no-cache -t nameofthing .**

I included the platform in the second build command because I started using an M1 laptop and ran into issues when building images and then pushing those images to third party cloud platforms like AWS.

Run

**sudo docker run — restart=always — publish 3000:3000 — name=nameofthing -d nameofthing**