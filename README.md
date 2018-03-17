## Prereqs

1. Copy a public/private keypair into the `DOT-ssh` directory.  It should be one you 
   have registered with GitHub
2. Create file in this repo directory called `github.env` that contains the following:

        GITHUB_USER=<your-github-username>
        GITHUB_KEY=<name-of-private-key-you-copied-into-DOT-ssh>

### Docker for Windows Notes

This note is for users running on Windows 10 and driving this from WSL
(Windows Subsystem for Linux) but using the Docker for Windows
engine.  In this case you will be accessing this repo from 
a (WSL) Linux terminal and it will be via a path that looks
something like this: /mnt/c/.....

That confuses the Docker for Windows engine and makes it so that
your bind mount will not work. In that case, please set the
REPO_DIR environment variable to look like this:
/c/...

Example:

    If your $PWD looks like this:
      /mnt/c/Users/Bob/Projects/docker-zcs-build-machines
    Then you would set the following value to:
      /c/Users/Bob/Projects/docker-zcs-build-machines

The easiest way to "set it and forget it" is to create a file
called `.env` in this repo directory and have a single
line that looks like this (adjusted for your situation,
obviously, with no trailing slash).

REPO_DIR=/c/Users/.../docker-zcs-build-machines

## Centos7

### Up

If you have not already built the image:

    docker-compose -f docker-compose-centos7.yml up --build -d

If you have already built the image:

    docker-compose -f docker-compose-centos7.yml up -d

### Down

    docker-compose -f docker-compose-centos7.yml down

## Ubuntu 16

### Up

If you have not already built the image:

    docker-compose -f docker-compose-ubuntu16.yml up --build -d

If you have already built the image:

    docker-compose -f docker-compose-ubuntu16.yml up -d

### Down

    docker-compose -f docker-compose-ubuntu16.yml down

