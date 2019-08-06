# Access the shell command prompt to run another example (5 minutes)

In this step, we will run a new Elektron-SDK Docker container to access the shell command prompt and run another example.

The example used in this step is **VAConsumer**. We will run this example to connect to EDP-RT (Elektron Data Platform - Real Time) in Cloud. 

To run this example, you need to have the following information.

1. **Username** to connect to Elektron Data Platform (It could be a machine ID or email account)
2. **Password** for the above username
3. **ClientID** which is a unique ID defined for an application making the request (If the Username is a machine ID, the ClientID could be the same machine ID)

First, we run the elektron-sdk image without any arguments to access the shell command prompt.

`docker run -it --name esdk elektron-sdk`{{execute T2}}

The **i** option is used to keep the standard input open for this container and the **t** option is used to allocate a pseudo-TTY for this container. The name of this container is **esdk** specified with the **name** option.

After running this command, you can access shell in the container.

Next, the EDP-RT in Cloud connectivity example has a dependency on the Libcurl library. Therefore, we run the following command to add the location of Libcurl library to the LD_LIBRARY_PATH environment variable.

`export LD_LIBRARY_PATH=/opt/refinitiv/Elektron-SDK/esdk/install/lib64`{{execute T2}}

Then, run the VAConsumer with the following options.

`VAConsumer -encryptedSocket amer-1.pricing.streaming.edp.thomsonreuters.com:14002 ELEKTRON_DD mp:/IBM.N -sessionMgnt -uname <username> -passwd <password> -clientId <clientid>`{{execute T2}}

Please change <username>, <password>, and <clientid> according to your credential.
  
The output of VAConsumer looks like:


