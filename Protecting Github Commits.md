#git #cmd

Requirements:
- Git Credential Manager
- GPG
- Pinentry

#### Part 1
---
get your @users.noreply.githumb.com email in [https://github.com/settings/emails](https://github.com/settings/emails)

Make sure that the checkbox `Keep my email addresses private` together with `Block command line pushes that expose my email` is checked.

##### GPG Key Generation:
gpg --full-generate-key

Choose the defaults or `ECC (sign and encrypt)`, `Curve 25519`, and `1y`.

Fill in the needed information and use the github provided email

Now that that is configured, time to export the generated keys so we can tell GitHub which keys proves who we are. First step is to get the key id, specifically the long keyid.

```
gpg --list-keys --keyid-format long
```

The long keyid is usually after `pub ed25519/`, copy the long keyid and execute the command below:

```
gpg --export --armor {long-keyid}
```

Copy the text in the terminal or use `pbcopy` to send exported data to clipboard

```
gpg --export --armor {long-keyid} | pbcopy
```

#### Part 2
---
Now that the keys is copied to our clipboard, we must tell Github our GPG Public Key for it to be able verify commits we signed.

Open [https://github.com/settings/keys](https://github.com/settings/keys) on a browser and click `New GPG key` button. Paste the key.

Configure git to use a signing key

```
	git config user.signingkey {long-keyid}
```

This is also a good time to re-configure your Git to no longer use your business email. Repositories can be scanned and is a good source of valid emails for spamming and phishing.

```
git config user.email {github_provided_username}@users.noreply.github.com 
```

Find the path of the gpg application using `which`

```
which gpg
```

Copy the return path and configure git to use that as the `gpg.program`. Assuming the value is `/opt/homebrew/bin/gpg`, execute the command below:

```
git config gpg.program /opt/homebrew/bin/gpg
```

or use backtick to use a command output as a command argument like:

```
git config gpg.program `which gpg`
```

### Tell our Shell about GPG (mac, idk about windows lol)

There is no doubt that we use different shells so to cater to two commonly used shells while in terminal, execute the command below.

```
current_shell=`ps -p $$ | awk 'FNR == 2 {print}' | awk '{print $4}'`; if [[ $current_shell == '-bash' ]]; then echo 'export GPG_TTY=$(tty)' >> ~/.bashrc; elif [[ $current_shell == '/bin/zsh' ]]; then echo 'export GPG_TTY=$(tty)' >> ~/.zshrc; fi
```

What the above command does is check whether you are using `bash` or `zsh` in your current terminal. It then sets up an environment variable `GPG_TTY`, so it knows that it can invoke gpg.

### Reload our environment/shell read command (rc)

With our read command file configured to utilize GPG, we need to reload it so the new variable will be available to us.

For those who use bash:

```
source ~/.bashrc
```

For those who use zsh:

```
source ~/.zshrc
```

The above will ensure that GPG_TTY variable is now an available environment variable.

Alternatively, closing the terminal and opening it will cause it to reload the rc file. This confuses other engineers, making them wonder why it suddenly worked.


Time to setup git to always sign commits.
```
git config commit.gpgsign true
```