#### Image
An image is a collection of everything that an application needs to run. Such as environment variables, application files, third-party libraries and a cut-down OS.

### Container 
Provides an isolated environment for the app, could be stopped and restarted and it is a **process**. We can run multiple containers from a single image in which, each of them has its own write layer and what we write in a container is invisible from other containers. Although we can share data between them. Container is like a lightweight virtual machine.

##### Container Commands
- Run container in background(detached mode) so we could still use the terminal `docker run -d imageName`
- Run a container and giving it a name `docker run -d --name contName imageName`
- List running containers `docker ps`
- Viewing logs of the running container `docker logs contName(ID)`
- By default, there is no mapping between ports of containers and ports of the host. To do so, we use `docker run -d -p hostPort:containerPort --name contName imageName`
- Executing commands in the **running** container: `docker exec yourCommand`
	- Opening shell in the container: `docker exec -it containerName sh`. We can exit the shell by `exit` an the container will not stop running
- Stop a container: `docker stop contName`
- Start a stopped container: `docker start contName` (The `docker run` would start a *new* container but this only restart an existing one)
- To remove a *stopped* container: `docker rm contName` (Or we can use `-f` to force and remove a running one as well)
- Copy files between host and container: `docker cp contName(ID):/srcPathInContainer destPathOntheHost` (we can do reverse by substitution of source and destination paths)
- We can pass output of a docker command to another one as its argument: `docker container rm -f $(docker container ls -aq)` which `a` gives all the containers and `q` would give their id so we give all containers ids to remove them in one go


##### Volumes
Each container has its own file system separate from other containers (even with same base image). So we should not save data in containers file systems since in case of removing the container, the data is lost. For that we have *volumes*.
A volume is a storage outside the container, it could be somewhere on the host or on the cloud.
- Create a volume on the host: `docker volume create volumeName`
- Inspect information of a volume: `docker volume inspect volumeName`
- Associate a volume to a container at run time: `docker run -d -p hostPort:contPort -v volumeName:/APathForTheVolumeInContainerFileSystem imageName`
- To publish changes in the source code for production, we have to build a new image but during development it will be time consuming so we can map the source code directory on the host, as a volume, to the working directory of the container so any changes happening in the source code on the host, the container would see it apply it to the running app: `docker run -d -p hostPort:contPort -v projectPathOnHost:/workingDirInCont imageName`
	- For Linux and Mac instead of `projectPathOnHost` we can use `$(pwd)` and on windows PowerShell can go with `${pwd}`
	