## Linux commands

### Contents:
* How to know Kernel version using source code?
* What are DTS, DTB, DTC and its usage?

* Kernel: How to know Kernel version using source code?
   1. **Locate the Version File**: The kernel version is typically defined in the `Makefile` located at the root of the source tree. Open the `Makefile` and look for the following lines:
     ```makefile
     VERSION = 5
     PATCHLEVEL = 10
     SUBLEVEL = 0
     EXTRAVERSION = -imx
     ```
     These lines indicate the kernel version. In this example, the version would be `5.10.0-imx`.
  2. **Check the `include` Directory**: Another place to check is the `include/generated/utsrelease.h` file, which is generated after building the kernel. This file contains the `#define UTS_RELEASE` line that specifies the kernel version.

* BSP, Bootloader: 1. DTS, DTB, DTC
Device Tree Source (DTS) files are simple text files that can be compiled into a binary Device Tree Blob (DTB) (or device tree binaries (DTBs)) format using the Device Tree Compiler (DTC) tool.

* Fix: [permission denied for root@localhost for ssh connection](https://askubuntu.com/questions/497895/permission-denied-for-rootlocalhost-for-ssh-connection)
  * In `/etc/ssh/sshd_config`, set
  ```sh
  PermitRootLogin without-password
  PermitRootLogin yes
  ```
  * `sudo service ssh restart` => restart ssh service.

<details> <summary>Click for more details for Root SSH  </summary>

By default, the SSH server denies password-based login for root. In /etc/ssh/sshd_config, if the following line exists, possibly commented out (with a # in front):

PermitRootLogin without-password
Then change it to the following, uncommenting if needed (remove the # in front):

PermitRootLogin yes
And restart SSH:

sudo service ssh restart
Or, you can use SSH keys. If you don't have one, create one using ssh-keygen (stick to the default for the key, and skip the password if you feel like it). Then do sudo -s (or whatever your preferred method of becoming root is), and add an SSH key to /root/.ssh/authorized_keys:

cat /home/user/.ssh/id_rsa.pub >> /root/.ssh/authorized_keys

</details>

## Ubuntu 20.04
1. Error:

Fix:
```
dpkg -l | grep ^iU | awk '{print $2}' | xargs sudo dpkg --purge
```
For more: [Soln. in askubuntu.com Link](https://askubuntu.com/questions/1330174/apt-fix-broken-install-not-working)

2. Also for below error
Error:
```
Unpacking python3-catkin-pkg-modules (0.4.24-1) ...
dpkg: error processing archive /tmp/apt-dpkg-install-HRuYld/52-python3-catkin-pkg-modules_0.4.24-1_all.deb (--unpack):
 trying to overwrite '/usr/lib/python3/dist-packages/catkin_pkg/__init__.py', which is also in package python3-catkin-pkg 0.4.16-1
Preparing to unpack .../53-python3-catkin-pkg_0.4.24-100_all.deb ...
Unpacking python3-catkin-pkg (0.4.24-100) over (0.4.16-1) ...
Preparing to unpack .../54-python3-rospkg-modules_1.4.0-1_all.deb ...
Unpacking python3-rospkg-modules (1.4.0-1) ...
dpkg: error processing archive /tmp/apt-dpkg-install-HRuYld/54-python3-rospkg-modules_1.4.0-1_all.deb (--unpack):
 trying to overwrite '/usr/lib/python3/dist-packages/rospkg/__init__.py', which is also in package python3-rospkg 1.2.3-1
Preparing to unpack .../55-python3-rosdistro-modules_0.8.3-1_all.deb ...
Unpacking python3-rosdistro-modules (0.8.3-1) ...
dpkg: error processing archive /tmp/apt-dpkg-install-HRuYld/55-python3-rosdistro-modules_0.8.3-1_all.deb (--unpack):
 trying to overwrite '/usr/lib/python3/dist-packages/rosdistro/__init__.py', which is also in package python3-rosdistro 0.8.0-1
Preparing to unpack .../56-python3-rosdistro_0.8.3-100_all.deb ...
Unpacking python3-rosdistro (0.8.3-100) over (0.8.0-1) ...
Preparing to unpack .../57-python3-rospkg_1.4.0-100_all.deb ...
Unpacking python3-rospkg (1.4.0-100) over (1.2.3-1) ...
Preparing to unpack .../58-snapd_2.54.3+20.04.1ubuntu0.3_amd64.deb ...
Unpacking snapd (2.54.3+20.04.1ubuntu0.3) over (2.54.3+20.04.1ubuntu0.2) ...
Errors were encountered while processing:
 /tmp/apt-dpkg-install-HRuYld/52-python3-catkin-pkg-modules_0.4.24-1_all.deb
 /tmp/apt-dpkg-install-HRuYld/54-python3-rospkg-modules_1.4.0-1_all.deb
 /tmp/apt-dpkg-install-HRuYld/55-python3-rosdistro-modules_0.8.3-1_all.deb
E: Sub-process /usr/bin/dpkg returned an error code (1)
r2@ifmsrvtsf02:~$

```
Step-1: Remove manually the packages.
Step-2: Run again 
```
dpkg -l | grep ^iU | awk '{print $2}' | xargs sudo dpkg --purge
```
Now able to install.
```
  192  sudo rm -f /usr/lib/python3/dist-packages/catkin_pkg-0.4.24.egg-info
  193  sudo rm -rf /usr/lib/python3/dist-packages/catkin_pkg-0.4.24.egg-info/
  194  sudo rm -rf /usr/lib/python3/dist-packages/rospkg-1.4.0.egg-info
  195  sudo rm -rf /usr/lib/python3/dist-packages/rosdistro-0.8.3.egg-info
  196  sudo rm -rf /usr/lib/python3/dist-packages/rosdep2
  197  sudo apt update && sudo apt upgrade
  198  dpkg -l | grep ^iU | awk '{print $2}' | xargs sudo dpkg --purge
  199  sudo apt update && sudo apt upgrade
  200  sudo apt-get install meld

```

