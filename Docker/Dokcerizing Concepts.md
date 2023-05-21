#### Tagging Images
By default, all images are tagged as *latest* which is not suitable since if a problem occurs, we can't say what version of the image is the target. So we always have to use tagging.
Tagging could either takes place at building time or after it. (Note: An image can take on multiple tags.)
1. At build time: `docker build -t imageName(imageID):tagName .`
2. After building: `docker image tag imageName(imageID):srcTag imageName(imageID):DestTag` or `docker image tag imageName(imageID):tagName`

**Note**
The *latest* tag does not necessarily points to the latest version of the image and can get out of order so we have to apply it to the latest version explicitly.

#### Removing Images and Containers
To free up space on the machine, we can remove all stopped containers by `docker container prune` and then we can remove all dangling images as well using `docker image prune`
To remove a specific image we can use `docker image rm imageName(imageID)`

#### Pushing Images to DockerHub
First we need to create a repo on [DockerHub](https://hub.docker.com/).
Then we can either use  docker desktop or CMD to push. For CMD:
1. `docker login` and the provide the credentials
2. Set the repo and tag name for the image by `docker image tag imageName(ID) repoName:tagName`
3. Push to dockerhub `docker push repoName:tagName`

#### Saving and Loading Images
We can save images as .tar files to be compressed and then reload and reuse them in the future.
1. save the image in the current dir: `docker image save -o outputFileName.tar imageName:imageTag`
2. load the image from current dir: `docker image load -i outputFileName.tar`