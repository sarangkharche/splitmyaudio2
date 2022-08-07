---
sidebar_label: "Deploy Streamlit with SSL on AWS Lightsail with Docker, Nginx and Letsencrypt"
description: "Deploy Streamlit with SSL on AWS Lightsail with Docker, Nginx and Letsencrypt."
---

# Deploy Streamlit with SSL on AWS Lightsail with Docker, Nginx and Letsencrypt

## Create AWS Lightsail Instance

Use Ubuntu, 20.04

## SSH into instance

.pem is the key generated when creating the Lightsail instance

username is usually ubuntu

`ssh -i "filename.pem" username@publicip`

## Go to namecheap or your domain provider

Add A record in Advanced DNS settings, with value as Lightsail instance public ip and host as somesubdomain for example or `@` for apex domain

## Allow ports for Lightsail instance

For testing, allow All protocols anywhere for an instance

Or use selected like 80, 443

## Install Docker and Docker Compose

[How To Install and Use Docker on Ubuntu 20.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)

[How To Install and Use Docker Compose on Ubuntu 20.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

## SSH git

In `~/.ssh`, generate keys with `ssh-keygen`

Copy the `id_rsa.pub` key and paste into GitHub settings

## Clone your repo

Go to working directory with example `cd ~` and git clone your repo

`git@github.com:androiddevnotes/streamlittraefiklightsail.git`

## Docker Compose

`sudo docker-compose -f production.yml up --build -d`