
Public ->  no need to secure
Private -> need to secure passphrase

~/.ssh/

~ = home directory
.name = hidden




Auth token:
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

Public Key:
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIHMweSsQZdHpjG8sNDSTv7om4X8yXYnNYpnHegs4pwVE 

~/.ssh/id_ed25519

Private key:
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBzMHkrEGXR6YxvLDQ0k7+6JuF/Ml2JzWKZx3oLOKcFRAAAAIjCr1Xcwq9V
3AAAAAtzc2gtZWQyNTUxOQAAACBzMHkrEGXR6YxvLDQ0k7+6JuF/Ml2JzWKZx3oLOKcFRA
AAAEA7rZb6zRzV8yxk3+ugxksSgF9cQPLb+CklIJNiaC/wMnMweSsQZdHpjG8sNDSTv7om
4X8yXYnNYpnHegs4pwVEAAAAAAECAwQF
-----END OPENSSH PRIVATE KEY-----

SSH ACCESS

ssh == sftp

ssh -i ~/.ssh/privKey_file username@hostname

scp ~/.ssh/id_ed25519 dh_rcj265@san.ronins.site:~/san.ronins.site/anthonydir/neko.png ~/desktop/code

from local to remote transfer = scp (secure copy)

scp -i {key} {source} {dest}
-i = authenticate to server
for example (for dest.): user@host:~/source.html


ssh-keygen -A

install fdroid
then install termux within
"pkg update" in termux
afterwards "pkg upgrade"

pkg install openssh

1. sshd
2. ssh into
3. authorize your
4. ssh into ronins with acc given
5. authorize your....
6. scp __


> ~/.ssh
> chmod 0700 
> ~/.ssh/authorized_keys
> chmod 0644 


phone user: u0_a364
host: 192.168.114.218

ssh_keygen -t ed25519
ssh_copy

termux
/data/data/com.termux/files/home/.ssh/id_ed25519
/data/data/com.termux/files/home/.ssh/id_ed25519.pub


ronin
/home/rayaay/.ssh/id_ed25519
/home/rayaay/.ssh/id_ed25519.pub

scp -i ~/.ssh/id_ed25519 rayaay@ronins.site:~/rayaay.ronins.site/favicon.gif u0_a364@192.168.114.218


/home/rayaay/rayaay.ronins.site

uuPPp$D!Ab


scp -i ~/.ssh/id_ed25519 u0_a364@192.168.114.218:chmod rayaay@ronins.site:~/rayaay.ronins.site/

scp -i ~/.ssh/id_ed25519 u0_a364@192.168.114.218:~/.ssh/authorized_keys rayaay@ronins.site:~/rayaay.ronins.site/ 



scp -i ~/.ssh/id_ed25519 u0_a364@192.168.114.218:~/.ssh/macprivkey

  449  scp -i ~/.ssh/id_ed25519 ~/.ssh/id_ed25519 u0_a364@192.168.114.218:~/.ssh/macprivkey

  450  scp -i ~/.ssh/id_ed25519 ~/.ssh/id_ed25519 192.168.114.218:~/.ssh/macprivkey

  451  scp -P8022 -i ~/.ssh/id_ed25519 ~/.ssh/id_ed25519 192.168.114.218:~/.ssh/macprivkey 

  452  scp -P8022 -i ~/.ssh/id_ed25519 ~/.ssh/id_ed25519.pub 192.168.114.218:~/.ssh/macpubkey 

  453  ssh u0_a364@192.168.114.218 -p 8022

