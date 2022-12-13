# Docker Compose Icarus Terminal

This service is a convenient way to deploy an instance of ![Icarus Terminal](https://github.com/iaincollins/icarus) webservice to use with a browser.

Tested on Linux with Steam version of Elite Dangerous Odyssey.

## Introduction and Setup

The container setup uses rootless-node base image.

The ED-logdir defaults to `$HOME/.steam/steam/steamapps/compatdata/359320/pfx/drive_c/users/steamuser/Saved Games/Frontier Developments/Elite Dangerous/`. 

You can edit this path via the .env file, but please only change the `MOUNT_DIR` variable, as the `LOG_DIR` variable refers to the internal container path and should not be changed.

This should theoretically work with windows, if you adapt to the correct Saved Games path.

### Installation ###

A "recent" version of docker and docker-compose is needed to build this.

```bash
git clone https://github.com/helpsterTee/ed-icarus-docker
cd ed-icarus-docker
docker compose --profile icarus_service up --build
```

You can now point your browser to `http://localhost:3300` to access the Icarus Terminal.

After building the image, you can exit with `CTRL-C`. If you need to start the service later on again, use 

`docker start icarus_docker-icarus_service-1` 

or the respective container id, you may discover by 

`docker ps -a`

### Issues ###

Sadly, I can't support your local docker installation, so you should get that up running first, here are some great starter points: 

![https://docs.docker.com/get-started/](https://docs.docker.com/get-started/)

This docker compose setup shouldn't have much issues, but you can ask via GitHub issues. Be sure to include some logging that describes the problem.

### License and Credits ###

Original license by Icarus Terminal still applies, see it ![here](https://github.com/iaincollins/icarus/blob/main/LICENSE)

For all files in this repository, see LICENSE file.

Credits for Icarus Terminal goes to ![@iaincollins](https://github.com/iaincollins) and their supporters. Thanks :)
