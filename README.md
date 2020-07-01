# Windows_Command_Line_Tutorial
A tutorial describing the different commands one can can use and the different tasks one can accomplish using Windows Command Prompt.


Windows Command Line-

1) To Open The Terminal Window-
	(Windows Button + R)   Opens Run Command
	Type cmd and Enter

2) Create new file-
	Use echo command. Syntax-
	echo ["Enter the text you want to place is the filename.txt"] >> filename.txt
	One '>' overrides all contents in the file if it already exists and replaces it with the newly entered text. 
	Two '>' used in this example appends the existing text in the filename.txt to the end of the file if it already 
	exists or creates a new file if it doesn't exist.

3) Print the Contents of the File Created-
	use type command. Syntax-
	TYPE filename.txt

4) Create new Directory-
	use mkdir command. Syntax-
	mkdir newDirectory or mkdir E:\newDirectory

5) To change path and access the directory
	use cd command. Syntax-
	cd newDirectory (if the directory is in existing path of terminal)
	dir E:\newDirectory (if the directory does not exists in the path of the terminal)

6) To change the name of given file or directory
	we use 'ren' command(this command only works if the file or directory is in the path of the terminal). Syntax-
	ren oldfilename.txt newfilename.txt 
	ren oldDirectory_name newDirectory_name

7) To move file or directory to another directory-
	use move command.
	move (filename.txt_or_oldDirectory) newDirectory

8) To view the contents of directory-
	use dir command. Syntax-
	dir newerDirectory    or dir C:\

	we can also use /s Sub-Folders to display all the sub-Folders. Syntax-
	dir C:\ /s

	we can view all the special functions involved with dir by using the following command-
	dir /?

9) To view the contents of directory in a text file-
	use dir command. Syntax-
	dir E:\ > E:\result.txt		or	dir E:\newDirectory > E:\result.txt

10) To delete file-
	use del command. Synatx-
	del filename.txt    

11) To delete directory-
	use rmdir command.Syntax-
	rmdir directory_name 					
	(This deletes empty directories only)
 	
	rmdir directory_name /s /q
	(We use the above command to delete directories which have files in them 
	/s   Stands for Sub-Folders and /q   is used to suppress the display 
	warning that directory is not empty)

12) To view all contents of a directory or folder-
	use Tree command. Syntax-
	tree (directory_name or path(ex- E:\))  
	
	we can include the more command to get more information. Synatx-
	tree (directory_name or path(ex- E:\)) |More

	we can view the names of the files in each folder by using /F. Syntax-
	tree (directory_name or path(ex- E:\)) /F

13) To view date or time using command prompt-
	use date or time command. Syntax-
	 date /t or time /t

	to change date or time enter-
	date or time 

	To view both date and time together type-
	 date /t && time /t

	to change date and time together enter-
	 date (mm-dd-yyyy) && time (time in 24hrs format)

14) To view your time zone-
	use tzutil command. Synatx-
	 tzutil /g

	we can see all the different functions of tzutil command by typing-
	 tzutil /?

15) For Disk Management -
	use diskpart command. Syntax-
	 diskpart
	(The command opens another screen where in further commands can be entered)

	Typing 'help' or '?' gives a list of commands with descriptions. We can use these list of commands to understand 
	and learn more about our disk drives.
	
	Typing 
	 list disk
	 gives a list of disks in the computer.
	
	Output-
	 Disk ###  Status         Size     Free     Dyn  Gpt
         --------  -------------  -------  -------  ---  ---
         Disk 0    Online          238 GB  1024 KB        *

	We can type 
	 select disk 0
	to select disk 0.

16) Creating a partition in disk-
	Select a disk to perform the partition.Command-
 	  select disk 0
	Creating partition-
	 create partition 
	We should select what kind of partition we wish to create. Here we are creating a primary partition.
	 create partition primary
	We can adjust amount of memory alloted to patition.
	 creating pattition size = 10
	here memory size is in MB.

17) To delete partition-
	Syntax-
	 delete partition

18) Group Policy Settings-
	Group Policy is a feature of the Microsoft Windows NT family of operating systems that controls the 
 	working environment of user accounts and computer accounts. Group Policy provides centralized management 
	and configuration of operating systems, applications, and users' settings in an Active Directory environment.
	
	We can check the group policy settings and update them using the command line. We use the command 'gpupdate'.
	Syntax-
	 gpupdates
	The above command updates the group policy settings.
	To learn what more can be done with gpupdate type-
	 gpupdate/?

20) Resultant Set of policy(RSoP)-
	RsoP (Resultant Set of Policy) is a Microsoft tool that is built into Windows 7 and later versions. 
	It provides administrators a report on what group policy settings are getting applied to users and computers. 
	It can also be used to simulate settings for planning purposes.
	Syntax-
	 gpresult
	We can find more on RSoP of our system by typing-
	 gpresult/?
	Which will display the set of functions applicable with gpresult.

21) To format disk-drive-
	use format command. To know about all the functions that go with the format command. Type-
	 format/?

22) To shut down, restart or logging off computer-
	use shutdown command. Syntax-
	 shutdownn 
	The above command shows a list of possible functions that can be used with shutdown command to perform various
	types of restarting or logging off to suite with the needs of the computer.

23) Obtaining information from the Windows Management Instrumentation Database-
	we use the wmic command. It finds the information on the local or remote computer.Syntax-
	 wmic bios				
	bios - Basic Input and Output Service Management
	
	To obtain the computers Serial Number-
	 wmic bios get serialnumber

	To get more information on the wmic command-
	 wmic bios /?

	To get more information on the system-
	 wmic computersystem

	To obtain information generated by the computersystem command-
	 wmic computersystem get (keyword)
	Examples for the 'keyword' include Manufacturer, Model, DNSHostName etc.
	The way we obtain the Serial Number as stated above is one such example.

	To get multiple data at once-
	 wmic computersystem get NumberOfProcessors, NetworkServerModeEnabled

24) Obtaining information on the disk drive using the wmic-
	use-
	 wmic diskdrive

	To obtain information generated by the diskdrive command-
	 wmic diskdrive get (keyword)
	Examples for the 'keyword' include Status, Availability, BytesPerSector, Capabilities etc.

	To get multiple data at once-
	wmic diskdrive get status, model
