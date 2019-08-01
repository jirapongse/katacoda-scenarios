# Run a Consumer example (5 minutes)

In this step, we will run a new Docker container from the Elektron SDK Docker image in another terminal. 

Use the following command to open a new termial. 

`bash`{{execute T2}}

This container will start the Consumer example in the Elektron SDK package. The Consumer example will connect to the Provider example running in another Docker container on the same Docker host machine.

Use the following docker run command to run the Consumer Docker container.

`docker run --name consumer -t --link provider:prov1 elektron-sdk ./Consumer -h prov1 -p 14002 -s DIRECT_FEED -mp TEST`{{execute T2}}

The command specifies the name of this container to **consumer** via the **name** option and use the **t** option to allocate the teletype (TTY) for this container so the output can be seen on the console. The Docker image used to run this container is **elektron-sdk**. It runs the **Consumer** example in the Elektron SDK package.

The Consumer example uses the **prov1** alias name to connect to the **Provider** container on TCP 14002 port. It subscribes to an item named **TEST** from the **DIRECT_FEED** service.

The output after running this command is:

`
Proxy host:
Proxy port:

Input arguments...

Using Connection Type = 0
srvrHostname: prov1
srvrPortNo: 14002
serviceName: DIRECT_FEED

Attempting to connect to server prov1:14002...

Attempting to connect to server prov1:14002...

Channel IPC descriptor = 3

Channel 3 In Progress...

Channel 3 Is Active
Connected to eta3.1.1.L1.linux.rrg 64-bit Static device.
Ping Timeout = 60

Received Login Response for Username: root
        State: Open/Ok/None - text: "Login accepted by host 38ec020e0900"


Received Source Directory Response
        State: Open/Ok/None - text: "Source Directory Refresh Completed"

Received serviceName: DIRECT_FEED


TEST
DOMAIN: RSSL_DMT_MARKET_PRICE
State: Open/Ok/None - text: "Item Refresh Completed"
        RDNDISPLAY          100
        RDN_EXCHID          SES(155)
        DIVPAYDATE          22 OCT 2010
        TRDPRC_1            1.00
        BID                 0.99
        ASK                 1.03
        ACVOL_1             100000.00
        NETCHNG_1           2.15
        ASK_TIME            09:34:00:000:000:000
`
