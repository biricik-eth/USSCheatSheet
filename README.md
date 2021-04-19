# Unix System Services CheatSheet
The z/OS operating system has a Unix interface in addition to the traditional TSO interface. Details can be found [here](https://en.wikipedia.org/wiki/UNIX_System_Services). Many z/OS systems programmers are unused to working in the Unix shell and have a hard time getting around in the Unix shell. Additionally, the default shell on USS is not a bash shell so help provided by traditional Unix users is sometimes deceptive. This page is intended to provide z/OS Systems Programmers (AKA Sysprogs) a cheat sheet that they can use to do most of the tasks they would need to accomplish on z/OS USS. Contributions come from Sysprogs in multiple companies. Clicking on the command will take you to detailed documentation of that particular command. Detail for all commands can be found in the [Unix System Services Command Reference](https://www-01.ibm.com/servers/resourcelink/svc00100.nsf/pages/zOSV2R3SA232280/$file/bpxa500_v2r3.pdf).



| USS "Command" | Description                                                                                                                                   |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|<img width="400"/> [chattr](https://www.ibm.com/docs/en/zos/2.1.0?topic=descriptions-chattr) +a *filename*| Change attributes of the file *filename* to make it APF authorized. Other attributes could be set as well.|
| [chtag](https://www.ibm.com/docs/en/zos/2.1.0?topic=descriptions-chtag-change-file-tag-information) -t -c IBM-1047 *filename*| Tag *filename* as an EBCIDIC. The chtag allows you to tell z/OS how the file is encoded.|
| [chtag](https://www.ibm.com/docs/en/zos/2.1.0?topic=descriptions-chtag-change-file-tag-information) -t -c ISO8859-1 *filename* | Tag *filename* as an ASCII file. The chtag allows you to tell z/OS how the file is encoded.|
| [df](https://www.ibm.com/docs/en/zos/2.1.0?topic=scd-df-display-amount-free-space-in-file-system) -kP | Display free space in the filesystems -k makes sure the numbers are in 1K (instead of 512 bytes. P means show fomplete info (including percentages |
|[find](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/find.htm) / -name *filename* 2>/dev/null| Look in the file system for *filename* starting in the root. if you come across an error (like Permission Denied) throw it away. |
| [ls](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/lscmd.htm) -lta | List the files in the current directory -l makes sure it shows data like permissions, -t sorts by time and -a shows . info|
| [ls](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/lscmd.htm) -ET | List the files in the current directory -E shows extended attributes (like APF authorization) and T shows file tagging (is it ASCII, EBCIDIC, or Binary)|
| [mkdir](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/mkdir.htm) | Create a directory. The file system is hierarchical. This will create a directory in the current directory. |
|[ps](https://www.ibm.com/docs/en/zos/2.1.0?topic=descriptions-ps-return-status-process) -ef | Return the status of all of the processes known by USS |
| [rm](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/rm.htm) * | Remove a file. With the * it will remove all of the files in the current directory |
| [rm](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/rm.htm) -R * | Remove all of the files in this directory and recurse down any directories and remove files from them too|
| [type](https://www.ibm.com/docs/en/SSLTBW_2.1.0/com.ibm.zos.v2r1.bpxa500/type.htm) *name* | Show the location of the executable known as *name*. Very useful when you want to make sure you are executing the right code.|
