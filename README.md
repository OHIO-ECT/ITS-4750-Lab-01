# Lab 1 - The Toolkit

### Goals

-   Configure Remote Desktop to connect to the lab environment.

-   Learn some basic network connectivity-testing tools and basic equipment configuration

-   Work with Ubuntu Linux Desktop GUI and Terminal/CLI

-   Work with Windows GUI and Terminal/CLI

-   Learn Basic GNS3 Connectivity between objects

### Resources

-   Personal Computer

-   Assigned GNS3 Virtual machine

-   This Lab as a PDF open in an independent reader. (Not embedded in a browser)

## Pre-Lab - Review videos BEFORE attempting the lab!

- Review BEFORE starting the lab
    - [Tech Nugget N0.1 Basic Diagnostic Tools 1]
    - [Tech Nugget N0.2 Basic Diagnostic Tools 2]
    - [Tech Nugget N0.3 Basic Diagnostic Tools 3]
    - [Tech Nugget N0.4 Basic Diagnostic Tools 4]
    - [Tech Nugget N0.5 Basic Diagnostic Tools 5] 
    - [Tech Nugget N11.0 NMCLI]

### Remote Desktop Gateway Connection

Review [Tech Nugget N14.0 RDC Connections] and [Tech Nugget N15.0 RD Gateway] to learn about how to access sessions via RDC. If you are a Mac/OSX user also view [Tech Nugget N17.0 RDC and RD Gateway Apple Mac OSX]. Other OS's are not officially supported, you will need to do some research to figure out what you need.

### Ubuntu GUI

Review [Tech Nugget N25.0 - Ubuntu 20.04 Intro] to get an overview of how the Ubuntu Desktop functions.

### Connect to your GNS3 VM

Each student has been issued their own Linux Ubuntu Desktop Virtual Machine (VM)

1.  Receive the following information from class administrators (Faculty, Lab Manager, Lab Assistant)

    -   GNS3 VM IP address

    -   GNS3 VM Username

    -   GNS3 VM Password

2.  Watch the "Remote Desktop Gateway Connection" pre-lab videos for the complete procedures to connect to the GNS3 VM

    -   RD Gateway IP/Hostname: its-s15.its.ohio.edu

3.  **[Pro Tip]** The GNS3 machine has web access to the outside world. When saving data for lab reports there are several options. The easiest is to use a browser on the GNS3 machine to access web-based email.

4.  **[Data]** Open the file named "README.txt" on the VM's desktop. Email the contents (i.e. copy/paste text content of the file to an email) to your OHIO ID.

5.  **[Data]** It is also possible to copy/paste text data from the child VMs. Copy "Fine Art Indeed" from this document and past it into the README file.

#### **[Pro Tip]** - This is not where you want to start. Read the Lab Report Guidelines at the end of this document.

> "Knowing the destination generally makes a journey shorter" - ECT Ducky

### Connecting objects inside GNS3

6.  Using the network diagram shown below in this document connect all the GNS3 objects together. Review [Tech Nugget N1.1 GNS3] (6:20) for detailed instructions how to connect objects together in GNS3.

7. **[Toolkit]** Please record in a lab notebook that child VMs inside GNS3 use the username itsclass and the password class115#

### Start GNS3 Project

8.  Start all components in the project with the big green triangle.

9.  **[Pro Tip]** All the VMs will start at once. Get comfy as Atlas heaves the world up. The more objects in a project the longer this start up time will take. If you don't know who Atlas is you'll have some time to read [this] while the all the child VMs start.

10. Once all the child VMs have started and are either at a login prompt to a desktop GUI they are ready for use.

11. It is not always necessary (or desired) to start all objects at once. See context menu of each object to start it individually.

### GNS3 Context

After starting up the project each child VM object will open a child window. There should be three child windows inside the GNS3 machine. One is a Ubuntu Linux Server (terminal only), second is Ubuntu Linux Desktop (GUI but there's a terminal option), third is Windows 10 (with two terminal options described below). In a very [Inception]-type way each child VM can have windows of its own in side it's GUI. If this idea gives you a headache you are [doing it correctly]. Much of what we do as IT Professional is virtual. This lab environment is a very good example.

See [ECT Tech Nuggets Playlist] for more detail. As always, if you have questions it's your responsibility to ASK for help! We can't know if you don't understand!

![][1]

Shown above GNS3 and child VMs - GNS3 Window (left), Ubuntu Linux Server (top center), Windows 10 (bottom center), Ubuntu Linux Desktop/GUI (right)

**[Note]** Camera pictures are never permitted in document for lab reports. Screens shots are only acceptable when specifically requested.

### Fixed Width Fonts

**[Pro Tip]** Effective network documentation and reporting generally involves moving data and commands in and out of text-based terminals. These terminals rely on fixed width fonts like Courier New to convey tabular information effectively. Lab reports MUST follow this convention.

### Diagnostic Commands

**[Data]** - For each of the commands that are requested in this section of the lab report, Make sure the response is free from error notations and is like responses that are shown in class and in Tech Nuggets. Save the output of each of the commands for potential use in your lab report.

**[Toolkit]** Many of these diagnostic commands will appear in almost every lab in this class. Detailed notes should be kept handy in a lab notebook.

**[Pro Tip]** Even in this dedicated virtual environment it is easier to take more data that you need as the lab is being performed. In future labs there will be points of data that WILL be difficult to reproduce if not completely lost if it is not take at the requested/appropriate time.

**[Pro Tip]** All of the diagnostic commands that are in use in the labs have quick help that is available on the command line with either a -h or /? flag. Additional information can also be found in Linux man pages or via Internet searches.

### Ethernet Card Diagnostic Information

Each operating system has different ways of naming network cards, which we will refer to in this course as "ethernet card", "interfaces" or "NIC" (network interface card). These interfaces may be a few letters (2-6) that specifies the type of the technology, followed by a number especially when there is more than one of the same types. Examples include lo0 (loopback interface), Linux (Ubuntu) machines typically have interface names like ens160, VyOS uses eth0 and eth1 for the first and second ethernet interfaces. Windows will have "helpful" names like Ethernet Card (1).

12. On the Ubuntu Linux Desktop aka Ubuntu Linux Desktop/GUI

    -   Open a terminal window (AKA CLI) [Icon left on side of screen of the Linux Desktop child VM].

    -   **[Data]** At the prompt in the window that opens type ip a

    -   **[Data]** Also use the nmcli d show command.

13. On the Ubuntu Linux Server aka Ubuntu Linux CLI

    -   Login to Ubuntu Linux Server.

    -   **[Data]** In the Ubuntu Linux Server's terminal use the nmcli d show command.

    **[Pro Tip]** The ip and nmcli commands are in use in many Linux distributions and have an extensive number of flags that both show and configure the computers network stack. Search engines and man pages are necessary resources to fully leverage these tools.

14. On the Windows Desktop

    -   Click on the Start Button and type powershell.exe OR Start Button and type cmd [Windows has several CLI environments... Oh yippy]. In this case, either CLI type will work.

    -   **[Data]** In one of the Windows CLIs enter 
        ````
        ipconfig /all
        ````

**[Pro Tip]** Network Interface data is also available through GUI tools. These methods above are the fastest and most detailed way to get network information about IP settings of each of the machines. This will save you time and give you the data you need to solve problems (in this case the problem is the lab report).

### Ping

Ping is a basic (the MOST basic) tool for figuring out if a machine has network access. The command will, in effect, bounce packets off the destination machine like a sonar.... PING. The command gives a binary answer either YES it sees something or NO it does not.

The best network debugging processes start with pinging another machine that is in the same IP network (more on that idea later).

Most implementations of ping will repeat the ping process several times; others will run continuously until user presses CTRL+C to stop the process.

The format of the ping command is ping `<destination>` in the systems in use in this lab. Where `<destination>` is either a hostname like www.google.com or IP address. i.e. ping ip6echo.net

15. **[Data]** Use the ping command on the specified machine to ping the following locations:

-   132.235.1.1 on Ubuntu Linux Desktop/GUI

-   61.8.0.71 on Windows

-   xkcd.com on the Ubuntu Linux CLI

16. **[Data]** Use the help flag {-h in Linux or /? in windows} to find the properly flag to request 15 ping and then terminate

-   203.178.141.194 on a Ubuntu Linux Desktop/GUI machine

-   www.kame.net on the Windows machine

### Traceroute 

The traceroute command gives more detail about the network BETWEEN the machine and the destination.

**[Pro Tip]** The -n or the -d option suppresses DNS hostname lookups on many commands. Typically, DNS names are not necessary for network diagnostics and consume time and create unwanted network traffic.

**[Pro Tip]** When individual traceroute hit fails lines noted with \* \* \*, which will typically continue until the test has reached 30 hops. Press Ctrl+C to stop it once if you get three or more lines with the \* \* \* notation.

17. In Ubuntu GUI (child VM) access the termina/CLI and issue the command `traceroute -n <destination>` for each of the following destinations. Where `<destination>` is either a hostname like www.google.com or IP address.

    **[Data]** Traceroute to the following destinations on the Ubuntu Linux Desktop/GUI:

-   132.235.8.133

-   www.ford.com

18. In Ubuntu Linux CLI (child VM) access the termina/CLI and issue the command `traceroute -n <destination>` for each of the following destinations. Where `<destination>` is either a hostname like www.google.com or IP address.

    **[Data]** Traceroute to the following destinations on the Ubuntu Linux CLI:

-   132.235.1.1

-   itsohio.net

19. In Windows 10 (child VM) access the termina/CLI. Windows is limited to eight-character old-school commands (long story why) and uses a different switch to suppress DNS lookups. Access the Windows CLI and issue the command: 
    ````
    tracert -d <destination>
    ````
    **[Data]** In Windows, traceroute to the following destinations:

-   132.235.1.1

-   itsohio.net

## Route Table

The route table is part of an Internet Protocol enabled network stack, and includes the directions on where network packets should be sent next on their journey from the source host to the destination. The network diagnostic tools to view that table are critical to all the ITL labs.

The command in Linux is `ip route` and in Windows and in older versions of Linux (not used here) `netstat -rn`

20. **[Data]** Use the respective commands to get the route table from each if the machines

### Name Resolution (DNS) 

Converting Internet names to numbers and numbers to names is the responsibility of the Name Resolution services which use the Domain Name System (DNS) protocols. There are two commands that can access this name system.

> Syntax is: `nslookup <destination>`where `<destination>` is either a hostname like www.google.com or IP address.

21. **[Data]** On Ubuntu Linux CLI use nslookup for each of the following host names:

    -   www.ohio.edu

22. **[Data]** On Ubuntu Linux Desktop/GUI use nslookup for each of the following host names:

-   xkcd.com

-   69.58.0.32

nslookup can also be configured to use the non-default name servers with the correct command line options.
> Syntax used is: `nslookup <Target IP> <DNS Server IP>`

23. **[Data]** On Windows use nslookup and Google's public DNS server (8.8.8.8) as the `<DNS Server IP>` for each of the following host names:

-   132.235.1.1

-   www.cnn.com

-   132.235.9.75

-   98.139.183.24

Dig output returns more information than nslookup giving details of DNS record for that host/IP, but is only available in Linux. 
> Syntax for name to number lookups is: `dig <destination>` where `<destination>` is either a hostname like www.google.com or IP address. To request a number to name conversion you must include the -x option.

24. **[Data]** On Ubuntu Linux Desktop/GUI use dig for each of the following host names:

-   203.178.141.194

-   www.ford.com

-   www.ohio.edu

-   www.google.com

25. **[Data]** On Ubuntu Linux CLI use dig for each of the following host names:

-   132.235.67.1

-   69.58.0.32

-   8.8.8.8

### Wireshark 

Wireshark is a packet capture tool available on Linux, Mac and Windows for free. This means that it will capture traffic (all or some) that comes to or leaves a NIC on the machine. We will be looking at pre-captured data as an example. From Blackboard, download the ITL sample file called "Lab 01 - ITLsample.pcap". See [ECT Tech Nugget N0.5 Basic Diag Tools 5 Wireshark][Tech Nugget N0.5 Basic Diagnostic Tools 5] for more detail about Wireshark.

26. Install Wireshark on **[your]** machine, if you don't have it already (http://www.wireshark.org/download.html). Install the current stable release.

27. Start Wireshark, then open the "Lab 01 - ITLsample.pcap" file using File/Open. Note that you may not get Wireshark to start by double-clicking a capture file.

### Wireshark MAC Address Information

28. In Wireshark the summary lines are the lines of data shown in the top frame of Wireshark. To select a packet, click anywhere on the summary line.

29. Scroll down to packet 58. This machine is trying to match the IP address 132.235.233.254 to the corresponding Ethernet (MAC) address using the ARP protocol. The next packet (59) contains the answer, right on the summary line in the top Wireshark window.

### Wireshark Filtering for DNS Information

30. Look for packets that use the Domain Name System (DNS). Scrolling down the file looking is an option, but it is pretty large. Instead, look for the "Filter" text box near the top of the window, and type the letters dns into the field. The field should turn green showing that this is a valid filter. Click the "Apply" button. To reset the view, use the "Clear" button.

31. In the filtered view, look for a "query" (not a "query response") that has an info field containing:

    `Standard Query 0x0a44 A miles.its.ohiou.edu`

32. In the "View" menu, select "Expand All". Notice that the middle frame expands the packet data to show **[a lot]** of detail.

33. To get packet detail needed into a format where portions of it are can be used in a lab report use File -> Export Packet Display -> As Plain Text...

34. In the dialog window the pops up, pick "Selected packet" in the "Packet Range" section. Under Packet Format, Packet summary line and usually the "As Displayed" option on the right side needed as well.

35. Select a location and name for the file. Pressing Save will create a TEXT output of that file for use in a lab report. The packet text output may need some formatting inside Word.

36. See Wireshark export guide on ITL class Blackboard site for more detail about how to export data for a lab report.

### Create a GitHub account
37. This is a public Github site (which is how you can view it now). However, **all other labs will not be public.** Go create a GitHub account. Use your OHIO email address.

38. Send an email to the course instructors with the new GitHub username. 

39. You will be unable to access any further labs until you create the GitHub account.

**[Toolkit]** Network Diagnostic and Debugging Toolkit - For your LAB NOTEBOOK!

Unless otherwise noted these are entered at a command line (terminal aka console) prompt:

-   `ipconfig /all` - [Windows] Used to display basic network card configuration information on Windows.

-   `ping` - [All] Used to check if a host is reachable across a network or to display the round-trip time for information traveling to or from the host

-   `traceroute` [Linux] or `tracert` [Windows] - Used to display the IP addresses and/or host names of all the routers between your host and another host, including round trip times to each of the intermediate routers. Nearly always use the -d [Windows] or -n option [Linux] to disable DNS resolution.

-   `netstat` [Windwos] or `ss` - [Linux] Used to display the Network status information for your particular host operating system. This can include existing network connections as well as routing information (i.e. how to reach other hosts if more than one network interface exists on the host)

-   `dig` - [All] Used to convert host names to IPv4 addresses or vice-versa. Web version: http://digwebinterface.com

-   `nslookup` - [All] Also used to convert hostnames to IPv4 addresses. A deprecated version of this command still exists in most major operating systems.

### Lab Report Template

40.  Download and review the template MS-Word (.docx) file that is part of this GitHub repo. Use it as a template for how lab reports should be written. It won't answer EVERY question, but it should prove to be a good guide and starting point.

41.  Install DrawIO from https://www.diagrams.net or use the web version. The desktop version is a bit more full featured and does not require a network connection to use.

42.  Download and review the template Diagrams.net AKA DrawIO (.drawio) file that is part of this GitHub repo. Use it as a basic template for diagraming for labs. The template diagram will not have everything in it for every lab (a few labs don't have a Network Diagram). Again, it's a good starting point. 

### Lab Report

Each report is to be written individually. Reports will be uploaded to Blackboard electronically in PDF format (ONLY!). Reports do not generally need to be more than a few (several) pages. Officially, they need to be "long enough to answer the questions". See the report writing guidelines provided on the course Blackboard for more details. Each lab report must have a header (**no cover pages!**) on the first page that includes:

-   Your Name

-   The lab section you attend

-   Your affiliation (CS ugrad, CS grad, ITS ugrad, ITS grad)

### Lab Report Tips

-   For terminal window data (ping, traceroute, netstat etc.) data should be formatted with a fixed width font like courier to preserve the columns and displayed as shown on screen.

-   **[NO SCREEN SHOTS!]** Not with your phone camera or otherwise!

-   Number your answers with the same numbers as the Lab Report Questions.

-   Terminal window data often needs to be reformatted to remove the extra line breaks. While this report is long future ones will be **much** longer. Removing the extra line breaks will save much space. A smaller font can also be used for terminal window data or adjust margins for that data to stop line wrapping.

### Lab Report Questions

1.  Format document - See lab write up guidelines on ITL Blackboard site.

2.  **Show** abbreviated email to yourself from Step 4.

3.  Ethernet Card Data - using `ip a` / `nmcli` outputs **create a table** that correlates output from each of these commands:

    a.  All interface names

    b.  All IP addresses (ignore IPv6 for now)

    c.  All IP address masks (ignore IPv6 for now)

    d.  All IP broadcast addresses (ignore IPv6 for now)

4.  Ping Data - **Show** the command used and the first 3 lines of output for each target, and add the average round trip time for each destination on the next line (copy it from the summary line if ping printed one, or calculate it).

5.  Traceroute Data - **Show** the command used show the output for all destinations. Note that each line of traceroute output is the results from a new set of probe packets (i.e. times are not always getting longer for later lines in the output). **Show** the single **longest** delay among all times for that set of probe packets shown in the output. Display the answer with a table showing command, destinations, and time.

6.  Netstat/IP Route Data - **Show** the IP address of the first hop router (Hint: check traceroute data!). **Show** results for each target into the report, highlight only the host name (or IPs) or names returned for that particular IP address.

7.  Dig/NSLookup data - **Show** results for each target, hightlight only the IPv4 address or addresses returned for that particular hostname. The command line version will return additional names and IP addresses; ignore these for now. Highlight only the host name or names returned for that particular IP address.

8.  Wireshark data - (for help see Lab Writeup Guide and [Tech Nugget N0.5 Wireshark][Tech Nugget N0.5 Basic Diagnostic Tools 5])

    a.  For packet 58, show the MAC address **explain** which part of the address identifies the manufacturer of the card.

    b.  From DNS data **show** entire Wireshark packet output from the packet.

### Network Diagram

![][2]

  [Tech Nugget N14.0 RDC Connections]: https://youtu.be/qv7vglHUObk
  [Tech Nugget N15.0 RD Gateway]: https://www.youtube.com/watch?v=_AfOdcuYesg
  [Tech Nugget N17.0 RDC and RD Gateway Apple Mac OSX]: https://youtu.be/g1oYzEham8c
  [Tech Nugget N25.0 - Ubuntu 20.04 Intro]: https://youtu.be/X4bfK24sbzM
  [Tech Nugget N0.1 Basic Diagnostic Tools 1]: https://youtu.be/_pRXauSnU6U
  [Tech Nugget N0.2 Basic Diagnostic Tools 2]: https://youtu.be/hWeJlNVaUbU
  [Tech Nugget N0.3 Basic Diagnostic Tools 3]: https://youtu.be/PMk53TngTio
  [Tech Nugget N0.4 Basic Diagnostic Tools 4]: https://youtu.be/gD-Tk1Bk7x0
  [Tech Nugget N0.5 Basic Diagnostic Tools 5]: https://youtu.be/QTIbS9wyfag
  [Tech Nugget N11.0 NMCLI]: https://youtu.be/43F51qVz9Ds
  [Tech Nugget N1.1 GNS3]: https://www.youtube.com/watch?v=w5qsM3LhpQI
  [this]: https://greekgodsandgoddesses.net/gods/atlas/
  [Inception]: https://www.imdb.com/title/tt1375666/
  [ECT Tech Nuggets Playlist]: https://www.youtube.com/playlist?list=PLEA5GnkCPRTlvN_eyR99jOSsBCaV6khRS
  [1]: images/lab1-pic1.png 
  [2]: images/lab1-pic2.png
