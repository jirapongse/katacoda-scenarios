# Stop and remove Docker containers (5 minutes)


In this step, we will stop the running Docker containers and then remove those Docker containers.

Use the following command to break the Consumer Docker container on termial 2.

`Ctrl+c`{{execute interrupt T2}}

This container will start the Consumer example in the Elektron SDK package. The Consumer example will connect to the Provider example running in another Docker container on the same Docker host machine.

Use the following docker run command to run the Consumer Docker container.

`docker run --name consumer -t --link provider:prov1 elektron-sdk ./Consumer -h prov1 -p 14002 -s DIRECT_FEED -mp TEST`{{execute T2}}

The command specifies the name of this container to **consumer** via the **name** option and use the **t** option to allocate the teletype (TTY) for this container so the output can be seen on the console. The Docker image used to run this container is **elektron-sdk**. It runs the **Consumer** example in the Elektron SDK package.

The Consumer example uses the **prov1** alias name to connect to the **Provider** container on TCP 14002 port. It subscribes to an item named **TEST** from the **DIRECT_FEED** service.

The output after running this command is:
