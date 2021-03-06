---
path: '/docs/server-configuration'
date: '2020-05-17T10:10:00Z'
title: 'Server Configuration'
categories: ['Exoframe']
tags: ['config']
excerpt: 'Exoframe default settings'
---

Exoframe stores its config in `~/.exoframe/server.config.yml`.  
Currently it contains the following settings:

```yaml
# whether debug mode is enabled, default "false"
debug: false

# whether to enable letsencrypt, default "false"
letsencrypt: false

# email used for letsencrypt
letsencryptEmail: your@email.com

# whether to apply gzip compression, default "true"
compress: true

# whether to execute docker prune for images and volumes, default "false"
autoprune: false

# base top-level domain to use for deployments without domains specified, default "false"
# used as postfix, e.g. if you specify ".example.com" (dot is auto-prepended if not present)
# all your deployments will be autodeployed as "deployment-id.example.com"
baseDomain: false

# CORS support; can be "true" ("*" header) or object with "origin" property, default "false"
cors: false

# Traefik image to be used; set to "false" to disable traefik management, default "traefik:latest"
traefikImage: 'traefik:latest'

# Traefik container name, default "exoframe-traefik"
traefikName: 'exoframe-traefik'

# Additional Traefik start args, default []
traefikArgs: []

# Network used by traefik to connect services to, default "exoframe"
exoframeNetwork: 'exoframe'

# server image update channel; can be "stable" or "nightly", default "stable"
updateChannel: 'stable'

# path to folder with authorized_keys, default "~/.ssh"
publicKeysPath: '/path/to/your/public/keys'

# whether Exoframe server would be running in swarm mode, default "false"
swarm: false

# Additional Traefik ports, default: null
traefikPorts:
  - '7788/tcp': 
    - HostPort: '7788'
  - '7788/udp':
    - HostPort: '7788'

# plugins config
plugins:
  # list of plugins that has to be installed and loaded by exoframe-server on startup
  install: ['exoframe-plugin-swarm']
  # specific plugin config (see plugins docs to know what property they use)
  swarm:
    enabled: true
```

_Warning:_ Most changes to config are applied immediately. With exception of Letsencrypt, Additional ports and Plugins config.  
If you are enabling letsencrypt after Traefik instance has been started, you'll need to remove Traefik and then restart Exoframe server for changes to take effect.  
If you are adding plugins after server has been started, you'll need to restart the server so that it can install and load newly added plugins.
