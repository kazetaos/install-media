# install-media
Build the Kazeta installation media.

## How to build

The installer is offline, so you first need to build an OS image using the kazetaos/kazeta repository.
Place the built image with extension `img.tar.xz` in `installer/airootfs/root/kazeta-2025-0_545b900.img.tar.xz`, then build the installation media following the instructions below.

There are two methods of building the installation media for Kazeta. Directly from an Arch based system or from a Docker container.

### Arch based systems
On Arch the following packages will need to be installed:
- archiso
- grep
- file
- coreutils
- pikaur

To start building, use the following command:

```bash
./build-iso.sh
```

### Docker
Before being able to build with Docker, the following packages will need to be installed:
- docker.io
- coreutils

To start building, use the following command:

```bash
./build-iso-docker.sh
```

## Files and directories
Here a short explaination of what which files and directories do.

### installer
Contains the modified archiso profile for Kazeta.

### installer/pacman.conf
The pacman configuration during the creation of the installation media. Repositories can be added here.

### installer/packages.x86_64
A list of packages which are installed on the installation media during creation.

### installer/airootfs
Files which are added to the filesystem of the installation media's root file system.

### installer/airootfs/root/customize_airootfs.sh
This script runs in the live enviroment before it is put on the installation media. Allowing configuration changes.

### docker/Dockerfile
This file is the base for the docker container which is used
