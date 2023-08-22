# Test bridge

## Prerequisites

Edit your /etc/hosts to add `127.0.0.1  bridge.local`

## Build

```bash
npm build
```

## Generate app service file

```bash
npm run generate -- -u http://bridge.local:9000
```

copy or link generated file to your Synapse config

```bash
ln -s synapse/mx-conf/eimis-registration.yaml eimis-registration.yaml
```

### Edit synapse configuration

```bash
echo "\
app_service_config_files:\n\
  - /mx-conf/eimis-registration.yaml\
" >> synapse/mx-conf/homeserver.yaml
```

## Synapse server

[Start your Synapse instance with docker-compose](./synapse/readme.md)

## Start

```bash
npm run start
```
