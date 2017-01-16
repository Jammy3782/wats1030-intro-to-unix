# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
/home/cabox/workspace    
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md      
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?* total 36K                                                                                                                                      
drwxrwxr-x  4 cabox cabox 4.0K Jan 15 23:24 .                                                                                                  
drwxr-xr-x 11 cabox cabox 4.0K Jan 15 23:24 ..                                                                                                 
drwxrwxr-x  8 cabox cabox 4.0K Jan 15 23:24 .git                                                                                               
-rw-rw-r--  1 cabox cabox 1.1K Jan 15 23:24 LICENSE                                                                                            
-rw-rw-r--  1 cabox cabox 2.7K Jan 15 23:24 README.md                                                                                          
drwxrwxr-x  7 cabox cabox 4.0K Jan 15 23:24 challenge_files                                                                                    
-rw-rw-r--  1 cabox cabox 5.5K Jan 15 23:24 nix_scavenger_hunt.md                                                                              
-rw-rw-r--  1 cabox cabox  317 Jan 15 23:24 nix_scavenger_hunt_stretch.md                                                                      
cabox@box-codeanywhere:~/workspace$                                                                                                            
                                           
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
ls - list directory contents, -a, --all do not ignore entries starting with . -L, --dereference
when showing file information for a symbolic link, show information for the file the link references rather than for the link itself. --hide=PATTERN
do not list implied entries matching shell PATTERN (overridden by -a or -A)
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var     
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
cabox@box-codeanywhere:~/workspace$ cd                                                                                                         
cabox@box-codeanywhere:~$ pwd                                                                                                                  
/home/cabox   
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:* . 
-bash: /home/cabox: Is a directory  
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
* Press the up arrow on your keyboard. *What just happened?*
* Press the up arrow a few more times. *What do you see?*
* Run the `history` command. *What do you see?*
cabox@box-codeanywhere:~/workspace$ history                                                                                                    
    1  whoami                                                                                                                                  
    2  history                                                                                                                                 
cabox@box-codeanywhere:~/workspace$       

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?* cabox@box-codeanywhere:~/workspace$ whoami   
cabox   
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
cabox@box-codeanywhere:~/workspace$ who                                                                                                        
cabox    pts/0        Jan 15 23:24 (54.69.152.243)                                                                                             
cabox    pts/1        Jan 16 00:09 (54.186.244.104)    
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND                                                                       
root         1  0.0  0.4  33204  2596 ?        Ss   Jan15   0:00 init                                                                          
root         2  0.0  0.0      0     0 ?        S    Jan15   0:00 [kthreadd/919083]                                                             
root         3  0.0  0.0      0     0 ?        S    Jan15   0:00 [khelper/919083]                                                              
root       150  0.0  0.1  19428   820 ?        S    Jan15   0:00 upstart-udev-bridge --daemon                                                  
root       160  0.0  0.2  49216  1392 ?        Ss   Jan15   0:00 /lib/systemd/systemd-udevd --daemon                                           
syslog     312  0.0  0.2 184188  1456 ?        Ssl  Jan15   0:00 rsyslogd                                                                      
root       399  0.0  0.5  61316  3080 ?        Ss   Jan15   0:00 /usr/sbin/sshd -D                                                             
root       436  0.0  0.1  15476   940 ?        S    Jan15   0:00 upstart-socket-bridge --daemon                                                
root       447  0.0  0.1  15492   864 ?        S    Jan15   0:00 upstart-file-bridge --daemon                                                  
root       461  0.0  0.5  71260  2652 ?        Ss   Jan15   0:00 /usr/sbin/apache2 -k start                                                    
www-data   464  0.0  0.4 415720  2424 ?        Sl   Jan15   0:00 /usr/sbin/apache2 -k start                                                    
www-data   465  0.0  0.4 415720  2428 ?        Sl   Jan15   0:00 /usr/sbin/apache2 -k start                                                    
root       528  0.0  0.1  12740   856 tty1     Ss+  Jan15   0:00 /sbin/getty 38400 console                                                     
root       530  0.0  0.1  12740   852 tty2     Ss+  Jan15   0:00 /sbin/getty 38400 tty2                                                        
root       573  0.0  0.6  63876  3480 ?        Ss   Jan15   0:00 sshd: cabox [priv]                                                            
cabox      575  0.0  0.2  63876  1468 ?        S    Jan15   0:00 sshd: cabox@pts/0                                                             
cabox      576  0.0  0.8  20560  4456 pts/0    Ss+  Jan15   0:00 -bash                                                                         
root      1180  0.0  0.6  63876  3484 ?        Ss   00:09   0:00 sshd: cabox [priv]                                                            
cabox     1182  0.0  0.2  63876  1468 ?        S    00:09   0:00 sshd: cabox@pts/1                                                             
cabox     1183  0.0  0.8  20560  4464 pts/1    Ss   00:09   0:00 -bash                                                                         
cabox     1382  0.0  0.2  15520  1144 pts/1    R+   00:14   0:00 ps aux    
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*                                                     
'Top' displays a real time view of a running system. It appears that the data displayed is constantly being updated. 

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*                                                                                                                                                
                                                                                                                                               
cabox@box-codeanywhere:~/workspace$ cd challenge_files                                                                                         
cabox@box-codeanywhere:~/workspace/challenge_files$ *                                                                                          
-bash: 01: command not found                                                                                                                   
cabox@box-codeanywhere:~/workspace/challenge_files$          
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*                                                                                                                                                
                                                                                                                                               
cabox@box-codeanywhere:~/workspace/challenge_files$ more                                                                                         
Usage: more [options] file...                                                                                                                    
                                                                                                                                                 
Options:                                                                                                                                         
  -d        display help instead of ring bell                                                                                                    
  -f        count logical, rather than screen lines                                                                                              
  -l        suppress pause after form feed                                                                                                       
  -p        suppress scroll, clean screen and disblay text                                                                                       
  -c        suppress scroll, display text and clean line ends                                                                                    
  -u        suppress underlining                                                                                                                 
  -s        squeeze multiple blank lines into one                                                                                                
  -NUM      specify the number of lines per screenful                                                                                            
  +NUM      display file beginning from line number NUM                                                                                          
  +/STRING  display file beginning from search string match                                                                                      
  -V        output version information and exit                                                                                                  
cabox@box-codeanywhere:~/workspace/challenge_files$ credit_cards                                                                                 
-bash: credit_cards: command not found                              
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
cabox@box-codeanywhere:~/workspace/challenge_files$ modi_laboriosam.txt                                                                          
-bash: modi_laboriosam.txt: command not found             
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* cabox@box-codeanywhere:~/workspace/challenge_files$ grep                                                                                         
Usage: grep [OPTION]... PATTERN [FILE]...                                                                                                        
Try 'grep --help' for more information.    
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
Report bugs to: bug-grep@gnu.org                                                                                                                 
GNU Grep home page: <http://www.gnu.org/software/grep/>                                                                                          
General help using GNU software: <http://www.gnu.org/gethelp/>                                                                                   
cabox@box-codeanywhere:~/workspace/challenge_files$ -r                                                                                           
-bash: -r: command not found                                                                                                                     
cabox@box-codeanywhere:~/workspace/challenge_files$ -r, --recursive                                                                              
-bash: -r,: command not found                                                                                                                    
cabox@box-codeanywhere:~/workspace/challenge_files$            

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*   
I could not get this particular command to work in SSH terminal. 
cabox@box-codeanywhere:~/workspace/challenge_files$ ls > files.txt                                                                               
cabox@box-codeanywhere:~/workspace/challenge_files$ files.txt                                                                                    
-bash: files.txt: command not found                                                                                                                                                               
                                                                                                                                                      
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* I am seeing a list of user names. 
otal 456K                                                                                                                                       
drwxrwxr-x 7 cabox cabox 4.0K Jan 16 01:31 .                                                                                                     
drwxrwxr-x 4 cabox cabox 4.0K Jan 16 01:00 ..                                                                                                    
drwxrwxr-x 2 cabox cabox 4.0K Jan 15 23:24 01                                                                                                    
-rw-rw-r-- 1 cabox cabox    0 Jan 15 23:24 2015_special_stuff.demo                                                                               
-rw-rw-r-- 1 cabox cabox   93 Jan 15 23:24 Afton-Jast.user      
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:* cabox@box-codeanywhere:~/workspace/challenge_files$  aux | grep                                                                                  
-bash: aux: command not found                                                                                                                    
Usage: grep [OPTION]... PATTERN [FILE]...                                                                                                        
Try 'grep --help' for more information.        
