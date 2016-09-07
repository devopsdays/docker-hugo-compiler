# docker-hugo-compiler

This repository supplies the Docker Hub container located at
https://hub.docker.com/r/devopsdays/docker-hugo-compiler/ . Docker Hub will
automatically update the creation of the Docker image when it detects any
changes made to this repository.

**devopsdays/docker-hugo-compiler** is an installation of Hugo release 0.15
running on Alpine Linux release 3.4.


##devopsdays/docker-hugo-compiler

Docker image that runs the Hugo static web site compiler to generate a static
web site from a Markdown description located in a directory.

Use this Docker container _instead of installing Hugo_ directly on your
computer. This will keep Hugo and its dependencies separate from any
software you have installed.

The file **hugoCompiler** is provided as an example run script to execute
the Hugo compiler within this image. The command to run the compiler from
the root directory of the web site is:

    docker run --rm -e SITE_URL="http://www.mysite.com" -v $(pwd):/site devopsdays/docker-hugo-compiler

The options are:

* **--rm** will remove the Docker container created from the image after the compiler finishes.

* **-e** sets the environment variable ```SITE_URL``` within the container. This is the URL for the website which is included in various ways in the generated web site source code.

* **-v** mounts a data volume in the container. The command will mount the present working directory (```PWD```) to the internal directory ```/site```, which is the workspace defined in the containers.

##Usage

Create a directory in your computer, place a normal Hugo website definition and
run the command (above). The result is that the generated website is placed in
the directory ```../public```.

##Credits
Based upon databliss/docker-hugo-compiler by Randolph Kahle
