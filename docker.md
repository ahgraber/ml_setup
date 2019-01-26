# Docker setup

Alternatively, if you don't want to spend the time to meticulously read through & follow these instructions to set up your computer, worry about versioning conflicts, you can use Docker to obtain mini-environments that are based on the instructions here. 

### Intro to Docker
[Here](https://towardsdatascience.com/learn-enough-docker-to-be-useful-b7ba70caeb4b) and [here](https://towardsdatascience.com/docker-for-data-science-4901f35d7cf9) are good intros.  If you like video, [here's a youtube intro](https://www.youtube.com/watch?time_continue=25&v=oO8n3y23b6M).

TL;DR - Docker Images are blueprints to build a Docker container - "An image contains the Dockerfile, libraries, and code your application needs to run, all bundled together."  A Container is the actualization of an Image - it's the created running enviromnent you use.

1. [Install Docker Desktop](https://docs.docker.com/install/) 
2. Optional: Install Kitematic (GUI for Docker) [macOS](https://download.docker.com/kitematic/Kitematic-Mac.zip)/[Windows](https://download.docker.com/kitematic/Kitematic-Windows.zip) (or, if you don't trust those links, install Docker Desktop and look for a link to Kitematic from the Desktop app).
3. Make sure you've installed it - in terminal, run:
   * `docker --version`
   * `docker run hello-world`
   
