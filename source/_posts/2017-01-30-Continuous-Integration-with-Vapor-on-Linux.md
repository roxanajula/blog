---
title: Continuous Integration With Vapor on Linux (Using GitLab CI)
date: 2017-01-30 10:00:00
tags: vapor, ci, linux, gitlab, 
authorIds: 
- josc
categories:
- Operations
---

As many others, we are struggling with lacking Swift features on Linux. And we have tried to find the best way to test our code runs on Linux before deploying our code.

We are already using a Gitlab server internally, and found their CI tool to be what we needed. This guide will show you how to setup an automated test on your own computer on Linux everytime you push your code to gitlab.com

## About GitLab / gitlab.com

GitLab is a widely used free Git service. It provides a lot of the features github does, but provides either self-hosted or gitlab.com with free private repositories.

Their CI tool is really easy to setup, as you can see in this guide.

## Requirements

- First of all you need an account on gitlab.com [Signup now](https://gitlab.com/users/sign_in#register_pane)

- A private repository on gitlab.com - Just create your project(s)

- A GitLab Runner

## Setup a GitLab Runner

You can basically setup your runner everywhere you want e.g.:
* In a Docker container
* In a Vagrant machine
* On Digital Ocean
* On AWS (e.g. on their free-tier)

You basically just need a Linux machine :-)

### Install GitLab runner software

(Our guide will use Ubuntu 16.04)

Setup the GitLab runner repository:

```
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-ci-multi-runner/script.deb.sh | sudo bash
```

Install the runner on your machine

```
sudo apt-get install gitlab-ci-multi-runner
```

Setup the runner (This part will ask you some questions)

```
sudo gitlab-ci-multi-runner register
```
