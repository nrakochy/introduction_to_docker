##Why does Docker matter? What problems does it answer?

According to the [docs](https://www.docker.com/whatisdocker)(two that are most compelling in my mind):

    Docker containers wrap up a piece of software in a complete filesystem that contains everything it needs to run:
    code, runtime, system tools, system libraries – anything you can install on a server.

    How is this different than VM?
      “Containers have similar resource isolation and allocation benefits as virtual machines
      but a different architectural approach allows them to be much more portable and efficient.”

    Value added:

      1. Eliminate Environment Inconsistencies
      “By packaging up the application with its configs and dependencies together and shipping as a container,
      the application will always work as designed locally, on another machine, in test or production.
      No more worries about having to install the same configs into a different environment.”

      2. Accelerate Developer On-boarding
      “Stop wasting hours trying to setup developer environments, spin up new instances and make copies of production code to run locally.
      With Docker, you can easily take copies of your live environment and run on any new endpoint running Docker.”

##Other benefits

    Multiple containers using the same OS resources- Instead of virtualizing hardware, the run as a user of the LXC.
    Can be used in most DevOps applications: Ansible, Puppet, Chef, etc.

##Overview

##Key Terms

    Images
    Dockerhub

##Demo deploy

##Constraints

    Cannot use multiple OS or kernels
    Security is always a concern for immature trends- Key strength also its weakness: you are talking directly to the kernel, and major kernel sub-systems are not namespaced
        Resources like Red Hat, which provide registry of certified docker formatted container images
        https://opensource.com/business/14/9/security-for-docker


##Quotes:
    [Ben Lloyd Pearson](http://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/)
    “Docker makes it possible to set up local development environments that are exactly like a live server,
    run multiple development environments from the same host that each have unique software, operating systems, and configurations,
    test projects on new or different servers, and allow anyone to work on the same project with the exact same settings, regardless of the local host environment.”


##Sources:

    https://www.docker.com/whatisdocker
    http://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/
    http://www.centurylinklabs.com/what-is-docker-and-when-to-use-it/
    http://www.centurylinklabs.com/setting-up-a-simple-docker-dev-environment/
    http://opensource.com/business/14/7/docker-security-selinux
    https://opensource.com/business/14/9/security-for-docker

