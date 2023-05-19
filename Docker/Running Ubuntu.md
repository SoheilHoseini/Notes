1. Go to [DockerHub](https:/hub.docker.com) and search for ubuntu
2. You can either use the `docker pull ubuntu` in CMD in a folder you want to pull the image and then run the container using `docker run ubuntu` 
3. Or you can use `docker run -it ubuntu` to download the image and run the container (interactively) at the same time
4. Now the shell prompt is open which takes our commands and passes them to the os and something is there like `root@847f9ff14cb9:/#` :
 4.1. `root` : You have logged in as the root user
 4.2. `847f9ff14cb9` : The Id/name of the runnig machine
 4.3. `/` : Currently you are at the root directory
 4.4. `#` : You are the root user (otherwise it would be a `$` )
 