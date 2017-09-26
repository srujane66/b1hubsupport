---
layout: post
postid: '01200'
catid: '00300'
categories: hub
title: When IP address of Phillips Hue Bridge is changed, can I still control Phillips Hue devices?
---

When the IP address of the bridge is changed:

**Accessing from local network**:
The **IP** changes are handled successfully in the back-end. The Hue devices respond to the commands without any ambiguity.

**Accessing from cloud**:
In this case, the Hue bulbs stop responding to the commands. To overcome this issue, set a static IP to the router. The configuration process changes from router to router.

For example:

**Setting a static IP in NETGEAR**

1. Launch an Internet browser and type [http://www.routerlogin.net](http://www.routerlogin.net) into the address bar.

2. Enter the router username and password when prompted. The default username is admin. The default password is password.

3. Under the BASIC tab, click Internet. The Internet Setup screen displays.

![Static IP 1.PNG]({{ site.img }}/Static%20IP%201.PNG)

Under the Internet IP Address menu, select Use Static IP Address.

**Address.**

4. Enter the static IP address, IP Subnet Mask, and Gateway IP Address provided by your ISP.

5. Under the Domain Name Server (DNS) Address menu, select Use These DNS Servers.

6. Enter the **Primary DNS** and **Secondary DNS** provided by your ISP.

7. Click **Apply** to save the settings.

8. To verify your changes, click on **ADVANCED** and view the **Internet Port** information.

![Static IP 2.PNG]({{ site.img }}/Static%20IP%202.PNG)

**Setting a static IP in TP-LINK:**

1. Open the web browser and type the IP address of the device in the address bar (default is 192.168.1.1).

2. Press Enter. Type the username and password in the login page, the default username and password both are admin.

3. Click OK to login the web page.

4. Click on Advanced Setup-&gt;Routing, and you will see the routing information in the next screen.

Click **ADD ROUTE** button to add a new route and then **save**.