# Show_cmd_Capture
 
The Show_cmd_Capture_v1.0.exe is windows operating system utility that captures the cli commands passed on command prompt of the devices. The script will capture list of show commands output from the list of devices given in the inPut.yaml. This is not a official script and no official support is offered.

How to use:
1. The executable is tested on Microsoft Windows10 Operating systems and Mac 10.15
2. For Windows, download the latest version of Show_cmd_Capture.exe and inPut.yaml to your windows system. This system should have IP reachability to all the devices given in the input file.  
3. For Mac, download the latest version of Show_cmd_Capture_Mac and inPut.yaml to your Mac system. This system should have IP reachability to all the devices given in the input file
4. The input yaml file should be maintatained as shown in the file in this repo (retain the same file name as well).
5. Replace IPs and commands as needed, no other changes required. The ips should be comma (,) seperated only no range will be accepted.
7. For Windows, Open the command promt and execute from the download folder Show_cmd_Capture_v1.0.exe.
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/exec_yaml_file-image.png?raw=true)
8. For Mac, Open the terminal window and anvigate to the folder to where the file was downloaded. execute "chmod 777 <Show_cmd_Capture_Mac..>". Then run the file as any other script. like ./<Show_cmd_Capture_Mac> . You may want to allow this file in ‘Security & Privacy’ under ‘System Preferences'.
![Screenshot 2021-03-31 at 1 18 47 PM](https://user-images.githubusercontent.com/8314629/113111947-49d46180-9226-11eb-9876-e22912491699.png)
9. When prompted for project name provide any name (without special character),the same name will be used to create a output folder to store all show commands output. Ensure there is no folder already exist with this same name from where you are executing.
10. When prompted, provide device login credentials (username, password and enable password). The same username and password will be used of all the devices in the input file.
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/device_cred_image.png?raw=true)
8. If you would like to capture the ISE show commands as well from the script, answer "yes" when prompted
9. Script will execute all the commands to all the devices in the YAML file
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/cmd_fires_image.png?raw=true)
10. Oncee completed, you can find a a folder with  project name given, and .zip with same name and a .log file.
![alt text](https://github.com/senglobe/Show_cmd_Capture/blob/master/outputfile_image.png?raw=true)
11. The .log (file date_time_projectname.log) will show any error durin the script execution



Good to know:
1. The script will try to reach 4 devices at a time(multi threading) from the list.
2. The script waits 2 seconds before sending next commoand, to avoid sending too many requests to the device.
3. In the sample show command "show run" had given with multiple exclude key words "show run | sec exc username | password |-password | key|-key | community | secret |crypto", this is to ensure secure data is not collected in show run. In case if you want to exclude any other information from other show commands or in show run, just include them in the input.
4. Do not add CPU intensive commands to the input file like "show tech"
