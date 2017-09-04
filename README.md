# Default Virtual Machine

A common virtual machine (VM).

## What's included

* Pip
* Automatic Python virtual environment switching
* Git default configuration

## Installation

You will want to have a good internet connection for these. This should only need to be done once.

1. [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads) (5.1.2 or later).
2. [Install Vagrant](https://www.vagrantup.com/downloads.html).
3. Download (or `git clone`) this repository to your computer.
    * Put it wherever you keep your other projects—we recommend a `startup-systems` folder.
4. Run the one-time setup from a terminal (if on Windows, make sure you use the terminal you installed above going forward, e.g. cmder):

    ```bash
    cd path/to/this/repository/
    vagrant up
    ```

1. The VM should now be running. You can verify this with `vagrant status`.
1. [Set up your SSH key for Git](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/); you will need it later.

## Guest vs host

The "host machine" is the operating system that your computer is running directly (likely Windows or OSX), whereas the "virtual machine" is the one running through Vagrant+VirtualBox, which will be [Ubuntu](http://www.ubuntu.com/desktop) (Linux).

## Usage

`host>` means you run the command on your host computer, `guest>` means it should be run within the VM. Within the VM, the terminal prompt will actually look something like `vagrant@vagrant:~$`.

```bash
host> cd path/to/this/repository/

# Start the VM (if it isn't already running).
host> vagrant up

# Connect to the VM.
host> vagrant ssh
# You are now inside the guest VM.
guest>

# When you're done, go back to your host.
guest> exit
# Stop the guest VM (to recover CPU and memory resources on your host).
host> vagrant suspend
```

based off of https://github.com/startup-systems/vm
