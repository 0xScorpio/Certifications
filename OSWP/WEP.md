## WEP Overview

## Exploitation
As always, let's firstly check for available network interfaces:

`` iwconfig ``

Once we pick our network interface (for this example, I'm using wlan0), we have to switch it from 'Managed' to 'Monitor' mode:

``airmon-ng start wlan0``

Most likely, the name of the network interface will change - this is the name we'll use to sniff all nearby wireless networks:

``` airodump-ng wlan0mon ```

Once we pick the Access Point we want to monitor connections for, we grab its BSSID and its frequency channel:

`` airodump-ng --bssid EXAMPLE-BSSID -c EXAMPLE-CHANNEL -w WEP_Capture wlan0mon ``

We can now observe for associations between the AP and various clients. Clients will be stated under the STATION label. The Data label will show the number of Initialization Vectors per 10 second rate, and specifically for the WEP algorithm, it is recommended to capture around 10,000 data packets. 
In my case, I prefer capturing around 30,000 IVs in case of lower connection ratings. On a separate terminal, run an ARP replay attack until we get our specified number of IVs:

`` aireplay-ng -3 -b EXAMPLE-AP-MAC -h EXAMPLE-CLIENT-MAC wlan0mon ``

> [!NOTE]
> -3 is just short-hand for arpreplay within aireplay-ng

Now that we've captured enough data packets, it's time to get cracking! Make sure to add the .cap extension:

``` aircrack-ng WEP_Capture.cap ```
