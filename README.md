# Change-Swap-in-Linux
Intructions to increase swap

The swap file is an important part in Linux/UNIX. Generally, when installing the system, you have to declare the size of the swap file. Let’s have a look at changing the swap size in Ubuntu. It is recommended running a “root” terminal.

# sudo -s

To find out how much swap size we have. By default, the system should have a swap file at “/swapfile”

# swapon -s

For manipulating the swap file, we have to disable it first

# swapoff -a

Now, change the size of the swap file. The total size of the swap file will be bs*count = 1M x 4096 = 4GB

# dd if=/dev/zero of=/swapfile bs=1M count=4096

My recommendation is to setup as much swap memory as you RAM. If you have 16Gb will be bs*count = 4M x 4096 = 16GB

# dd if=/dev/zero of=/swapfile bs=4M count=4096

Make the “/swapfile” usable again

# mkswap /swapfile

Turn on the swapfile

# swapon /swapfile

After restarting your system, check out the result

# swapon -s
