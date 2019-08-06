# Stop and remove Docker containers (5 minutes)

In this step, we will stop the running Docker containers and then remove those Docker containers.

Use `Ctrl+c`to interupt the consumer Docker container on the termial 2.

`clear`{{execute interrupt T2}}

We can use the **docker ps** commmand with the a option to list all containers on the host machine. 

`docker ps -a`{{execute T2}}

The output indicates that the statuses of both provider and consumer containers are up.


To stop containers, you can use the **docker stop** command with the name of the container.

Use the following command to stop the running provider Docker container.

`docker stop provider`{{execute T2}}

Use the following command to stop the running  Docker container. 

`docker stop consumer`{{execute T2}}

Next, we can use the **docker ps** commmand again to verify the statuses of those containers.

`docker ps -a`{{execute T2}}

Now, the statuses of those containers are changed to exited.

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

