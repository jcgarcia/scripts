

# JC Scripts Collection

Welcome to my collection of useful scripts! This repository contains
various Bash scripts designed to simplify tasks, enhance productivity,
and streamline workflows.

## Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
- [Configurations](#configurations)
- [Available Scripts](#available-scripts)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This repository includes scripts that automate tasks such as AWS profile
management, device handling, and more. The scripts are organized into a
compact library file (`scripts.ar`) to make distribution easy and
efficient. Each script is documented and designed for ease of use,
customization, and flexibility.

---

## Getting Started

### Steps to Set Up the Environment

1. Clone the repository:

```bash
mkdir ~/scripts && cd ~/scripts 

git clone git@github.com:jcgarcia/scripts.git

```
2.  Run the setup script:

```bash

./installscripts
```
3.  The setup script will:

    -   Verify that all required components are present, including
        README.md, README.pdf, .jcscripts, installscript, and
        lib/scripts.ar.

    -   Extract scripts from the scripts.ar library into the directory
        specified in .jcscripts (default: ~/scripts).

    -   Make valid shell scripts executable.

    -   Add the scripts directory to your system's PATH for easy
        access.

4.  After installation, you can call any script directly by its name
    from any location:

```bash

script_name
```
## Configurations

The `.jcscripts` file contains configuration options for the scripts repository. Below are the configurable values:

- **EDITOR**: Specifies the text editor for editing scripts (default: `vi`).
- **SCRIPTS_DIR**: Defines the directory where the scripts will be stored (default: `~/scripts`).
- **SSH_KEY**: Path to the SSH key for accessing GitHub (default: `~/.ssh/personalkey.pem` you must generate your own key and change that in the config file).

### Generating an SSH Key

To generate your own SSH key:

1. Run the provided script, and follow the prompts to create the key.
  
```bash
   ./generate_ssh_key
```


2. Follow the prompts to create the key.


- Copy the contents of the public key file (~/.ssh/personalkey.pem.pub):

```bash
cat ~/.ssh/personalkey.pem.pub
```
- Log in to GitHub and navigate to Settings > SSH and GPG Keys > New SSH Key.
[Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?form=MG0AV3)


- Paste the contents into the Key field, give it a meaningful title, and save.


Example .jcscripts file:

```bash

# Configuration for scripts
EDITOR=vi
SCRIPTS_DIR=~/scripts
```
## Available Scripts

Here are all the scripts included in this repository:

- **awsaccess**: Manage AWS Identity Center operations like users and groups.
- **awsaddprofile**: Interactively add new AWS profiles and validate login.
- **awslogin**: Dynamically sets AWS default profile after SSO login.
- **awsmoveaccount**: Move AWS accounts between organizational units.
- **awsnewaccount**: Create a new AWS account, wait for creation, and verify membership in the organization.
- **awsorg**: Fetch and display AWS Organization layout in multiple formats.
- **awsres**: Dynamically retrieve AWS resource information.
- **awsresources**: Manage AWS resources efficiently.
- **backup**: Example backup script for your systems.
- **connecttoaws**: Automate AWS connection processes.
- **createOrgAdm**: Automates the creation of an organization administrator profile.
- **createscripts**: Generate and manage new scripts using a predefined template.
- **device**: Dynamically list, mount, and unmount devices, including WSL-mounted drives.
- **edit**: Edit an existing script or create one if it doesn’t exist.
- **getamiinfo**: Fetch and display information about AWS AMIs (Amazon Machine Images).
- **installscripts**: Automates the installation and setup of scripts from the repository.
- **listownamis**: Lists owned AMIs for your AWS account.
- **publish**: Creates a clean distribution package for the repository, ready to upload to GitHub.
- **newkey**: Automates the process of generating a new SSH key for secure access to GitHub and updates the `.jcscripts` configuration file with the new key path. This ensures seamless integration with the repository's settings.

- **scripts**: Lists all available scripts in the scripts directory.
- **template**: A sample script template for creating new Bash scripts.

For detailed instructions on using each script, refer to the comments at the beginning of the script files. If you're unsure how to get started, see the [Getting Started](#getting-started) section above.


**Contributing**

Contributions are welcome! If you'd like to contribute, please:

1.  Fork this repository.

2.  Create a new branch for your feature or bug fix.

3.  Commit your changes and submit a pull request.

**License**

This repository is released under the MIT License. Feel free to use and
adapt the scripts as needed.

**Additional Notes**

If the setup script detects that the environment has already been
initialized, it will notify you and avoid reinitializing. To force
reinstallation, delete the marker file:

```bash

rm ~/.scripts_installed
```
To customize the editor or scripts directory, modify .jcscripts before
running installscripts.

