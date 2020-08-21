# title: CYBERSEC2020(I) - Insider Threat


informed by Po-Yu Chen, FineArt Tech.

# Preface
------------
## Command and Control
[ATT&CK Matrix for Enterprise](https://attack.mitre.org/tactics/TA0011/)

-   Communication Through Removable Media
-   Custom Command and Control Protocol
-   Data Encoding
-   Data Obfuscation

> Case: [US charges engineer Xiaoqing Zheng and businessman Zhang Zhaoxi of stealing secrets, spying on General Electric to aid China](https://www.scmp.com/news/world/united-states-canada/article/3007398/us-accuses-engineer-xiaoqing-zheng-and-businessman)

> Authorities say that to conceal his alleged activities, Zheng used encryption and a technique called “steganography’’ to hide secret material in otherwise ordinary files or messages – in one instance in a digital photograph of a sunset, the indictment says.

## Attention to confidentiality of value
## Semiconductor package
What is the confidenial information of the semiconductor package?
-   design information
-   patent application
-   industrial development data
-   ...and more

# How to Steal?
------

## Step One: Stegnography
*by tools, command, script*

### Tool List
-   Xiao Steganography
-   Image Steganography
-   Steghide
-   Crypture
-   SteganographX plus
-   DeepSound
-   rSteg
-   SSuite Picsel
-   Camouflage
-   OpenStego
-   mp3stego
-   Hide"N"Send
-   wbStego4open
-   Out Secret

### Encode to files
-   Video
-   Hidden File
-   NTFS>ADS
-   Images
-   Text
-   Sound

> Example: change the font color to white in the Word files

### Online Environment
-   [CyberChef](https://gchq.github.io/CyberChef/)
-   [CTF SSLEYE](https://ctf.ssleye.com/)
-   [wntool](https://www.wntool.com/)
-   [SSLEYE](http://www.ssleye.com/)
-   ...and more

### Code Obfuscated for R&D
-   Python
-   JavaScript
-   C#
-   Java
-   ...and more

### Offline Program Tools
-   CyberChef
-   Portable Encoding Decoding Free
-   Advanced Encode Decode Tools
-   Base64 Tools
-   ...and more

### Content Encode or Obfuscated
| -- | -- | -- | --
----|----|----|-------------
| Base64 | Hexadecimal | Hex dump | CharCode |
| Decimal | Binary | Octal | Base32 |
| Base58 | Base85 | HTML entity | URL encode |
| Quoted Printable | Punycode | Text encoding | Parse TLV |
| Zhuyin | Image to Base64 | Morse code | unicode |
| ASCII | XXencode | 4 corner method


### Measurements
-   Imperceptibility
-   Undetectability
-   Robustness
-   Capability
-   Computational Complexity


## Step Two - 1: Devices
-   USB
-   CD/DVD
-   Mobile
-   Paper
-   Printer
-   Others (ex. Pi)
-   HDD

## Step Two -2: Network
-   Mail
-   Web
-   DNS Tunnel
-   UDP Tunnel
-   ICMP Tunnel
-   FTP/sFTP
-   Ngrok (Socket)
-   Cloud Tools

### Obfuscated

## Step Three: Avoid

-   Monitor or Detection
-   Analysis
-   Warning
-   Block

## Step Four: Decode



# Demo
-------
## MACOS
-   Compress the target file
![compress](/assets/compress.png)
-   get an original picture
![flower](/assets/flower.jpeg)
```sh
$cat flower.jpeg confidential.zip > payload.jpg
$file payload.jpg 
```
```
payload.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 225x225, components 3
```
![payload](/assets/payload.png)
```sh
$cp payload.jpg payload.zip
$unzip payload.zip -d result
```
```
Archive:  payload.zip
warning [payload.zip]:  9408 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: result/test5.pcap       
  inflating: result/__MACOSX/._test5.pcap  
  inflating: result/test123_0810.pcap  
  inflating: result/__MACOSX/._test123_0810.pcap
```
```sh
$ls result
```
```
__MACOSX		test123_0810.pcap	test5.pcap
```
-   Now you get the confidential file

# Devices 
----------------

![Devices](/assets/Devices_Demo.jpeg)

# None Powershell.exe run Powershell
----------------
## All of them are locked by Defender

-   [PowerLine](https://github.com/fullmetalcache/PowerLine)
-   [Not Powershell nps.exe](https://github.com/Ben0xA/nps)
-   [PowerShdll](https://github.com/p3nt4/PowerShdll)
-   [PowerLessShell](https://github.com/Mr-Un1k0d3r/PowerLessShell)
-   [Nopwershell](https://github.com/bitsadmin/nopowershell)
-   [SyncAppvPublishingServer](https://twitter.com/monoxgas/status/895045566090010624)

## Can't be detected DEMO

![Obfuscated](/assets/Obfuscated.jpg)