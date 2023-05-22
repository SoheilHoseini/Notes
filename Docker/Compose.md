When we are dealing with multiple container applications, we have docker files specific for each of them with their specific instructions. To build images out of the docker files and run the containers, we can create a `.yml` fill called `docker-compose.yml` which contains necessary instructions to run containers. There is an example below:

![docker compose sample](docker-compose-sample.png)

- `version`: determines the compose file version compatible with the docker engine we're using which could be checked [here](https://docs.docker.com/compose/compose-file/compose-versioning/)
- `services`: declares services (images) we want to build. we have three services here `frontend`, `backend` and `db` (These names are arbitrary)
	- `build`: path to docker file of each image
	- `ports`: port mapping between host and container. It is in form of a list so we can declare multiple mappings
	- `environment`: declare environmental variables like `DB_URL` for database connection address string
	- `command`: Although there are commands in `CMD` of the backend container docker file, for migrating our database we need to override them and execute another commands. To do so, we can saved them in a shell file called `docker-entrypoint.sh` and gave it as a value to `command` so it executes them all 
	- `image`: when we want to pull the image from DockerHub, we use this field to determine  the version we're looking for
	- `volumes`: we have to declare a volume to save the database on the host so the data is not lost. But we have to define the volumes outside the services part
	
- `volumes`: define the volumes we want to use. As seen in the picture, we only write the name of it with no value in front of the name

**Note**
To detect changes of the source code in the container, we can use the volume mapping (mentioned [here]([[Images and Containers#Volumes]])) but if we have just run the docker compose, services dependencies has to be installed on the host so the containers can run properly. 



#### Compose Commands
Since the docker compose file is built on docker engine so all the commands using `docker` are also available in `docker-compose` but this time they are targeting the whole application and all containers. For example we can force rebuild all the images with no caching using `docker-compose build --no-cache`

- Running the app and building images if necessary: `docker-compose up -d` in the background (detached mode)
- Stopping the app and removing containers: `docker compose down`
