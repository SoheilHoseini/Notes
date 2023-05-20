1. Go to [DockerHub](https:/hub.docker.com) and search for ubuntu
2. You can either use the `docker pull ubuntu` in CMD in a folder you want to pull the image and then run the container using `docker run ubuntu` 
3. Or you can use `docker run -it ubuntu` to download the image and run the container (interactively) at the same time
4. Now the shell prompt is open which takes our commands and passes them to the os and something is there like `root@847f9ff14cb9:/#` :
	 1. `root` : You have logged in as the root user  
	 2. `847f9ff14cb9` : The Id/name of the running machine  
	 3. `/` : Currently you are at the root directory  
	 4. `#` : You are the root user (otherwise it would be a `$` )  
5. Log in as another user than root:
	1. Open a new terminal  
	 2. Run `docker ps` to get the id of the running container  
	 3. Run `docker exec -it -u username containerID bash`  
 