## Systems Engineer Study

Systems Engineering (also known as Infrastructure Engineering, Operations Engineering, or DevOps) is a challenging but rewarding career path. Because Systems Engineering draws from a wide variety of smaller topics, it can be hard to know where to start and in what order to begin. This resource is intended to give you a sketch of some of the learning-paths that that can lead you to a career in Systems Engineering.

## linux-refresh

Command line tools in Linux are all file based. Printers, disks and other hardware are also files.  Essential commands are found in the bin (binaries) directory on /bin. Super user commands are in /sbin. 



## Linux
    Important Linux Commands List:

        ## User
        su - switch user
        sudo - run with root
        sudo su - or sudo -i - switch user to root user
        sudo is controlled by the sudoers file in /etc/sudo and should be edited with visudo. This command opens the sudoers file in a safe manner, preventing multiple simultaneous edits and performing syntax checks

        Sudoers file syntax:
        username ALL=(ALL:ALL) ALL
            username/groupname: The name of the user or group (with % prefix for groups)
            First ALL: Applies to all hosts
            (ALL:ALL): The user can run commands as all users and all groups
            Last ALL: The user can run all commands

                
        ##File Commands:

        ls – directory listing
        ls -al – formatted listing with hidden files
        cd dir - change directory to dir
        cd – change to home
        pwd – show current directory
        mkdir dir – create a directory dir
        rm file – delete file
        rm -r dir – delete directory dir
        rm -f file – force remove file
        rm -rf dir – force remove directory dir *
        cp file1 file2 – copy file1 to file2
        cp -r dir1 dir2 – copy dir1 to dir2; create dir2 if it doesn't exist
        mv file1 file2 – rename or move file1 to file2 if file2 is an existing directory, moves file1 into directory file2
        ln -s file link – create symbolic link link to file
        touch file – create or update file
        cat > file – places standard input into file
        more file – output the contents of file
        head file – output the first 10 lines of file
        tail file – output the last 10 lines of file
        tail -f file – output the contents of file as it grows, starting with the last 10 lines
        
        ##Process Management:

        ps – display your currently active processes
        top – display all running processes
        kill pid – kill process id pid
        killall proc – kill all processes named proc *
        bg – lists stopped or background jobs; resume a stopped job in the background
        fg – brings the most recent job to foreground
        fg n – brings job n to the foreground
        
        ##File Permissions:

        chmod octal file – change the permissions of file to octal, which can be found separately for user, group, and world by adding:
        4 – read (r)
        2 – write (w)
        1 – execute (x)
        
        ###Examples:

        chmod 777 – read, write, execute for all
        chmod 755 – rwx for owner, rx for group and world

        chown - change file owner and group
        
        ###EXAMPLES
            chown root /u
                    Change the owner of /u to "root".

            chown root:staff /u
                    Likewise, but also change its group to "staff".

            chown -hR root /u
                    Change the owner of /u and subfiles to "root".

        
        ##SSH:

        ssh user@host – connect to host as user
        ssh -p port user@host – connect to host on port port as user
        ssh-copy-id user@host – add your key to host for user to enable a keyed or passwordless login
        
        ##Searching:

        grep pattern files – search for pattern in files
        grep -r pattern dir – search recursively for pattern in dir
        command | grep pattern – search for pattern in the output of command
        locate file – find all instances of file
        
        ##System Info:

        date – show the current date and time
        cal – show this month's calendar
        uptime – show current uptime
        w – display who is online
        whoami – who you are logged in as
        finger user – display information about user
        uname -a – show kernel information
        cat /proc/cpuinfo – cpu information
        cat /proc/meminfo – memory information
        man command – show the manual for command
        df – show disk usage
        du – show directory space usage
        free – show memory and swap usage
        whereis app – show possible locations of app
        which app – show which app will be run by default. E.g. (which ls)
        
        ##Compression:

        tar cf file.tar files – create a tar named file.tar containing files
        tar xf file.tar – extract the files from file.tar
        tar czf file.tar.gz files – create a tar with Gzip compression
        tar xzf file.tar.gz – extract a tar using Gzip
        tar cjf file.tar.bz2 – create a tar with Bzip2 compression
        tar xjf file.tar.bz2 – extract a tar using Bzip2
        gzip file – compresses file and renames it to file.gz
        gzip -d file.gz – decompresses file.gz back to file
        
        ##Network:

        ping host – ping host and output results
        whois domain – get whois information for domain
        dig domain – get DNS information for domain
        dig -x host – reverse lookup host
        wget file – download file
        wget -c file – continue a stopped download
        ##Installation:

        dpkg -i pkg.deb – install a package (Debian)
        rpm -Uvh pkg.rpm – install a package (RPM)
        
        ##Install from source:

        ./configure
        make
        make install
        
        ##Shortcuts:

        Ctrl+C – halts the current command
        Ctrl+Z – stops the current command, resume with
        fg in the foreground or bg in the background
        Ctrl+D – log out of current session, similar to exit
        Ctrl+W – erases one word in the current line
        Ctrl+U – erases the whole line
        Ctrl+R – type to bring up a recent command
        !! - repeats the last command
        exit – log out of current session

## Linux File System:
    Everything is a file!
        /bin - essential commands
        /sbin - super user essential commands
        /usr - userspace folder
            /usr/bin - user essential commands (same as /bin)
            /usr/sbin - root essential commands (same as /sbin)
        /boot - files the system needs to boot. aka boot files
        /var - log fles and web app files
        /tmp - temp files. lost after reboot and 
        /lib - shared librries - things the system needs to boot
        /home - where user files live. /desktop /docs etc...
        /root - where root user files live. /desktop /docs etc... 
        /dev - devices, hardware and emulated hardware
            /dev/sda1,2,3 and so on - disk files
        /etc - configuration files for the system.. network etc... and some application files.
            /etc/network/interfaces - network interfaces
        /mnt and /media - mount drives (like usb flash)

## Managing Users
    adduser - create a new user or update default new user information (must be ran with root priv)
        all users are listed in /etc/passwd as username:x:UID:GID:user_info:home_directory:login_shell. 
         passwords are saved as a hash in /etc/shadow
    useradd - doesnt set home directory or login shell. 
    usermod - modify a user account
    groupadd - create a new group
    groupmod - modify a group definition on the system
    gpasswd - administer /etc/group and /etc/gshadow (remove user from group)
    groupdel - delete a group


## Bash Scripting:
    Linux User and group management:
    Linux Process Management:
    Linux Perfomrance Monitoring (htop, top, iotop):

## AWS Core Services
	EC2:
	S3:
	RDS:
	VPC:
	IAM:

## Networking:
    TCP/IP:
    DNS:
    DHCP:
    Subnetting:
    Routing and Switching:
    Network Troubleshooting tools:
        Traceroute:
        Ping: 
        Netstat:

## Scripting and Automation
    Python Basics for SysAdmin
    Practice writing a bash script
    Configuration Management tools:
        Ansible:
        Puppet:
    Error handling basics in scripts:
    AWS CloudFormation IAC:

## Security
    Linux basic Security Best Practices:
    Principle of least privilege in Linux:
    AWS Security Groups:
    IAM roles and Policies in AWS:
    Common Security Threats and Mitigation Strategies:
    Firewalls:
    Endpoint Detection and Protection Software:
    Antivirus:

## Package Management
    apt provides a high-level commandline interface for the package
    management system. (includes a repository which allows for update)
    dpkg is a medium-level tool to install, build, remove and manage Debian packages. (no repo for updates)
    git - version management tool often ussed to clone git repos using git clone ...
    pip - A tool for installing and managing Python packages

# Operating System Fundamentals
    The POSIX family of Standards (Portable Operating System Interface)
    "Unix-like" Operating Systems (Linux)
    Process Models
    Threading
    File Systems
    Permissions
# Operating System Virtualization
    docker
# Command-Line Shells
    bash
# standard streams
    stdout, stdin, stderr
# shell-scripting
# Command-Line Utilities
# General Utilities
    man, cp, mv, cat, echo, rm, tar, grep
# Network Utilities
    rsync, dig, netstat, nc
# Pattern Matching / Batch Processing Utilities
    awk, sed
# Networking Fundamentals
    The OSI Model:
# Internet Protocols
    tcp/ip, tls/ssl, http, dns
# Network Security
    firewall, iptables