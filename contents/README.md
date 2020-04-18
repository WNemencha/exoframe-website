---
path: '/'
date: '2020-05-17T10:10:00Z'
title: 'Exoframe'
categories: ['basics']
tags: ['Basics', 'Server', 'Advanced', 'FAQ']
excerpt: ''
---

<img alt="Exoframe" src="https://github.com/exoframejs/exoframe/raw/master/logo/png/exo_white.png" width="300">

> Simple Docker deployment tool

Exoframe is a self-hosted tool that allows simple one-command deployments using Docker.

## Features

- One-command project deployment
- SSH key based auth
- Rolling updates
- Deploy tokens (e.g. to deploy from CI)
- Deploy secrets (e.g. to hide sensitive env vars)
- Automated HTTPS setup via letsencrypt \*
- Automated gzip compression \*
- Rate-limit support \*
- Basic HTTP Auth support \*
- Simple access to the logs of deployments
- Docker-compose support
- Simple function deployments
- Multiple deployment endpoints and multi-user support
- Simple update procedure for client, server and Traefik
- Optional automatic subdomain assignment (i.e. every deployment gets its own subdomain)
- Swarm mode deployments
- Complex recipes support (i.e. deploy complex systems in one command)

\* Feature provided by [Traefik](https://traefik.io/)

## Demo

[![asciicast](https://asciinema.org/a/129255.png)](https://asciinema.org/a/129255)

## Installation and Usage

To run Exoframe you will need two parts - Exoframe CLI and [Exoframe server](https://github.com/exoframejs/exoframe-server).  
For server install instructions see [server installation docs section](docs/ServerInstallation).

To install Exoframe CLI you can either download one of the pre-packaged binaries from [releases page](https://github.com/exoframejs/exoframe/releases) or install it using npm (needs at least Node 8.x):

```
npm install exoframe -g
```

Make sure you have [Exoframe server](https://github.com/exoframejs/exoframe-server) deployed, set it as your endpoint using:

```
exoframe endpoint http://you.server.url
```

Then login using:

```
exoframe login
```

Then you will be able to deploy your projects by simply running:

```
exoframe
```

You can find a list of all commands and options in the [docs](/docs/).

## Docs

- [Basics](/docs/basics)
- [Server Installation](/docs/server-installation)
- [Server Configuration](/docs/server-configuration)
- [Advanced topics](/docs/advanced)
- [Function deployments](/docs/functions)
- [FAQ](/docs/faq)
- [Contribution Guidelines](/docs/contributing)
- [Templates guide](/docs/templates)
- [Recipes guide](/docs/recipes)
- [Using nightly versions](/docs/nightly)
- [Using development and debug versions](/docs/developing)
- [Tutorials, articles, video and related links](/docs/links)

## License

Licensed under MIT.

### Deploy to Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/exoframejs/exoframe-website)
