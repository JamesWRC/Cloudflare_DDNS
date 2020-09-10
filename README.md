# Cloudflare DynDNS for multiple IP addresses
Manage your different servers with dynamic IP addresses. 
Acts as a lightweight manager for A name records for services which are 'distributed' and IP addresses may change frequently. 
<h3 align="center">Cloudflare DynDNS</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)](https://github.com/JamesWRC/Cloudflare_DDNS)
[![GitHub Issues](https://img.shields.io/github/issues/jameswrc/Cloudflare_DDNS.svg)](https://github.com/JamesWRC/Cloudflare_DDNS/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/JamesWRC/Cloudflare_DDNS.svg)](https://github.com/JamesWRC/Cloudflare_DDNS/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md)

</div>

## 📝 Table of Contents

- [Introduction](#introduction)
- [How can this help?](#how_this_can_help)
- [Prerequisites](#prerequisites)
- [Configuration](#configuration)
- [Install](#install)
- [Acknowledgments](#acknowledgments)

## Introduction <a name = "introduction"></a>
This tool has been developed for uses that have many different distributed servers which IP addresses change frequently, primarily developed with dynamic IP addresses in mind.


## How can this help <a name = "how_this_can_help"></a>
I have designed this tool to help manage services with different domain extensions for services that have different IP addresses. 
For example if you have multiple Docker containers running on various servers, different countries or distribute your server infrastructure then this tool will help.

This tool has an in built **queue service** which will enable your services to update their IP addresses, without using up all of your Cloudflare API request limits (1200 per 5 minutes). For example you may limit only 50 IP addresses to be updater per minute (IE this tool will use 250/1200 API calls per 5 minutes.)


## Prerequisites <a name = "prerequisites"></a>
- Cloudflare.
  - any tire will do, even free.
- Docker installed on a server.
  - Can be your origin server, any other server **or even** a raspberry pi.

## Configuration <a name = "configuration"></a>

### Settings / preferences
In the code you will see a basic settings.json.
In this file you will need to provide your:
- Cloudflare API key
- Cloudflare email account
- The Cloudflare Zone ID you wish to use this tool with.

There are additional settings that come default (recommended) configurations. They are as follows:
- ```CF_API_TOKEN``` --> provide your [Cloudflare API key](https://support.cloudflare.com/hc/en-us/articles/200167836-Managing-API-Tokens-and-Keys#12345682). 
- ```CF_EMAIL_ADDRESS``` --> Your Cloudflare accounts email.
- ```CF_ZONE_ID``` --> Your Cloudflare Zone ID.
- ```MAX_UPDATED_PER_MIN``` --> The maximum number of request to update Cloudflare DNS records in one minute.


### Install <a name = "install"></a>
- You will need to first [install docker for your machine / server](https://docs.docker.com/get-docker/)
- Now get the docker image:
```
Docker image is not ready yet, check back later or build image locally
```
- Build the container locally by running:
```sudo chmod +x buildDocker.sh && ./buildDocker.sh```
- Run the docker container:
```docker run cloudflare_ddns```
- Configure to your needs.


## Acknowledgments <a name = "acknowledgments"></a>
* [Cloudflare documentation](https://api.Cloudflare.com/)

## Powered by <a name = "powered_by"></a>

* [Flask](https://flask.palletsprojects.com/en/1.1.x/) - The web framework used
* [Python3](https://www.python.org) - Language used
* [Docker](https://docs.docker.com/get-docker/) - Orchestration
* [Cloudflare](https://www.Cloudflare.com) - Main web proxy service.