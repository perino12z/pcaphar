# Introduction #

Many web traffic analysis tools exist for modern desktop browsers -- IE, Firefox, Chrome. There is none such tool exists for mobile browsers, such as Safari on iPhone, or browser of Andriod. What we can do is to set up an private WiFi network, connect the mobile device to the network, capture the traffics, and then analyze the traffics.



# Setup WiFi hotspot #
## Apple MacBook ##
  1. click the wireless icon in the MacBook menu bar
    * enter a name for the network - “hot1” in this example
  1. open System Preferences -> Sharing on the MacBook
    * select Internet Sharing on the LHS
    * choose “Ethernet” for “Share your connection from”
    * choose “AirPort” for “To computers using”
    * click “AirPort Options”
      1. type a name for your network (“hot1” again)
      1. do NOT enable encryption
      1. click OK
    * check the Internet Sharing checkbox
    * click Start when asked “Are you sure you want to turn on Internet sharing?”

## Window 7 Laptop ##

This setup may also applies to Windows XP or Vista, but I have not tried with them.
If anyone have experience on those or other machines, please provide a comment below.
So that we will update this info.

  1. Open Control Panel -> Network and Internet -> Network and Sharing Center
  1. select the link for "Set up a new connection or network"
  1. select "set up a wireless ad hoc (computer-to-computer) network"
  1. Next, give the network a name (hot1, for example), and check "Save this network"
  1. Go back to "Network and Sharing Center", click the "Change adapter settings" link on the left
  1. Find you LAN, right click and open the properties -> Sharing tab
  1. Enable sharing.


The WiFi hotspot should be available.

# Start capturing TCP traffic #

## Tcpdump ##
  1. open a terminal on the Mac
  1. Run this command. Specify any filename you want as “yourfilename.pcap”.
```
  sudo tcpdump -i en1 -n -s 0 -w yourfilename.pcap tcp or port 53
```

Leave tcpdump running. Cotrol-C to terminate tcpdump when finish capturing.

## WireShark ##

Alternatively, we can use WireShark to capture packets.
  1. Open WireShark
  1. Menu Capture->Options
  1. In the options dialog, select your wireless interface, and click on "Capture Filter"
  1. In the "Capture Filter" dialog, create a new filter (if you have not already), with name "TCP and UDP port 53 (DNS)", and filter string as "tcp or udp port 53"
  1. Select the filter, close the dialog.
  1. Click "Start" button in the "Capture Options" dialog to start capturing.
  1. Save the capture when finished.


# Connect mobile device to hotspot #

On your mobile device connect to the WiFi hotspot specified above (“hot1” in our example).
Now, any websites you visit on your mobile device should be captured by tcpdump.

# Clear the browser cache #

  1. iPhone
> Settings -> Safari:
> > look for "Clear History", "Clear Cookie", and "Clear Cache"

  1. Android

> Open Broswer -> Memu -> More -> Settings:
> > look for "Clear cache", " Clear history", and "Clear all cookie data".