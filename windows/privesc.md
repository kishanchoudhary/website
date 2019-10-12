
  
Initially we will want to quickly gather some essential information so we can get a lay of the land and asses our situation.  
  
First let's find out what OS we are connected to:
```
C:\Windows\system32> systeminfo | findstr /B /C:"OS Name" /C:"OS Version"
OS Name:                   Microsoft Windows 7 Professional
OS Version:                6.1.7601 Service Pack 1 Build 7601
```
  

Next we will see what the hostname is of the box and what user we are connected as.

```
C:\Windows\system32> hostname
victim
```
```
C:\Windows\system32> echo %username%
user1
```
  

Now we have this basic information we list the other user accounts on the box and view our own user's information in a bit more detail. We can already see that user1 is not part of the localgroup Administrators.

```
C:\Windows\system32> net users

User accounts for \\B33F

-------------------------------------------------------------------------------
Administrator            b33f                     Guest
user1
The command completed successfully.

C:\Windows\system32> net user user1

User name                    user1
Full Name
Comment
User's comment
Country code                 000 (System Default)
Account active               Yes
Account expires              Never

Password last set            1/11/2014 7:47:14 PM
Password expires             Never
Password changeable          1/11/2014 7:47:14 PM
Password required            Yes
User may change password     Yes

Workstations allowed         All
Logon script
User profile
Home directory
Last logon                   1/11/2014 8:05:09 PM

Logon hours allowed          All

Local Group Memberships      *Users
Global Group memberships     *None
The command completed successfully.

```  

That is all we need to know about users and permissions for the moment. Next on our list is networking, what is the machine connected to and what rules does it impose on those connections.  
  
First let's have a look at the available network interfaces and routing table.
```
C:\Windows\system32> ipconfig /all

Windows IP Configuration

   Host Name . . . . . . . . . . . . : b33f
   Primary Dns Suffix  . . . . . . . :
   Node Type . . . . . . . . . . . . : Hybrid
   IP Routing Enabled. . . . . . . . : No
   WINS Proxy Enabled. . . . . . . . : No

Ethernet adapter Bluetooth Network Connection:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
   Description . . . . . . . . . . . : Bluetooth Device (Personal Area Network)
   Physical Address. . . . . . . . . : 0C-84-DC-62-60-29
   DHCP Enabled. . . . . . . . . . . : Yes
   Autoconfiguration Enabled . . . . : Yes
   
Ethernet adapter Local Area Connection:

   Connection-specific DNS Suffix  . :
   Description . . . . . . . . . . . : Intel(R) PRO/1000 MT Network Connection
   Physical Address. . . . . . . . . : 00-0C-29-56-79-35
   DHCP Enabled. . . . . . . . . . . : Yes
   Autoconfiguration Enabled . . . . : Yes
   Link-local IPv6 Address . . . . . : fe80::5cd4:9caf:61c0:ba6e%11(Preferred)
   IPv4 Address. . . . . . . . . . . : 192.168.0.104(Preferred)
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Lease Obtained. . . . . . . . . . : Saturday, January 11, 2014 3:53:55 PM
   Lease Expires . . . . . . . . . . : Sunday, January 12, 2014 3:53:55 PM
   Default Gateway . . . . . . . . . : 192.168.0.1
   DHCP Server . . . . . . . . . . . : 192.168.0.1
   DHCPv6 IAID . . . . . . . . . . . : 234884137
   DHCPv6 Client DUID. . . . . . . . : 00-01-00-01-18-14-24-1D-00-0C-29-56-79-35
   DNS Servers . . . . . . . . . . . : 192.168.0.1
   NetBIOS over Tcpip. . . . . . . . : Enabled

C:\Windows\system32> route print

===========================================================================
Interface List
 18...0c 84 dc 62 60 29 ......Bluetooth Device (Personal Area Network)
 13...00 ff 0c 0d 4f ed ......TAP-Windows Adapter V9
 11...00 0c 29 56 79 35 ......Intel(R) PRO/1000 MT Network Connection
  1...........................Software Loopback Interface 1
 16...00 00 00 00 00 00 00 e0 Microsoft ISATAP Adapter
 15...00 00 00 00 00 00 00 e0 Microsoft ISATAP Adapter #2
 19...00 00 00 00 00 00 00 e0 Microsoft ISATAP Adapter #3
 14...00 00 00 00 00 00 00 e0 Teredo Tunneling Pseudo-Interface
===========================================================================

IPv4 Route Table
===========================================================================
Active Routes:
Network Destination        Netmask          Gateway       Interface  Metric
          0.0.0.0          0.0.0.0      192.168.0.1    192.168.0.104     10
        127.0.0.0        255.0.0.0         On-link         127.0.0.1    306
        127.0.0.1  255.255.255.255         On-link         127.0.0.1    306
  127.255.255.255  255.255.255.255         On-link         127.0.0.1    306
      192.168.0.0    255.255.255.0         On-link     192.168.0.104    266
    192.168.0.104  255.255.255.255         On-link     192.168.0.104    266
    192.168.0.255  255.255.255.255         On-link     192.168.0.104    266
        224.0.0.0        240.0.0.0         On-link         127.0.0.1    306
        224.0.0.0        240.0.0.0         On-link     192.168.0.104    266
  255.255.255.255  255.255.255.255         On-link         127.0.0.1    306
  255.255.255.255  255.255.255.255         On-link     192.168.0.104    266
===========================================================================
Persistent Routes:
  None

IPv6 Route Table
===========================================================================
Active Routes:
 If Metric Network Destination      Gateway
 14     58 ::/0                     On-link
  1    306 ::1/128                  On-link
 14     58 2001::/32                On-link
 14    306 2001:0:5ef5:79fb:8d2:b4e:3f57:ff97/128
                                    On-link
 11    266 fe80::/64                On-link
 14    306 fe80::/64                On-link
 14    306 fe80::8d2:b4e:3f57:ff97/128
                                    On-link
 11    266 fe80::5cd4:9caf:61c0:ba6e/128
                                    On-link
  1    306 ff00::/8                 On-link
 14    306 ff00::/8                 On-link
 11    266 ff00::/8                 On-link
===========================================================================
Persistent Routes:
  None
  
**# arp -A displays the ARP (Address Resolution Protocol) cache table for all available interfaces.**

C:\Windows\system32> arp -A

Interface: 192.168.0.104 --- 0xb
  Internet Address      Physical Address      Type
  192.168.0.1           90-94-e4-c5-b0-46     dynamic
  192.168.0.101         ac-22-0b-af-bb-43     dynamic
  192.168.0.255         ff-ff-ff-ff-ff-ff     static
  224.0.0.22            01-00-5e-00-00-16     static
  224.0.0.251           01-00-5e-00-00-fb     static
  224.0.0.252           01-00-5e-00-00-fc     static
  239.255.255.250       01-00-5e-7f-ff-fa     static
  255.255.255.255       ff-ff-ff-ff-ff-ff     static

  
```
That brings us to the active network connections and the firewall rules.

```
C:\Windows\system32> netstat -ano

Active Connections

  Proto  Local Address          Foreign Address        State           PID
  TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       684
  TCP    0.0.0.0:445            0.0.0.0:0              LISTENING       4
  TCP    0.0.0.0:5357           0.0.0.0:0              LISTENING       4
  TCP    127.0.0.1:5354         0.0.0.0:0              LISTENING       1400
  TCP    192.168.0.104:139      0.0.0.0:0              LISTENING       4
  TCP    [::]:135               [::]:0                 LISTENING       684
  TCP    [::]:445               [::]:0                 LISTENING       4
  TCP    [::]:5357              [::]:0                 LISTENING       4
  UDP    0.0.0.0:5355           *:*                                    1100
  UDP    0.0.0.0:52282          *:*                                    976
  UDP    0.0.0.0:55202          *:*                                    2956
  UDP    0.0.0.0:59797          *:*                                    1400
  UDP    127.0.0.1:1900         *:*                                    2956
  UDP    127.0.0.1:65435        *:*                                    2956
  UDP    192.168.0.104:137      *:*                                    4
  UDP    192.168.0.104:138      *:*                                    4
  UDP    192.168.0.104:1900     *:*                                    2956
  UDP    192.168.0.104:5353     *:*                                    1400
  UDP    192.168.0.104:65434    *:*                                    2956
  UDP    [::]:5355              *:*                                    1100
  UDP    [::]:52281             *:*                                    976
  UDP    [::]:52283             *:*                                    976
  UDP    [::]:55203             *:*                                    2956
  UDP    [::]:59798             *:*                                    1400
  UDP    [::1]:1900             *:*                                    2956
  UDP    [::1]:5353             *:*                                    1400
  UDP    [::1]:65433            *:*                                    2956
  UDP    [fe80::5cd4:9caf:61c0:ba6e%11]:1900  *:*                      2956
  UDP    [fe80::5cd4:9caf:61c0:ba6e%11]:65432  *:*                     2956
```  
**# The following two netsh commands are examples of commands that are not universal across OS/SP. The netsh
firewall commands are only available from XP SP2 and upwards.**

```
C:\Windows\system32> netsh firewall show state

Firewall status:
-------------------------------------------------------------------
Profile                           = Standard
Operational mode                  = Enable
Exception mode                    = Enable
Multicast/broadcast response mode = Enable
Notification mode                 = Enable
Group policy version              = Windows Firewall
Remote admin mode                 = Disable

Ports currently open on all network interfaces:
Port   Protocol  Version  Program
-------------------------------------------------------------------
No ports are currently open on all network interfaces.

C:\Windows\system32> netsh firewall show config

Domain profile configuration:
-------------------------------------------------------------------
Operational mode                  = Enable
Exception mode                    = Enable
Multicast/broadcast response mode = Enable
Notification mode                 = Enable

Allowed programs configuration for Domain profile:
Mode     Traffic direction    Name / Program
-------------------------------------------------------------------

Port configuration for Domain profile:
Port   Protocol  Mode    Traffic direction     Name
-------------------------------------------------------------------

ICMP configuration for Domain profile:
Mode     Type  Description
-------------------------------------------------------------------
Enable   2     Allow outbound packet too big

Standard profile configuration (current):
-------------------------------------------------------------------
Operational mode                  = Enable
Exception mode                    = Enable
Multicast/broadcast response mode = Enable
Notification mode                 = Enable

Service configuration for Standard profile:
Mode     Customized  Name
-------------------------------------------------------------------
Enable   No          Network Discovery

Allowed programs configuration for Standard profile:
Mode     Traffic direction    Name / Program
-------------------------------------------------------------------
Enable   Inbound              COMRaider / E:\comraider\comraider.exe
Enable   Inbound              nc.exe / C:\users\b33f\desktop\nc.exe

Port configuration for Standard profile:
Port   Protocol  Mode    Traffic direction     Name
-------------------------------------------------------------------

ICMP configuration for Standard profile:
Mode     Type  Description
-------------------------------------------------------------------
Enable   2     Allow outbound packet too big

Log configuration:
-------------------------------------------------------------------
File location   = C:\Windows\system32\LogFiles\Firewall\pfirewall.log
Max file size   = 4096 KB
Dropped packets = Disable
Connections     = Disable
```
Finally we will take a brief look at the what is running on the compromised box: scheduled tasks, running processes, started services and installed drivers.

**# This will display verbose output for all scheduled tasks, below you can see sample output for a
single task.**

```
C:\Windows\system32> schtasks /query /fo LIST /v

Folder: \Microsoft\Windows Defender
HostName:                             B33F
TaskName:                             \Microsoft\Windows Defender\MP Scheduled Scan
Next Run Time:                        1/22/2014 5:11:13 AM
Status:                               Ready
Logon Mode:                           Interactive/Background
Last Run Time:                        N/A
Last Result:                          1
Author:                               N/A
Task To Run:                          c:\program files\windows defender\MpCmdRun.exe Scan -ScheduleJob
                                      -WinTask -RestrictPrivilegesScan
Start In:                             N/A
Comment:                              Scheduled Scan
Scheduled Task State:                 Enabled
Idle Time:                            Only Start If Idle for 1 minutes, If Not Idle Retry For 240 minutes
Power Management:                     No Start On Batteries
Run As User:                          SYSTEM
Delete Task If Not Rescheduled:       Enabled
Stop Task If Runs X Hours and X Mins: 72:00:00
Schedule:                             Scheduling data is not available in this format.
Schedule Type:                        Daily
Start Time:                           5:11:13 AM
Start Date:                           1/1/2000
End Date:                             1/1/2100
Days:                                 Every 1 day(s)
Months:                               N/A
Repeat: Every:                        Disabled
Repeat: Until: Time:                  Disabled
Repeat: Until: Duration:              Disabled
Repeat: Stop If Still Running:        Disabled
[..Snip..]
```
**# The following command links running processes to started services.**

```
C:\Windows\system32> tasklist /SVC

Image Name                     PID Services
========================= ======== ============================================
System Idle Process              0 N/A
System                           4 N/A
smss.exe                       244 N/A
csrss.exe                      332 N/A
csrss.exe                      372 N/A
wininit.exe                    380 N/A
winlogon.exe                   428 N/A
services.exe                   476 N/A
lsass.exe                      484 SamSs
lsm.exe                        496 N/A
svchost.exe                    588 DcomLaunch, PlugPlay, Power
svchost.exe                    668 RpcEptMapper, RpcSs
svchost.exe                    760 Audiosrv, Dhcp, eventlog,
                                   HomeGroupProvider, lmhosts, wscsvc
svchost.exe                    800 AudioEndpointBuilder, CscService, Netman,
                                   SysMain, TrkWks, UxSms, WdiSystemHost,
                                   wudfsvc
svchost.exe                    836 AeLookupSvc, BITS, gpsvc, iphlpsvc,
                                   LanmanServer, MMCSS, ProfSvc, Schedule,
                                   seclogon, SENS, ShellHWDetection, Themes,
                                   Winmgmt, wuauserv
audiodg.exe                    916 N/A
svchost.exe                    992 EventSystem, fdPHost, netprofm, nsi,
                                   WdiServiceHost, WinHttpAutoProxySvc
svchost.exe                   1104 CryptSvc, Dnscache, LanmanWorkstation,
                                   NlaSvc
spoolsv.exe                   1244 Spooler
svchost.exe                   1272 BFE, DPS, MpsSvc
mDNSResponder.exe             1400 Bonjour Service
taskhost.exe                  1504 N/A
taskeng.exe                   1556 N/A
vmtoolsd.exe                  1580 VMTools
dwm.exe                       1660 N/A
explorer.exe                  1668 N/A
vmware-usbarbitrator.exe      1768 VMUSBArbService
TPAutoConnSvc.exe             1712 TPAutoConnSvc
[..Snip..]
```

```
C:\Windows\system32> net start

These Windows services are started:

   Application Experience
   Application Information
   Background Intelligent Transfer Service
   Base Filtering Engine
   Bluetooth Support Service
   Bonjour Service
   COM+ Event System
   COM+ System Application
   Cryptographic Services
   DCOM Server Process Launcher
   Desktop Window Manager Session Manager
   DHCP Client
   Diagnostic Policy Service
   Diagnostic Service Host
   Diagnostic System Host
   Distributed Link Tracking Client
   Distributed Transaction Coordinator
   DNS Client
   Function Discovery Provider Host
   Function Discovery Resource Publication
   Group Policy Client
[..Snip..]
  ```
   
**# This can be useful sometimes as some 3rd party drivers, even by reputable companies, contain more holes
than Swiss cheese. This is only possible because ring0 exploitation lies outside most peoples expertise.**
```
C:\Windows\system32> DRIVERQUERY

Module Name  Display Name           Driver Type   Link Date
============ ====================== ============= ======================
1394ohci     1394 OHCI Compliant Ho Kernel        11/20/2010 6:01:11 PM
ACPI         Microsoft ACPI Driver  Kernel        11/20/2010 4:37:52 PM
AcpiPmi      ACPI Power Meter Drive Kernel        11/20/2010 4:47:55 PM
adp94xx      adp94xx                Kernel        12/6/2008 7:59:55 AM
adpahci      adpahci                Kernel        5/2/2007 1:29:26 AM
adpu320      adpu320                Kernel        2/28/2007 8:03:08 AM
AFD          Ancillary Function Dri Kernel        11/20/2010 4:40:00 PM
agp440       Intel AGP Bus Filter   Kernel        7/14/2009 7:25:36 AM
aic78xx      aic78xx                Kernel        4/12/2006 8:20:11 AM
aliide       aliide                 Kernel        7/14/2009 7:11:17 AM
amdagp       AMD AGP Bus Filter Dri Kernel        7/14/2009 7:25:36 AM
amdide       amdide                 Kernel        7/14/2009 7:11:19 AM
AmdK8        AMD K8 Processor Drive Kernel        7/14/2009 7:11:03 AM
AmdPPM       AMD Processor Driver   Kernel        7/14/2009 7:11:03 AM
amdsata      amdsata                Kernel        3/19/2010 9:08:27 AM
amdsbs       amdsbs                 Kernel        3/21/2009 2:35:26 AM
amdxata      amdxata                Kernel        3/20/2010 12:19:01 AM
AppID        AppID Driver           Kernel        11/20/2010 5:29:48 PM
arc          arc                    Kernel        5/25/2007 5:31:06 AM
[..Snip..]
```
