
# Welcome to the Blue Team Handbook Incident Response wiki!

Here you will find a wide variety of Blue Team focused commands and tutorials from "Blue Team Handbook: Incident Response Edition: A condensed field guide for the Cyber Security Incident Responder". BTHb:INRE was first published in 2014, and is getting a major update in 2025, and soon to be on the O'Reilly Books online platform. (All material (c) 2014, 2025 Don Murdoch). 

1. [Essential Pattern Matching Tutorial for Grep ‐ Incident Response]https://github.com/DonMVB/BTHbIR/wiki/Essential-Pattern-Matching-Tutorial-for-Grep-%E2%80%90-Incident-Response)
2. [Windows 10 11 Auto Start Extensibility Points (ASEPs)](https://github.com/DonMVB/BTHbIR/wiki/Windows-10-11-Auto-Start-Extensibility-Points-%28ASEPs%29)
3. [Windows Process Explorer IR Guide (Windows 11)](https://github.com/DonMVB/BTHbIR/wiki/Windows-Process-Explorer-IR-Guide-%28Windows-11%29)
4. [tcpdump and tshark for the Incident Responder](https://github.com/DonMVB/BTHbIR/wiki/tcpdump-and-tshark-for-the-Incident-Responder) and [wireshark for the Incident Responder](https://github.com/DonMVB/BTHbIR/wiki/wireshark-for-the-Incident-Responder)


For examining Windows systems there are several scripts.
1. [get-sysmon-exe-longtail.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Processes%20/get-sysmon-exe-longtail.ps1) collects a long tail analysis view of EXE's frmo Event ID 1 in the sysmon logs. Has an "hours" counter in the script.
2. [get-process-owner-cmdline.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Processes%20/get-process-owner-cmdline.ps1) gets the current list of processes and the owner. 
3. [get-service-summary.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Processes%20/get-service-summary.ps1)  gets a services summary, a little better than the SC command. 
4. [get-wmi-info.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Processes%20/get-wmi-info.ps1) can be used to gather quite a bit of WMI data.
5. [get-files-by-date.ps1](https://github.com/DonMVB/BTHbIR/blob/main/System_State/get-files-by-date.ps1) for locating files by create/modification time in a particular drive letter and path (make sure to update the variables at the top).

Windows System State 
1. [get-installed-apps-registry.ps1](https://github.com/DonMVB/BTHbIR/blob/main/System_State/get-installed-apps-registry.ps1) will pull out installed applications based on the system registry using multiple keys. 
2. [get-installed-apps-brief.ps1](https://github.com/DonMVB/BTHbIR/blob/main/System_State/get-installed-apps-brief.ps1) will list installed apps in a brief format, similar to Control Panels list, and provides names, version, and size.
3. [get-disk-info.ps1](https://github.com/DonMVB/BTHbIR/blob/main/System_State/get-disk-info.ps1) to pull out details and summary about physical and logical volumes.
4. [get-last-24-with-detail.ps1](https://github.com/DonMVB/BTHbIR/blob/main/System_State/get-last-24-with-detail.ps1) can be used to find what has changed in the last 24 hours. 

Thhere are a wide variety of utility oriented scripts.
1. [set-win-ad-audit-cis.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Utilties/set-win-ad-audit-cis.ps1) can be used to configure Windows auditing in accordance with the CIS 2019 bench mark (plus, added detailed tracking for the 4688 event!)
2. [posh_clock.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Utilties/posh_clock.ps1) creates a very large clock in a PowerShell prompt. Has some code to change the digits colors on the hour and the last five minutes in the hour. 
3. [get-sysinternals.ps1](https://github.com/DonMVB/BTHbIR/blob/main/Utilties/get-sysinternals.ps1) downloads Microsofts Sysinternals tools into C:\Sysinternals from the stable URL and cleans up after itself. 
4. [install_nsm_tools.sh]()

Scripts for Active Directory.
1. [check-ads-for-compromise.ps1](https://github.com/DonMVB/BTHbIR/blob/main/AD%20Analysis/check-ads-for-compromise.ps1) can be used to searched for a variety of indicators on an AD DC. Note - this cript produces numerous output files in C:\IR\HOST-NAME using the date stamp format advised by BTHb. Many of the event log checks stop at 15 or 20 events. Best bet - spend some time w/ the code, pull out parts to do some more in depht collection.
2. [red-team-simulator.ps1](https://github.com/DonMVB/BTHbIR/blob/main/AD%20Analysis/red-team-simulator.ps1) is something to perform causal activity and indicators that the AD DC detection script can find. 
3. There will be a set of "default system state" output files as the BTHb repository matures. 

For Linux containment, there are two exmaple scripts.
1. [[Linux Containment firewall script using nft]]
2. [[Linux Containment firewall script using iptables]]
3. [[Docker Investigation]]

For Router, Switch, and Firewall, here are some useful commands.
1. [[Cisco IOS 15.X IR Commands]]
2. [[PanOS 11.X IR Commands]]

For memory analysis with Volatility 3, there are two utility scripts 
1. The first script is an [installer](https://github.com/DonMVB/BTHbIR/blob/main/Volatility/install_volatility3.sh), which assumes a freshly installed Ubuntu.
2. There is also a more complete [symbol install](https://github.com/DonMVB/BTHbIR/blob/main/Volatility/update_volatility3_symbols.sh) script to ensure that Windows 11 memory images can be examined.

For Sysmon, there are several scripts forthcoming.
1. There is an XML [configuration file](https://github.com/DonMVB/BTHbIR/blob/main/Utilties/swift-with-net.xml ) which has Event ID 3 (network traffic) events enabled. This is a copy of the Swift on Security XML config, but w/ the extra spice of Event ID 3 enabled. 

This code and repository are copyright 2025 by Don Murdoch.
