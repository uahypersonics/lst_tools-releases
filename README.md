# lst_tools-releases
private distribution repository for prebuilt lst_tools python package wheels and their associated checksums.

These binaries are built from the lst_tools source code and are provided under the same BSD 3-Clause “New” or “Revised” License.

Access to this repository is restricted; redistribution outside authorized users is not permitted without explicit approval.

## Installation Guide

These wheels are for internal distribution only.

You will need:
- Access to this private repository
- set up an ssh keypair to authenticate with github

### 1. Set up ssh keypair
on the remote machine go to the .ssh directory
```bash
cd ~/.ssh
```
set up the ssh-keypair and give it a descriptive name to use for github
```bash
ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/ssh_key_name
```
example:
```bash
ssh-keygen -t ed25519 -C "john@doe.com" -f ~/.ssh/ssh_github_hpc
```

After running the commands above you should see a keypair; one private and one public key (with the ending .pub)

### 2. Add the public key to the authorized keys on github
- Go to your github profile settings
- Go to ssh and GPG keys
- Click on new ssh key
- Set the key title; e.g. ssh_{machine_name}
- drop the public key (contents of the .pub key) in the key field
- click on add ssh key

update .ssh/config file

```bash
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/{ssh_keypair_name}
```

### 3. Clone this repository
```bash
git clone git@github.com:uahypersonics/lst_tools-releases.git
cd lst_tools-releases
```
