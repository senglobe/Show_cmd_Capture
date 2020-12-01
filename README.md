# Show_cmd_Capture
 
The Show_cmd_Capture_v1.0.exe is windows operating system utility that captures the cli commands passed on command prompt of the devices. The script will capture list of show commands output from the list of devices given in the inPut.yaml. This is not a official script and no official support is offered.

How to use:
1. The executable is tested on Microsoft Windows10 Operating systems.
2. Download the latest version of Show_cmd_Capture.exe and inPut.yaml to your windows syste. This should have IP reachability to all the devices given in the input file.  

![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/exec_yaml_file-image.png?raw=true). 

3. The input yaml file should be maintatained as shown in the file in this repo (retain the same file name as well).
4. Replace IPs and commands as needed, no other changes required. The ips should be comma (,) seperated only no range will be accepted.
5. Open the command promt and execute from the download folder Show_cmd_Capture_v1.0.exe.
6. When prompted for project name provide any name (without special character),the same name will be used to create a output folder to store all show commands output. Ensure there is no folder already exist with this same name from where you are executing.
7. When propted, provide device login credentials (username, password and enable password). The same username and password will be used of all the devices in the input file.
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/device_cred_image.png?raw=true)
8. Script will execute all the commands to all the devices in the YAML file. 
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/cmd_fires_image.png?raw=true)
8. Oncee completed, you can find a a folder with  project name given, and .zip with same name and a .log file.
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/outputfile_image.png?raw=true)
9. The .log (file date_time_projectname.log) will show any error durin the script execution



Good to know:
1. The script will try to reach 4 devices at a time(multi threading) from the list.
2. The script waits 2 seconds before sending next commoand, to avoid sending too many requests to the device.
3. In the sample show command "show run" had given with multiple exclude key words "show run | sec exc username | password |-password | key|-key | community | secret |crypto", this is to ensure secure data is not collected in show run. In case if you want to exclude any other information from other show commands or in show run, just include them in the input.
4. Do not add CPU intensive commands to the input file like "show tech"
