![Screenshot_2](https://user-images.githubusercontent.com/101652840/162251429-8a9f8c39-64b3-49c0-b81e-cdebb02c300e.png)

# cstm-update-motd infos

`author: grEEni`  
`author www: https://www.mxmedia.com`  
`author discord: greeniDevil90#9181`  

Feel free to copy and modify ;)

# cstm-update-motd installation

1.) install needed depencys and tools

```shell
apt-get update && apt-get upgrade
```

```shell
apt-get install gawk wget curl figlet git
```

Check your git version

```shell
git --version
```

Output something like this

```shell
Output
git version 2.20.1
```

2.) git clone 

Change to your `/etc/update-motd.d` directory

```shell
cd /etc/update-motd.d
```

```shell
git clone https://github.com/mx-media/cstm-update-motd.git
```

3.) edit your `/etc/pam.d/sshd`

```shell
nano /etc/pam.d/sshd
```

edit this part

```bash
# Print the message of the day upon successful login.
# This includes a dynamically generated part from /run/motd.dynamic
# and a static (admin-editable) part from /etc/motd.
session    optional     pam_motd.so  motd=/run/motd.dynamic
session    optional     pam_motd.so noupdate
```

to

```bash
# Print the message of the day upon successful login.
# This includes a dynamically generated part from /run/motd.dynamic
# and a static (admin-editable) part from /etc/motd.
session    optional     pam_motd.so  motd=/run/motd.dynamic
#session    optional     pam_motd.so noupdate
```
