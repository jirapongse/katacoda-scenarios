# Build the Elektron SDK Docker Image (5 minutes)

In this step, we will build the Elektron SDK Docker image from the [Dockerfile](https://github.com/Refinitiv-API-Samples/Article.EMA.ETA.Docker) available on GitHub.

In short, the script in the Dockerfile will do the following:
- Use Oracle Linux 7 as a base image
- Use the yum command to install the required package to build the Elektron SDK
- Clone the Elektron SDK from GitHub and download cmake
- Run cmake to build the Elektron SDK

Use the following docker build command to build the Elektron SDK Docker image.


`docker build -t elektron-sdk https://github.com/Refinitiv-API-Samples/Article.EMA.ETA.Docker.git`{{execute T1}}

The **-t** parameter is used to tag elektron-sdk as a name of this Docker image.

It may take 20-30 minutes to build the Elektron SDK Docker image. 

After the build was successful, the **docker image** command can be used to 
list all available images on the host machine and the output will show the 
elektron-sdk Docker image.

`docker image ls`{{execute T1}}

```
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
elektron-sdk        latest              2155a4084df2        14 seconds ago      2.142 GB
```
