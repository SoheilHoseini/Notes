##### Image
An image is a collection of everything that an application needs to run. Such as environment variables, application files, third-party libraries and a cut-down OS.

#### Container 
Provides an isolated environment for the app, could be stopped and restarted and is a process. We can run multiple containers from a single image in which, each of them has its own write layer and what we write in a container is invisible from other containers. Although we can share data between them. 