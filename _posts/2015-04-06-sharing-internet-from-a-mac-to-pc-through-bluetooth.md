---
layout: post
title: Sharing internet from a mac to PC through bluetooth
date: 2015-04-06T11:30:03+00:00
author: Chan Le
permalink: /sharing-internet-from-a-mac-to-pc-through-bluetooth/
---
Config the following things for mac:

1. turn on sharing: Open Sharing in System Preferences, choose the source of your Mac internet connection \(Wifi or Ethernet\) as "Share your connection from", then tick Bluetooth PAN in "to computers using"

2. set mac IP: Open Network in System preferences, choose Advance -&gt; set IPV4 to 192.168.101.1 and subnet mask to 255.255.255.0, leave router blank and IPv6 Automatically.

Now on PC:

3. pair pc to mac: on PC, go to Bluetooth Devices -&gt; add a device -&gt; choose the mac -&gt; pair -&gt; next -&gt; done

4. connect: in Bluetooth Devices on PC, right click the mac and choose connect by -&gt; adhoc network

5. do not change IP on pc, leave its setting as default \(automatically assigned from dhcp\)

Done!
