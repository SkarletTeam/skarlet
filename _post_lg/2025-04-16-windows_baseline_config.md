---
layout: post_lg
title: "Windows Baseline Configurations"
tags: [tech, blog]
excerpt: "In this guide, we'll walk through the fundamentals of configuring baseline security settings on Windows using `LGPO.exe`. You'll learn how to back up your Local Group Policy settings, build custom configurations, and parse existing policies. This is a beginner-friendly overview, so for advanced options or the latest updates, be sure to consult Microsoft's official documentation."
author: "Anonymous"
date: 2025-04-16
image: /img/blog/baselines.webp
---

## How to install baseline security configurations ##
	
- This guide is intended to cover some of the basics of how to configure baseline security settings on windows using `LGPO.exe`, how to backup your LGPO settings, build your own and parse them. This is just a basic guide please reference Microsofts official documentation for any updates or more information on other options or commands.

---
- **Download the Microsoft Security Compliance Toolkit**

	- Go to [Microsoft Security Compliance Toolkit Download](https://www.microsoft.com/en-us/download/details.aspx?id=55319) and download LGPO and the appropriate baselines you need.
	- Documentation can be found here: [Windows Security Configuration framework](https://learn.microsoft.com/en-us/windows/security/operating-system-security/device-management/windows-security-configuration-framework/security-compliance-toolkit-10)

- **What is LGPO and how to use it?**

	- LGPO is a command-line tool to assist with automated management of Local Group Policies.	
		```  
		LGPO.exe command [...]

		Where command is one or more of the following, each of which can be repeated:

		/g path                   Import settings from one or more Group Policy backups anywhere
								  under the directory specified by path.
		/p path\lgpo.PolicyRules   Import settings from a Policy Analyzer .PolicyRules file.
		/m path\registry.pol       Import settings from a Registry Policy file into Computer (Machine)
								  Configuration.
		/u path\registry.pol       Import settings from a Registry Policy file into system-wide User
								  Configuration.
		/ua path\registry.pol      Import settings from a Registry Policy file into MLGPO User
								  Configuration for Administrators.
		/un path\registry.pol      Import settings from a Registry Policy file into MLGPO User
								  Configuration for Non-Administrators.
		/u:username path\registry.pol
								  Import settings from a Registry Policy file into MLGPO User
								  Configuration for the specified, valid local account.
		/s path\GptTmpl.inf        Apply the specified security template.
		/a[c] path\audit.csv       Apply an Advanced Auditing backup (CSV) file. With /ac, LGPO.exe
								  clears existing Advanced Auditing settings before applying the
								  settings from the CSV file, and copies the file to the local group
								  policy subdirectory so that the settings appear in the local group
								  policy editor.
		/e name|guid               Enable a Group Policy client side extension for local policy processing.
								  Specify a GUID, or one of these names (case-insensitive):
								  zone – Internet Explorer zone mapping extension; needed for
								  Site-ToZone Assignment List policy.
								  mitigation – Mitigation Options extension; needed for the Untrusted
								  Font Blocking policy (Windows 10).
								  audit – Advanced Audit Policy Configuration; ensures that
								  GpUpdate.exe also applies advanced audit policy settings.
								  LAPS – Local Administrator Password Solution (LAPS) extension.
								  DGVBS – Device Guard virtualization-based security extension; needed
								  for Credential Guard and for Device Guard (Windows 10).
								  DGCI – Device Guard code integrity policy extension; needed for
								  Device Guard (Windows 10).
		/ef path\backup.xml        Enable GP extensions referenced in backup.xml from a GPO backup.
		/t path\lgpo.txt           Apply registry-based commands from an “LGPO text” file.
		/boot                      Reboot after applying policies.
		/v                         Verbose output.
		/q                         Quiet output (no headers)
		```
	
3. **Windows 11 Security Baselines**:
	- If you downloaded **windows 11 security baselines** we can apply them using LGPO.
	- The way we can apply the Microsoft baseline, browse to the folder you unzipped `C:\Users\<User>\Downloads\Windows 11 Security Baseline\Windows11-Security-Baseline-FINAL\Documentation` you will find a file called `MSFT-Win11-FINAL.PolicyRules` this file is the policy ruleset that Microsoft has created. They have identified configurations that ideally will provide the best baseline security for windows 11. However these policy rules are just suggestions and best practices. You or your organization should review each policy rule and determane if the rule makes sense for your deployment or not. Later we will go over creation of policy rules and backup of rules.  These rules follow CIS and NIST standards so they are a very good starting point.
	- In order to deploy the baselines we do the following:
		- In the following example we will go over what the command means
		
			- Type and enter the following command(s):
				- `LGPO.exe /p .\MSFT-Win10-v1909-FINAL.PolicyRules /v > lgpo.out 2> lgpo.err`
				- `/p` is to identify the policy analyzer rules to be used and applied the policy analyzer rules can include multiple Group Policy Objects (GPOs) and client side extentions (CSEs).
				- `/v` is for verbose output.
				- `> lgpo.out 2> lgpo.err` this sends the output to two files `lgpo.out` is the verbose output, and the `lgpo.err` outputs any errors for troubleshooting.
				
		
4. **Backup GPO**:
	- In order to backup your current GPOs you will need to chose a backup path. Your can add the optional Display Name if you wish.
	
		- Type and enter the following command(s):
			- `LGPO.exe /b path [/n GPO-display-name]`
			
		- Note that the /b option does not back up MLGPO configuration settings.
		
			
5. **Parsing GPO text files**:

	- Parsing Registry Policy files to a GPO text format can be achived with the `LGPO.exe` allowing you to export current configs to an editable text document. This can allow you to build a custom LGPO template to be deployed in your environment.
	- Registry Policy files do not contain information indicating whether they are for Computer or User configuration. Use /m to indicate that the file should be interpreted as Computer Configuration, or one of the /u options.
	
	- The syntax of the parse command is as follows. you must chose a machine or user configuration.
	
		- `LGPO.exe /parse [/q] {/m|/u|/ua|/un|/u:username} path\registry.pol`
	
			- User Configuration:
			
			| Syntax | Description |
			| ----------- | ----------- |
			| /m  | Computer Configuration.|
			| /u  | System-wide User Configuration. |
			| /ua | MLGPO User Configuration for Administrators. | 
			| /un | MLGPO User Configuration for Non-Administrators. |
			| /u:username | MLGPO User Configuration for the specified, valid local account |
				
		- Example:
			
			- `LGPO.exe /parse /m C:\Windows\System32\GroupPolicy\Machine\registry.pol > regpol.txt`
	
4. **Creating GPO text files**:

	- A GPO text file can consist of any number of GPO entries, each entry contains four lines but can also contain a comment line proceeding it:
	
		- Comment (optional)
		- Configuration
		- Registry Key
		- Value Name
		- Action

	- Comment formating is as follows:
	
		- `; Revert the Intranet zone’s “Java Permissions” setting to “not configured”`

	- Configuration: 
	
		- The Configuration line is case-insensitive, cannot have leading or trailing whitespace, and must be one of the following
	
			| Syntax | Description |
			| ----------- | ----------- |
			| Computer | Computer Configuration. |
			| User | System-wide User Configuration. |
			| User:Administrators | MLGPO User Configuration for Administrators. |
			| User:Non-Administrators | MLGPO User Configuration for Non-Administrators. |
			| User:username | MLGPO User Configuration for the named local account. |

	
	- Registry Key:
		- The Registry Key is the name of a registry key, it should not be quoted even if it contains spaces. 
		- For example: `SOFTWARE\Policies\Microsoft\some policy`
	
	- Value Name:
	
		- Value Name is the name of the registry value to modify. It should not be quoted even if it contains spaces. The value (Default) can be used to denote the key’s default value. A dummy value such as * should be used for the CREATEKEY, DELETEALLVALUES, and CLEAR actions. For the DELETEKEYS action,the Value Name entry is a semicolon-delimited list of subkeys to delete from the named Registry Key
	
	- Action:

		- This field is the action that will be taken.
		
			| Syntax | Description |
			| ----------- | ----------- |
			| DELETE | Deletes the value (reverting a policy to “not configured”). This inserts a command into the registry.pol file that deletes the named value each time policy is re-applied. |
			| DWORD:n | Sets the value to a REG_DWORD value n. E.g., DWORD:1 Values can be specified in hexadecimal by prepending “0x”; e.g., DWORD:0x1000 |  
			| QWORD:n | Sets the value to a REG_QWORD value n. E.g., QWORD:1 Values can be specified in hexadecimal by prepending “0x”; e.g., QWORD:0x1000 |
			| SZ:text | Sets the value to a REG_SZ (text) value text. E.g., SZ:Authorized users only! |
			| EXSZ:text | Sets the value to a REG_EXPAND_SZ (expandable text) value text. E.g., EXSZ:%USERPROFILE%\Desktop |
			| MULTISZ:text | Sets a multi-string value. Use the character sequence \0 to separate multiple strings. Example:  MULTISZ:One\0Two\0Three |
			| BINARY:data | Sets a binary value. Use comma-separated, two-digit hex values on a single line. Example:  BINARY:00,ff,01,fe,02,fd,03,fc |
			| CREATEKEY | Create the key, but do not create any values. (Use * on the Value Name line.) |
			| DELETEALLVALUES | Delete all values from the registry key. (Use * on the Value Name line.) |
			| DELETEKEYS | Deletes one or more subkeys from the named Registry Key. The Value Name line is a semicolon-delimited list of subkeys to delete. |
			| CLEAR | Removes the named key and any commands associated with the key from policy entirely. |
			| | Note that all other commands (including the Delete command) each insert a command into the policy file. CLEAR deletes commands associated with a key, |
			| | as well as the key’s values and subkeys, from the policy file. The CLEAR has effect only when used with the /t command-line switch. |

		
			| Example GPO Text file entry |
			| ----------- |
			| ; Revert the Intranet zone’s “Java Permissions” setting to “not configured” |
			| Computer |
			| SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\1 |
			| JavaPermissions |
			| DELETE |


	- Creating the policy from GPO text file.
		
		- Type and enter the following: 
	
			- `LGPO.exe /r C:\Users\<User>\Documents\Windows 11 Security Baseline\lgpo.txt /w path\registry.pol /v`
			
			- the /r and /w arguments will build a new Registry Policy file from an GPO text file. 
 
   
   
   
   
<sub>This guide was inspired and heavily references the Microsoft LGPO.exe v3.0 Local Group Policy Object Utility documentation provided in the download of the Microsoft Security Compliance Toolkit. All rights are reserved to their prospective owners. This guide is for educational purposes only.</sub>