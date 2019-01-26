# Docker setup

Alternatively, if you don't want to spend the time to meticulously read through & follow these instructions to set up your computer, worry about versioning conflicts, you can use Docker to obtain mini-environments that are based on the instructions here. 

### Intro to Docker
[Here](https://towardsdatascience.com/learn-enough-docker-to-be-useful-b7ba70caeb4b) and [here](https://towardsdatascience.com/docker-for-data-science-4901f35d7cf9) are good intros.  If you like video, [here's a youtube intro](https://www.youtube.com/watch?time_continue=25&v=oO8n3y23b6M).

TL;DR - Docker Images are blueprints to build a Docker container - "An image contains the Dockerfile, libraries, and code your application needs to run, all bundled together."  A Container is the actualization of an Image - it's the created running enviromnent you use.

1. [Install Docker Desktop](https://docs.docker.com/install/) 
2. Optional: Install Kitematic (GUI for Docker) [macOS](https://download.docker.com/kitematic/Kitematic-Mac.zip)/[Windows](https://download.docker.com/kitematic/Kitematic-Windows.zip) (or, if you don't trust those links, install Docker Desktop and look for a link to Kitematic from the Desktop app).
3. Make sure you've installed it - in terminal, run:
   * `docker --version`
4. We *could* create docker images from scratch, but fortunately there's a pretty large community we can use as a base:

### R Docker Image
See also: [https://ropenscilabs.github.io/r-docker-tutorial/](https://ropenscilabs.github.io/r-docker-tutorial/)
We'll use the [tidyverse image from rocker](https://hub.docker.com/r/rocker/tidyverse) as a base.  This contains the tidyverse packages and a few others (like devtools).  If we are working on a project that requires glmnet (or whatever other package(s)), we'd have to install glmnet every time we create an instance of the tidyverse package.  Alternatively, we could build a new package that lists glmnet in the source.

1. Create a Dockerfile that initializes based on the rocker/tidyverse image and adds the R libraries we need
  ```
  # Create image on back of rocker/tidyverse using R version 3.5.2
  FROM rocker/tidyverse:3.5.2

  LABEL MAINTAINER="Alex Graber <ahgraber@gmail.com>"

  # Install any needed packages specified
  RUN install2.r --error \
  janitor data.table
  ```
2. In the terminal, navigate to the location where you saved the dockerfile. Run:
  ```
  docker build --tag=<image_name> .
  ```
  where the <image_name> is your name for the image, and the . implies the source files are in the current directory
3. After it builds (hopefully successfully), you can view the image in your list by running
  ```
  docker image ls
  ```
  and instantialize the image to create a container by running
  ```
  docker run -e PASSWORD=<new_password> -p 8787:8787 <image_name>
  ```
  where the <new_password> is your new password to access RStudio server and <image_name> is what you named the image
4. To use the container, open http://localhost:8787 in your browser and log in with username: rstudio password:<new_password>
5. If you need to get files back and forth to RStudio, you can mount a local volume to the docker image:
  ```
  docker run -v /host/directory:/container/directory -e PASSWORD=<new_password> -p 8787:8787 <image_name>
  ```
6. Bonus optional: if you will use this docker image frequently, create an alias for it in .bash_profile!
