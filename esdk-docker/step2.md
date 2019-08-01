# Run a Provider example (5 minutes)

In this step, we will run a Docker container from the Elektron SDK Docker image. This container will start the Provider example in the Elektron SDK package. The Provider example is listening on TCP 14002 port and provides data for DIRECT_FEED service.

Use the following docker run command to run the Proivder Docker container.

`docker run --name provider -t elektron-sdk ./Provider -p 14002 -s DIRECT_FEED`{{execute T1}}

The command specifies the name of this container to **provider** via the **name** option and use the **t** option to allocate the teletype (TTY) for this container so the output can be seen on the console. The Docker image used to run this container is **elektron-sdk**. It runs the **Provider** example in the Elektron SDK package.

The output after running this command is:

`portNo: 14002
serviceName: DIRECT_FEED
serviceId: 1

Server IPC descriptor = 3 bound on port 14002`