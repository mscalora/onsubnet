# onsubnet
Script to detect if any local network interface is on a particular subnet by returning status code (0 = yes, non-0 = no) 
This script was specifically created to be used with the ssh-config 'Match exec' feature. It has been tested on Mac & Linux.

## Command Line Example

    onsubnet 10.20.30.

## SSH Config Example

    Match exec "onsubnet 10.10.1." host my-server
        HostName web.example.com
        Port 1111
        ForwardAgent yes
        ProxyCommand ssh -p 110 -q relay.example.com nc %h %p
    
    Match exec "onsubnet --not 10.10.1." host my-server
        HostName web.example.com
        Port 1111
