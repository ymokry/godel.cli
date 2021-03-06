# Command-line tools for Godel VPN

<details>
<summary>Prerequisites</summary>

## Install Homebrew
Refer to https://docs.brew.sh/Installation to install `brew`

## Install password client
```sh
### Install 1Password CLI
$ brew install --cask 1password-cli

### Configure 1Password CLI
$ op signin https://my.1password.com <your email> <your secret key>
```
More info:
- [Brew docs](https://formulae.brew.sh/cask/1password-cli)
- [1Password docs](https://support.1password.com/command-line/)

## Install VPN client
```sh
### Install Openconnect
$ brew install openconnect
```
</details>

## Getting started as a user of Godel VPN tooling
```sh
### Clone the repo
$ git clone git@github.com:ymokry/godel.cli.git

### Replace required variables in the script
SECRET_NAME="My Secret"
VPN_URL="endpoint.example.com"
VPN_USER="n.surname"

### Copy the executable to your system folder [OPTIONAL]
$ sudo cp godel /usr/local/bin
```

## Usage
Get your password from the 1Password vault
```sh
$ godel password

### Output example:
# Getting GTE password ...
#
# Enter the password for <you email> at my.1password.com: <enter your password here>
#
# Your password has been copied to the clipboard (Command(⌘) + V for use)
```

Connect to VPN
```sh
$ sudo godel connect

### Output example:
# Connecting to <VPN endpoint> ...
#
# Password: <paste the password from the previous step>
# Password: <enter your OTP one time password>
# add host XXX.XXX.XXX.XXX: gateway XXX.XXX.XXX.XXX
# ...
# add net XXX.XXX.XXX.XXX: gateway XXX.XXX.XXX.XXX
# ...
```
**NOTE:** Don't close the terminal window. To disconnect, end the process (Control(^) + C)

## License
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
