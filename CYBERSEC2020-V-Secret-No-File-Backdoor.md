# CYBERSEC2020(V) - How We find a Secret No-File Backdoor

Informed by Dove Chiu and Tim Yeh, Trend Micro

# It begins with a case...
>   When doing Live Incident Response to Exchange Server Frontend, a suspicious thread is running.
>   The thread is running within wininit.exe.
-   Dump memory
![Dump](/assets/dump.png)

-   MZ without "MZ"
![Mz](/assets/mz.png)

# Reversing
-   fix MZ header
-   Rebuild PE
-   IDA Pro
![ida1](/assets/ida1.png)

## It seem like a Webshell Technique
-   https://attack.mitre.org/software/S0072/
![isapi](/assets/isapi.png)

## Is it an ISAPI filter backdoor ?
>   ISAPI filter should be registered in specific path in registry, but we can't find anything on this PC.
![isapi.path](/assets/isapipath.png)

## Let's check on the code again
-   A big loop
-   It only responses to GET and POST
![malcode1](/assets/malcode1.png)

-   It can only appears to be a backdoor!
![malcode2](/assets/malcode2.png)

## Where is the loader ?
-   Found a locked file, C:\Windows\System32\TSVIPSrv.dll in bootlog
![bootlog](/assets/bootlog.png)
### Let's reboot

## TSVIPSrv.dll
-   Raw Copy -> Must be an abnormal file.
-   But how did this be loaded ? Is it Dll hijacking ?
![dllfile](/assets/dllfile.png)

## The Loading Sequence
![loading](/assets/loading.png)

![loading.seq](/assets/seqloading.png)

## How about kill instead of reboot ?

# Summarize: why is it so hard to find ?
## For a webshell, we don't have an actual file under the web directory (fileless)
-   No requested.html
## TSVIPSrv.dll was only loaded once, after it was injected into wininit, it is no longer in the memory (processless)
-   We can only find a suspicious thread.
## We also can't find requested.html in IIS log. (logless)
## Some anti forensic techniques are used in TSVIPSrv.dll
-   huge, locked file, some of the av or scanning program can not detect
-   modify time was edited


# Related Sample: Welcome Server Siries
![welcome1](/assets/welcome1.png)

![welcome2](/assets/welcome2.png)

## Welcome Server 2.0
![welcomepro1](/assets/welcomepro1.png)

![welcomepro2](/assets/welcomepro2.png)

## Timeline
![timeline](/assets/timeline.png)

# In details: secret backdoor built by Windows HTTPAPI
-   HTTPAPI within http.sys can be used by far from XPSP2/2003 without IIS Web Server
-   No matter if IIS server existed, the port backdoor program can be re-used
-   https://docs.microsoft.com/en-us/windows/win32/api/http/nf-http-httpaddurl

### Example to register an URL:
>   http://+:80/favicon.ico
### Windows HTTPAPI as backdoor: POC
![POC](/assets/urlregister.png)

![POC2](/assets/POC.png)

![NoIP](/assets/noip.png)

### How to bypass privileges
-   httpaddurl need administrator privilege by default
-   Use Default URLACL http://+:80/Temporary_Listen_Addresses
![adbypass](/assets/adbypass.png)

## Q: Take advantage from hacker's thoughtlessness to detect and trace backdoors
-   Default is Microsoft-HTTPAPI/2.0, which is different from IIS Server(Microsoft-IIS/7.5)
![thoughtless](/assets/thoughtless.png)

## Q: How front line forensic officer detect and trace backdoors ?
>   netsh http show servicestate
![netsh](/assets/netsh.png)

## Q: Possibilities that built-in tools being bypassed
### Disadvantages of "netsh"
-   modification of HKLM\SOFTWARE\MICROSOFT\Netsh\nshttp can make the tool bypassed
-   not easy to integrate with tool products
![bypassreg](/assets/bypassreg.png)
-   https://attack.mitre.org/techniques/T1546/007/

## Q: Is there any API can directly be used ?
-   Maybe HttpControlService works, but not well documented.

## Reverse Engineering API to build tool
![reverse engineer](/assets/whatisthis.png)

# Real IR case
![realIR](/assets/realIRcase.png)

# Conclusion
-   secret Webshell techniques are used by APT group
-   footprinted backdoor lasts at least three years. According to its compile time, it probably lasts six years or more.
-   primary target: technology and government

-   At least three different kinds of hiding technique used by hacker were sponsored from Chinese Government.
>   IIS-Share, WelcomeServer, OwlProxy
-   Be able to last for a long time and not cleared.
-   Network manager or Front-line worker can use "netsh" to discover URL checking, or use un-published Windows API to build your own tools

# Related Link
-   https://ithelp.ithome.com.tw/articles/10187490
-   https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Winnti.pdf
