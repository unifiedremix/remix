![logo](https://raw.githubusercontent.com/unifiedstreaming/origin/master/unifiedstreaming-logo-black.png)

# Unified Remix

This repository contains a Docker Compose file which can be used to deploy a
Unified Remix demonstration environment.

For more details see [Unifed Remix](http://www.unified-streaming.com/products/unified-remix).

This environment only contains two use cases:

* Pre/Mid/Post roll
* Virtual Subclips

## Flow Diagram

The interaction between the components is depicted in the following diagram:

```
                                                                       rule sets
                                                                     /
 player --> cdn --> unified origin --> unified remix --> smil origin - ad networks
                           |                                         \
                      a/v sources                                      broadcast epg
```


## Setup

1. Install [Docker](http://docker.io)
2. Install [Docker Compose](http://docs.docker.com/compose/install/)
3. Clone this repository

## Usage

You need a license key to use this software. To evaluate you can create an account at [Unified Streaming Registration](https://unified-streaming.com/licenses/access).

The license key is passed to containers using the *USP_LICENSE_KEY* environment variable.

Start the stack using *docker-compose*:

```bash
#!/bin/sh
export USP_LICENSE_KEY=<your_license_key>
docker-compose up
```

You can also choose to run it in background (detached mode):

```bash
#!/bin/sh
export USP_LICENSE_KEY=<your_license_key>
docker-compose up -d
```

Now that the stack is running a demonstration page should be accessible at [http://localhost/](http://localhost/).