https://wiki.termux.com/wiki/Remote_Access
#### Using the SSH client
To login to a remote machine where the ssh daemon is running at the standard port (22):
`ssh user@hostname_or_ip`
Same as above, but if the ssh daemon running on different port, e.g. 8022:
`ssh -p 8022 user@hostname_or_ip`
Using public key authentication with ssh running on the standard port and a private key stored in the file `id_rsa`:
`ssh -i id_rsa user@hostname_or_ip`
#### SSH Agent

**Important note**: this does not work for Dropbear.

  
If you wish to use an SSH agent to avoid entering passwords, the Termux openssh package provides a wrapper script named `ssha` (note the `a` at the end) for ssh, which:

- Starts the ssh agent if necessary (or connect to it if already running).
- Runs the `ssh-add` if necessary.
- Runs the `ssh` with the provided arguments.

This means that the agent will prompt for a key password at first run, but remember the authorization for subsequent runs.