https://wiki.termux.com/wiki/Remote_Access

To start OpenSSH server, you need to execute this command: `sshd`
If you need to stop `sshd`, just kill it's process: `pkill sshd`

SSH daemon does logging to Android system log, you can view it by running `logcat -s 'sshd:*'`. You can do that either from Termux or ADB.
#### Setting up password authentication
Password authentication is enabled by default in configuration file. But you can still review it ($PREFIX/etc/ssh/sshd_config), it should be like this:
```
PrintMotd yes
PasswordAuthentication yes
Subsystem sftp /data/data/com.termux/files/usr/libexec/sftp-server
```
 Set new password. Execute command `passwd`. 
 ```$ passwd
New password:
Retype new password:
New password was successfully set.
```
#### Setting up public key authentication
`ssh-keygen -t rsa -b 2048 -f id_rsa`
Copy key to the remote machine (Termux). Password authentication has to be enabled in order to install pubkey on remote machine. Now do:
`ssh-copy-id -p 8022 -i id_rsa IP_ADDRESS`
From this point password authentication can be disabled. Edit file $PREFIX/etc/ssh/sshd_config and replace line beginning with "PasswordAuthentication" by
`PasswordAuthentication no`