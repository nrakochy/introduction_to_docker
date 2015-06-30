##Why does Docker matter? What problems does it answer?
According to the [docs](https://www.docker.com/whatisdocker):

    Docker containers wrap up a piece of software in a complete filesystem that contains everything it needs to run:
    code, runtime, system tools, system libraries – anything you can install on a server.

How is this different than VM?

      “Containers have similar resource isolation and allocation benefits as virtual machines
      but a different architectural approach allows them to be much more portable and efficient.”

###Value added:
According to the [docs](https://www.docker.com/whatisdocker)(two most compelling in my mind):

      1. Eliminate Environment Inconsistencies
      “By packaging up the application with its configs and dependencies together and shipping as a container,
      the application will always work as designed locally, on another machine, in test or production.
      No more worries about having to install the same configs into a different environment.”

      2. Accelerate Developer On-boarding
      “Stop wasting hours trying to setup developer environments, spin up new instances and make copies of production code to run locally.
      With Docker, you can easily take copies of your live environment and run on any new endpoint running Docker.”

###Other benefits
Not from the docs

    Multiple containers using the same OS resources- Instead of virtualizing hardware, the run as a user of the LXC.
    Can be used in most DevOps applications: Ansible, Puppet, Chef, etc.

##Overview

###Key Terms

    Dockerfile
    Images
    Dockerhub

###Demo

###Constraints

* Cannot use multiple OS or kernels
* Security is always a concern for immature tech 
    * Key strength also its weakness: you are talking directly to the kernel, and major kernel sub-systems are not  
    * Resources like [Red Hat](https://opensource.com/business/14/9/security-for-docker), which provide registry of certified docker formatted container images
    * Docker also released [Docker Trusted Registry](https://blog.docker.com/2015/06/docker-ready-for-production/)

### Open Containers Project
[Open Containers Project under the auspices of the Linux Foundation](http://www.opencontainers.org/)
* Container standardization

    "Participants include, basically, everyone from A to V in the tech industry.
    This is 20+ organizations including Apcera, AWS, Cisco, CoreOS, Docker, EMC,
    Fujitsu Limited, Google, Goldman Sachs, HP, Huawei, IBM, Intel, Joyent, Pivotal,
    the Linux Foundation, Mesosphere, Microsoft, Rancher Labs, Red Hat, and VMware."

[Source](https://blog.docker.com/2015/06/open-container-project-foundation/)


###Quotes:
[Ben Lloyd Pearson](http://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/)
    “Docker makes it possible to set up local development environments that are exactly like a live server,
    run multiple development environments from the same host that each have unique software, operating systems, and configurations,
    test projects on new or different servers, and allow anyone to work on the same project with the exact same settings, regardless of the local host environment.”


##Sources:

    https://www.docker.com/whatisdocker
    https://blog.docker.com/
    http://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/
    http://www.centurylinklabs.com/what-is-docker-and-when-to-use-it/
    http://www.centurylinklabs.com/setting-up-a-simple-docker-dev-environment/
    http://opensource.com/business/14/7/docker-security-selinux
    https://opensource.com/business/14/9/security-for-docker

