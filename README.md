[![](https://forthebadge.com/images/badges/made-with-python.svg)](https://www.python.org)

# Follina Exploiter CLI Tool MSDT Vulnerability (CVE-2022-30190)
A Command Line based python tool for exploit Zero-Day vulnerability in MSDT (Microsoft Support Diagnostic Tool) also know as 'Follina' CVE-2022-30190.

> Info : [New Microsoft Office zero-day used in attacks to execute PowerShell](https://www.bleepingcomputer.com/news/security/new-microsoft-office-zero-day-used-in-attacks-to-execute-powershell/)


**Made In Python(3.10.4)**


## Features

1. Execute malicious Command in Victim Device.
2. Take ReverseShell (NetCat).
3. Zero Click RTF included for .rtf files. `New`

## Requirements

- pyfiglet


## Installation

- Clone Repository

```
https://github.com/0xAbbarhSF/FollinaXploit
```

**For Linux**

- Install Required Module

```
pip3 install pyfiglet
```

**Single Line Command**

```
git clone https://github.com/0xAbbarhSF/FollinaXploit && pip3 install pyfiglet && cd FollinaXploit
```

- Run

```
python3 "follinaExploiter.py"
```

**For Windows**

- Install Required Module

```
pip install pyfiglet
```

- Run

```
python "follinaExploiter.py"
```

## How it work?

The vulnerability is being exploited by using the MSProtocol URI scheme to load some code.
Attackers could embed malicious links inside Microsoft Office documents, templates or emails
beginning with ms-msdt: that will be loaded and executed afterward without user interaction
- except if the Protected View mode is enabled. Nevertheless, converting the document to
the RTF format could also bypass the Protected View feature.

MS Office docx files may contain external OLE Object references as HTML files. There is an HTML scheme "ms-msdt:" which invokes the msdt diagnostic tool, what is capable of executing arbitrary code (specified in parameters).


## BONUS (0-click RTF version) ~~(Do it by yourself)~~ Now included

<details>
<summary><strong> Show Details </strong> </summary>
  
~~If you also add these elements under the `<o:OLEObject>` element in `word/document.xml`~~

```
<o:LinkType>EnhancedMetaFile</o:LinkType>
<o:LockedField>false</o:LockedField>
<o:FieldCodes>\f 0</o:FieldCodes>
```
~~then it'll work as RTF also (open the resulting docx and save it as RTF).~~ 

~~With RTF, there is no need to open the file in Word, it is enough to browse to the file and have a look at it in a preview pane. The preview pane triggers the external HTML payload and RCE is there without any clicks.~~
 
</details>

