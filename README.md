﻿# AD ACL Scanner

## Current version

**Version: 8.6**

**30 June, 2025**

**SHA256:** 82B61CACCC7A6E5A929750CB8D540D364138956B2DC44654D6A8E868F6E0C93D

**Fixed issues**
* Revealed hidden UI section for LDAP searched Depth
* New Download file function
* Always display Object Type in HTML report
* Issue with compare Default Security Descriptor
* Duplicate "Version" field in HTML report for Default Security Descriptor
* Addtional Forest and Domain collection functions

**New Features**
* Downloads for Windows Server 2025 templates



![](https://github.com/canix1/ADACLScanner/blob/master/src/ADACLScan7.0_Permission.png)

* From the CLI you can select Target and select RiskyTemplates to scan published certificate templates with "supply in request".
* The default output from CLI is structured and translated
* The default csv file output option is structured and translated and cannot be used for comparing.
* New output option for comparing that is called CSVTEMPLATE from CLI and "CSV Template" in GUI.
* Old CLI output format is produced by using the -RAW switch


## Download
**[Release](https://github.com/canix1/ADACLScanner/releases/latest)**

## Donate
Do you appreciate my work and want to buy me a beer? You can donate via PayPal: https://www.paypal.me/canix1 or send Bitcoins to <b>bc1qte7vlwhvrju7msv9hzfytwy7jd9vlmnjfpm0366d62yx4ke89czsavk0hr</b>

![](https://github.com/canix1/ADACLScanner/blob/master/src/DonateBitCoin.png)

## Description
* A tool completly written in PowerShell. 
* A tool with GUI used to create reports of access control lists (DACLs) and system access control lists (SACLs) in Active Directory .

Related blog posts
* [Forensics - Active Directory ACL Investigation](https://blogs.technet.microsoft.com/pfesweplat/2017/01/28/forensics-active-directory-acl-investigation)
* [Take Control Over AD Permissions And The AD ACL Scanner Tool](https://blogs.technet.microsoft.com/pfesweplat/2013/05/13/take-control-over-ad-permissions-and-the-ad-acl-scanner-tool)

## History

Features and fixes https://github.com/canix1/ADACLScanner/wiki/History

## Features
* Search with onelevel and set the depth of the search
    * Example:
```
ADACLScan.ps1 -Base rootdse -SearchDepth 3 -LDAPFilter "(objectClass=OrganizationalUnit)"
```

* Run effective rights report from the command line.
* parameter from command line to get modified date of security descriptor in report.
![](https://github.com/canix1/ADACLScanner/blob/master/src/effectiverights.gif)

* Save to excel file without excel installed. Both from UI and command line. Requires ImportExcel PowerShell Module. You can install ImportExcel directly from the Powershell Gallery.
![](https://github.com/canix1/ADACLScanner/blob/master/src/SaveToExcel.jpg)

* Command line support.
![](https://github.com/canix1/ADACLScanner/blob/master/src/adaclscan_commandline.gif)
* Custom search filter for scanning objects. 
* Support input from pipeline. You can call ADACLScan.ps1 by sending a distinguishedName via pipeline.
* Added formated synopsis to the script.

![](https://github.com/canix1/ADACLScanner/blob/master/src/ADACLScan6.0.png)
## Feature list

* Scan linked Group Policy Objects
* View HTML reports of DACLs/SACLs and save it to disk. 
* Export DACLs/SACLs on Active Directory objects in a CSV format. 
* Export DACLs/SACLs on Active Directory objects in a Excel sheet. 
* Connect and browse you default domain, schema , configuration or a naming context defined by distinguishedname. 
* Browse naming context by clicking you way around, either by OU�s or all types of objects. 
* Report only explicitly assigned DACLs/SACLs. 
* Report on OUs , OUs and Container Objects or all object types. 
* Filter DACLs/SACLs for a specific access type.. Where does �Deny� permission exists? 
* Filter DACLs/SACLs for a specific identity. Where does "Domain\Client Admins" have explicit access? Or use wildcards like "jdoe". 
* Filter DACLs/SACLs for permission on specific object. Where are permissions set on computer objects? 
* Skip default permissions (defaultSecurityDescriptor) in report. Makes it easier to find custom permissions. 
* Report owner of object. 
* Compare previous results with the current configuration and see the differences by color scheme (Green=matching permissions, Yellow= new permissions, Red= missing permissions). 
* Report when permissions were modified 
* Can use AD replication metadata when comparing. 
* Can convert a previously created CSV file to a HTML report. 
* Effective rights, select a security principal and match it agains the permissions in AD. 
* Color coded permissions based on criticality when using effective rights scan. 
* List you domains and select one from the list. 
* Get the size of the security descriptor (bytes). 
* Rerporting on disabled inheritance . 
* Get all inherited permissions in report. 
* HTLM reports contain headers. 
* Summary of criticality for all report types. 
* Refresh Nodes by right-click container object. 
* Exclude of objects from report by matching string to distinguishedName 
* You can take a CSV file from one domain and use it for another. With replacing the old DN with the current domains you can resuse reports between domains. You can also replace the (Short domain name)Netbios name security principals. 
* Reporting on modified default security descriptors in Schema. 
* Verifying the format of the CSV files used in convert and compare functions. 
* When compairing with CSV file Nodes missing in AD will be reported as "Node does not exist in AD" 
* The progress bar can be disabled to gain speed in creating reports. 
* If the fist node in the CSV file used for compairing can't be connected the scan will stop. 
* Display group members in groups in the HTLM report. 
* Present the value of the true SDDL in NTsecurityDescriptor, bypassing Object-Specific ACE merge done when a new instance of the ObjectSecurity class is initialized.
## System requirements
* Powershell 3.0 or above 
* PowerShell using a single-threaded apartment 
* Some functions requires Microsoft .NET Framework version 4.0