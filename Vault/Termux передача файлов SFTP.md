First install openssh-sftp-server
`$ pkg install openssh-sftp-server`
Connecting to Termux (sshd listening on port 8022):
`$ sftp -P 8022 192.168.1.20`
Connecting to somewhere else (sshd listening on standard port):
`$ sftp sftp.example.com`
However, to use command line SFTP client you should know some basic commands:

- **cd** PATH - change current directory to `PATH`.
- **get** REMOTE [LOCAL] - download file `REMOTE` and rename it as `LOCAL` (optional).
- **mkdir** PATH - create directory `PATH`.
- **ls** [PATH] - list files in directory `PATH`. If no argument, files in current directory will be listed.
- **put** LOCAL [REMOTE] - Upload file `LOCAL` and rename it as `REMOTE` (optional).
- **rm** FILE - Delete file `FILE`.

This is not a complete list of SFTP commands. To view all available commands, consider to view man page (`man sftp`) or view short help in interactive SFTP session by issuing command `help`.