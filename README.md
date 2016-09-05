# docker-hugo-compiler

This repository builds a Docker image to be used as a single transformation
of a web site definition into a static web site.

This is useful as the final preparation of a web site before uploading to 
production servers.

    docker run --rm -e SITE_URL="http://www.mysite.com" -v $(pwd):/site databliss/docker-hugo-compiler

The SITE_URL environment variable sets the target website base URL for all content generation.

The volume mapping of $(pwd):/site maps the current directory of the host computer
to the /site directory inside the container. 

Hugo is configured to work in that directory.

The --rm option removes the container after the transformation is complete.
