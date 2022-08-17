# kubernetes-local
## Vagrant Script to create three virtual machines
## Intructions
1. When you try to deploy with Rocky Linux run the commands below
    ```
    $ sudo apt install build-essential dkms Linux-headers-$(uname -r)
    $ vagrant plugin install vagrant-vbguest
    ```
    If you not run this commands, you will see this error
    ```
    Vagrant was unable to mount VirtualBox shared folders. This is usually
    because the filesystem "vboxsf" is not available. This filesystem is
    made available via the VirtualBox Guest Additions and kernel module.
    Please verify that these guest additions are properly installed in the
    guest. This is not a bug in Vagrant and is usually caused by a faulty
    Vagrant box. For context, the command attempted was:

    mount -t vboxsf -o uid=1000,gid=1000,_netdev vagrant /vagrant

    The error output from the command was:

    mount: /vagrant: unknown filesystem type 'vboxsf'.

    ```