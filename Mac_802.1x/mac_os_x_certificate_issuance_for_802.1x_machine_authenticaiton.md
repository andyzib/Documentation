# ADCS and OS X Certificate Issuance

## Purpose
Document how to configure Active Directory Certificate Services, Mac OS X, and a MDM (Mobile Device Managment) system for issuing certificates to OS X for the purpose of 802.1X machine authentication to Ethernet and Wi-Fi networks. 

## Requirements
* Mac computer running a supported version of OS X
* Active Directory Certificate Services running on a supported version and edition of Windows Server. 
* MDM solution such as Apple Profile Manager. 

##### Supported OS X Versions
This documentation covers issuing certificates to OS X versions that support Managed Profiles and certificate acquisition using DCE/RPC. 

* Mac OS X 10.8 (Mountain Lion)
* Mac OS X 10.9 (Mavericks)
* Mac SO X 10.10 (Yosemite)

##### Supported Windows Server Versions
In order to issue certificates to Macs using DCE/RPC Active Directory Certificate Services (ADCS) must be running on a version **and edition* of Windows Server that supports creation of customized certificate templates. 

* Windows Server 2008 Enterprise or Datacenter
* Windows Server 2008 R2 Enterprise or Datacenter
* Windows Server 2012 Standard or Datacenter
* Windows Server 2012 R2 Standard or Datacenter

## Setup

### Create Custom Template in ADCS

### Configure Profile in Profile Manager

### Deploy Profile 

## Frequently Asked Questions

##### I'm running Server 2008 R2 Standard, will it work? 
No. The ability to create custom certificate templates is only available in Server 2008 ***Enterprise*** and higher editions of Windows Server. You cannot create a custom template in any edition of Server 2003 or Standard Editions of Server 2008 and Server 2008 R2. 

Starting with Windows Server 2012, Microsoft discontinued the Enterprise edition of Windows Server. As such, the standard editions of Windows Server 2012 and Windows Server 2012 R2 ***do support*** creating custom certificate templates. 

##### I'm running Mac OS X 10.7. Will this work?
No. Obtaining a certificate using DCE/RCP was added to OS X in Mac OS 10.8. For older versions of Mac OS you have to obtain certificates using SCEP (Simple Certificate Enrollment Protocol.) Mac OS X 10.7 does have support for Managed Profiles, so you can use your MDM solution to enroll Mac OS X 10.7 and issue a certificate in the same method you would for an iOS device. 

##### I'm running Mac OS X 10.0, 10.1, 10.2, 10.3, 10.4, 10.5, or 10.6. Will this work? 
No. You may be able to obtain a certificate using SCEP on an older version of Mac OS X, but I have had no reason to research this and figure it out. Since I was able to get certificate issuance working on 10.8 and higher I used that to justify ending support of older Mac OS X versions. 

##### How do I setup Active Directory Certificate Services (ADCS)? 
Consult [Microsoft Technet](http://technet.microsoft.com/en-us/windowsserver/dd448615). Configuring Active Directory Certificate Services is out of scope of this document.  

##### Can you help me get this working for my organization? 
I would be happy to discuss offering my services as a paid consultant.  

## References
My possibly incomplete list of references. 

* [Apple KB HT5357](http://support.apple.com/en-us/HT5357 "How to request a certificate from a Microsoft Certificate Authority using DCE/RPC and the Active Directory Certificate profile payload")
* [Apple KB HT4772](http://support.apple.com/en-us/ht4772 "Accessing 802.1X networks in OS X Lion and Mountain Lion")
* [AFP 548 2012-11-20](https://www.afp548.com/2012/11/20/802-1x-eaptls-machine-auth-mtlion-adcerts "802.1x EAP-TLS Machine Authentication in Mt. Lion with AD Certificates")