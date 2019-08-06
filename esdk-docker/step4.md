# Stop and remove Docker containers
In this step, we will stop the running Docker containers and then remove those Docker containers.

Use `Ctrl+c`to interupt the consumer Docker container on the termial 2.

`clear`{{execute interrupt T2}}

We can use the **docker ps** commmand with the a option to list all containers on the host machine. 

`docker ps -a`{{execute T2}}

The output indicates that the statuses of both provider and consumer containers are up.

```
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS              PORTS     NAMES
6a8e7b28667a        elektron-sdk        "./Consumer -h prov1…"   57 seconds ago       Up 57 seconds     consumer
59f27e67dba7        elektron-sdk        "./Provider -p 14002…"   About a minute ago   Up About a minute     provider
```

To stop containers, you can use the **docker stop** command with the name of the container.

Use the following command to stop the running provider Docker container.

`docker stop provider`{{execute T2}}

Use the following command to stop the running  Docker container. 

`docker stop consumer`{{execute T2}}

Next, we can use the **docker ps** commmand again to verify the statuses of those containers.

`docker ps -a`{{execute T2}}

Now, the statuses of those containers are changed to exited.

```
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                        PORTS              NAMES
6a8e7b28667a        elektron-sdk        "./Consumer -h prov1…"   3 minutes ago       Exited (137) 1 second ago              consumer
59f27e67dba7        elektron-sdk        "./Provider -p 14002…"   3 minutes ago       Exited (137) 14 seconds ago              provider
```

You can restart those containers with the **docker start** command or remove 
those containers with the **docker rm** command. 

To remove the container, run the **docker rm** command with the sanme of the container.

Use the following command to remove the provider container.

`docker rm provider`{{execute T2}}

Use the following command to stop the consumer container. 

`docker rm consumer`{{execute T2}}

After removing, the output from the **docker ps** command indicates that 
those containers are removed.

`docker ps -a`{{execute T2}}


