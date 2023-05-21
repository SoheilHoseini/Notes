1. Create a file with name `Dockerfile` in the root directory of the application
2. According to the application, go to [DockerHub](https://hub.docker.com/) and find the right image suitable for the project and write its name in front of `FROM` in the docker file; So it will be used as the base image.
3. Build the image with `docker build -t imageName .`
4. You can see list of all images on the machine using `docker images` 
5. Now we can run a container of the image using `docker run -it imageName` 
	1. If the image is based on liunx-alpine, we can run the container using `docker run -it imageName sh` in order to have access to the shell prompt and look at the file system  
6. We have the image now and should copy the files and directories of the app into the image.  We can only copy the files in the current directory because when we build the image using `.` in the command, docker client sends contents of the current directory to docker engine and engine will start running the commands in there and doesn't have access to anything outside of the current directory. 
	1. Set the working directory using `WORKDIR /dirName` in the docker file
	2. Copy the files to the desired working directory with `COPY . .` or `ADD . .`
		- In both two ways, the first `.` is the source files and the second one is destination path.   
		- The source could be multiple files and even a list of strings like: ["file name1.txt", "file2.sh"]  
		- For copying URLs and zip files, we should use `ADD`
7. Some unnecessary and heavy files and dirs could be excluded from being copied to the image by mentioning them in a file named `.dockerignore` in the root dir of the app
8. We can run commands needed for the app to run, like `npm install` to install the dependencies of a node project using `RUN yourCommand` in the Dockerfile
9. If the host runs the app on a certain port, we should map the containers ports to the corresponding ports on the host, using `EXPOSE portNum` in Dockerfile
10. For security reasons you can add a user to the container and set its group, so all the other commands will be executed using the user. For that first we should create a user by a command like `RUN adduser -S -G userName userName && addgroup userName` in the Dockerfile and then add the user by `USER userName`
11. `RUN` is used to execute commands in **built time** but we can use `CMD` or `ENTRYPOINT` to run commands at **run time**, when a the container is started. So commands like `npm install` are executed by `RUN` and things like `npm start` would go by `CMD`.
	1. `CMD` is for supplying default command so it's not reasonable to have multiple `CMD`s. In such a case, only the last one will take effect.
	2. Difference between `CMD` and `ENTRYPOINT` is that whatever the default command is in front of `CMD`, we could override it we running the container by `docker run -it imgName myCommand`; But to override the `ENTRYPOINT`, we have to use the `--entrypoint` option so it would be a little bit harder to do so and less flexible.

