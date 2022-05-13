<!-- START doctoc.sh generated TOC please keep comment here to allow auto update -->
<!-- DO NOT EDIT THIS SECTION, INSTEAD RE-RUN doctoc.sh TO UPDATE -->
**:book: Table of Contents**

  - [Description](#description)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Credits](#credits)

<!-- END doctoc.sh generated TOC please keep comment here to allow auto update -->
## Description

Fork of [linuxserver / docker-openssh-server](https://github.com/linuxserver/docker-openssh-server) with ability to set up sshd listening port with an environment variable.

## Usage

1. Start docker container, in this example listening on port 443

```
docker run \
  -d \
  --name=openssh-server \
  -e PUID=1000 \
  -e PGID=1000 \
  -e OPENSSH_PORT=443 \
  -e PASSWORD_ACCESS=true \
  -e USER_PASSWORD=password \
  -e USER_NAME=user \
  -p 1234:1234 \
  --restart unless-stopped \
  ghcr.io/jlegido/docker-openssh-server:latest
```

2. SSH to the docker cotnainer on port 443:

```
ssh -p 443 user@localhost
```

## Documentation

Please refer to [linuxserver / docker-openssh-server](https://github.com/linuxserver/docker-openssh-server)

## Credits

* [linuxserver / docker-openssh-server](https://github.com/linuxserver/docker-openssh-server)
* [Added ability to define SSH port from ENV variables](https://github.com/linuxserver/docker-openssh-server/pull/42)
