# CYBERSEC2020(III) - Operation ENDTRADE

informed by Joey Chen, Trend Micro

# What is Operation ENDTRADE
-   An espionage operation, meant to generate actionable intelligence about people of interest through commercial trade.
-   Multi-year, multiple-waved attack with TTPs
-   Targetting second layer or third layer company to achieve supply chain attack.

>   The action aimed at chemical trading company. Also, it made a long-term plan and made good use of supply-chain, using surrounding companies.

# TICK
-   Other name:
-       BRONZE BUTLER, RedBaldNight
-   A Chinese origins lognstandingcyberrespionage group since 2008
-   Target Japan, Korea, Singapore, India, Taiwan etc.

## Target Scope since 2018
![scope](/assets/pie.png)

## Supply Chain Attack
-   First: Consultant Company and Consumer Electronics
-   Second: Factory and Chemical Industry
-   Third: Government and Military

## Third Party - As Target as Provider
![Target](/assets/topic.png)

## Got the real useful file, real contact information, real data

## Some Instructions were told to protect ourselves
-   Do not trust the sender name and email address !
>   But they got the real contact info from the company...
-   Be aware of the emergency and threatening word in mail topic !
-   Always check their spelling !
-   Appellations are important !
-   You can read, but do not click !
>   But the content seem to be beneficial...
-   Never open the attached file !
>   The file seem to have helpful data...
-   Never provide personal information in mail !

# Technical Summary 2019
-   2018 exploiting vulnerabilities
-   Using real Japanese decoy documents
-   Developed new malware families
-       ABK, BBK, Build_dower, Down_new, avenger, etc.
-   Check, escape and pretend existence anti-virus products
-       C:\Program Files\Fortinet\FortiClient\vir_sig\FortiAvat.exe (fake one)
-       C:\Program Files\Common Files\Check Point\CPInfo\fdecp.exe (fake one)
-       File Size Expansion to avoid Antivirus Scan

## Attack Target's Subsidiary
![subsidiary](/assets/subsidiary.png)

## Japanese Decoy about Chinese Economy
![decoy](/assets/decoy.png)

# Malware and Hacking Tools
### Adjust tools to avoid attack signature
## Public Tool
-   Lilith backdoor
-   BlackYe backdoor
-   zwcreatethreadex_test
-   doubleagent_x64
-   Rattler_32
-   Win10 UAC bypass
-   minikaiz

## Hacker Tool
-   expand
-   load_vbs
-   get_version
-   port_map
-   test_mac

## Downloader/ Dropper
-   ABK
-   BBK
-   Avenger
-   build_downer
-   down_new
-   doc_dll
-   PBA
-   snake
-   tomato

## Decoy Files
-   CVE_decoy
-   exetodoc
-   hidefloder
-   pretender

## Dropper Variant Collection
-   Import all the modules and features into their final downloaders
-   More stable, more powerful
-   All of them will connect legitimate website and verify the victim volume to decide download backdoor or not

### Dropper evolution and integration
>   2018 : ABK, BBK, tomato => 2019 : avenger
>   2018 : build_downer, snake => 2019 : down_new

## Terminate Specific Antivirus
![del_antivirus](/assets/del_antivirus.png)

# TICK Activity Since 2018 ~ 2019 First Half
## Using legitimate file as decoy
-   Stolen files from other company
## Using CVE to drop the downloader
-   CVE-2018-0802/ CVE-2018-0798
## Using new downloader and original backdoor
-   ABK/ BBK and Datper
## Using steganography to hide backdoor
-   Binary padding behind the piture
## Using legitimate website as phone home site


# Attack Scenario - Case 1
## Step 1: Use CVE-2018-0802 to drop
>   20190211eAsiaeOceaniae RisksReport1.doc

## Step 2: Execute and drop main downloader
>   8.t winhelp.dll

## Step 3: Add itself to registry and detect AV
>   svchdst.exe

## Step 4: Hash host volume info and verify with C2 (usually is a legitimate site)

## PDB strings
-   C:\users\jack\desktop\0211\doc_dll\release\docdll.pdb
-   C:\users\jack\desktop\test_dll\doc_dll\release\docdll.pdb

# TICK Activity Since 2019 Second Half
## Using legitimate file as decoy
-   Stolen from supply chain company
## Using more downloader and more backdoor
-   Down_new/build_down/avenger etc. and Casper/ Datper
-   Only active during the working hour (8:00 AM ~ 18:00 PM)
-   Target specific region user
## Using Steganography to hide backdoor
-   Apply steganography algorithm
## Using legitimate website as download site/C&C
## Using DLL injection/ DLL side loading technical

# Attack Scenario - Case 2
## Step 1: Use RTLO to drop
## Step 2: Execute and connect to C2
>   winlogan.exe

## Step 3-1: Get host volume info and CPU id to verify with C2
## Step 3-2: Upload victim info to C2
## Step 3-3: Request a steganography pciture

## Step 4: Download encrypted loader and decrypt it
## Step 5: Extract the backdoor loader
>   logo.bmp
>   winlogin.exe

## Step 6: Drop
>   AppLaunch.exe/ IEmstsc.exe

## Step 7: Drop
>   mscoree.dll

## Step 8: Dll hijack
## Step 9: Inject shellcode into svchost.exe
>   svchost.exe

## Step 10: Connect to C2

# Tools Summary
-   Virtual Machine Detect tool
-   Win 10 UAC Bypass tool
-   Load VBScript with ADS technical tool
-   Get host system service version tool
-   Get host credentials dump tool
-   Port mapping tool
-   Screen capture tool

## Load VBScript tool Builder
![VBScript](/assets/vbscript.png)

## Project V.S. Developer
![PvsDev](/assets/ProjectDev.png)

# Key Takeaways: Operation ENDTRADE
-   Multi-year, multiple-waved attack
-   Targeting second layer or third layer company to achieve supply chain attack
-   Target public relations business industry, milatary, and chemical
-   Using real Japanese decoy documents
-   Developed new malware families to avoid AV detection
-   Check the existence, pretend and escape anti-virus products

# Related Article
-   https://www.scmagazine.com/home/security-news/tick-cybergang-uses-custom-malware-to-target-japanese-websites/
-   https://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/
-   http://securityaffairs.co/wordpress/64311/apt/bronze-butler-ttps.html