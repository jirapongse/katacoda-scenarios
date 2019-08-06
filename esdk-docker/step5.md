# Access the shell command prompt to run another example
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

Then, you can run the VAConsumer with the following options.

`./VAConsumer -encryptedSocket amer-1.pricing.streaming.edp.thomsonreuters.com:14002 ELEKTRON_DD mp:/IBM.N -sessionMgnt -uname <username> -passwd <password> -clientId <clientid>`{{copy}}

Please copy the above command to change the username, password, and clientid according to your credential and then paste it back to the terminal.
  
The output of VAConsumer looks like:

```
Connections:
        amer-1.pricing.streaming.edp.thomsonreuters.com:14002 ELEKTRON_DD
                MarketPriceItems: /IBM.N
                MarketByOrderItems:
                MarketByPriceItems:
                YieldCurveItems:
                MarketPriceItems (Private Stream):
                MarketByOrderItems (Private Stream):
                MarketByPriceItems (Private Stream):
                YieldCurveItems (Private Stream):

Adding connection to amer-1.pricing.streaming.edp.thomsonreuters.com:14002...

Connection up! Channel fd=9


Received Login Response
        State: Open/Ok/None - text: "Login accepted by host ads-premium-az1-blue-9-main-prd.use1-az1."

        Authn TT Reissue: 1565076082
        Authn Error Code: 0
        Authn Error Text:

Received Source Directory Response:     State: Open/Ok/None - text: ""

Received serviceName: PERM_SVR_SNKDRV

Received serviceName: ELEKTRON_DD

        Service State: Up


(Channel 9):
/IBM.N
DOMAIN: RSSL_DMT_MARKET_PRICE
State: Open/Ok/None - text: "*All is well"
        PROD_PERM           4017
        RDNDISPLAY          64
        DSPLY_NAME          INTL BUS MACHI/d
        RDN_EXCHID          NYS(2)
        TRDPRC_1            140.760000
        TRDPRC_2            140.740000
        TRDPRC_3            140.810000
        TRDPRC_4            140.930000
        TRDPRC_5            141.020000
        NETCHNG_1           -6.490000
        HIGH_1              144.730000
        LOW_1               139.165000
        PRCTCK_1            �(1)
        CURRENCY            USD(840)
        TRADE_DATE          05 AUG 2019
        TRDTIM_1            20:01:00:000:000:000
        OPEN_PRC            144.720000
        HST_CLOSE           147.250000
        BID                 140.720000
        BID_1               140.720000
        BID_2               140.720000
```


