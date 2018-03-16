## Prereqs

1. Copy a public/private keypair into the `DOT-ssh` directory.  It should be one you 
   have registered with GitHub
2. Create file in this repo directory called `github.env` that contains the following:

        GITHUB_USER=<your-github-username>
        GITHUB_KEY=<name-of-private-key-you-copied-into-DOT-ssh>


## Centos7

### Up

If you have not already built the image:

    docker-compose -f docker-compose-centos7.yml up --build -d

If you have already built the image:

    docker-compose -f docker-compose-centos7.yml up -d

### Down

    docker-compose -f docker-compose-centos7.yml down
