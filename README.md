# OpenStack Debugging - Setup

For the OpenStack debugging session, you need to install devstack with PyCharm IDE. There are many options but we recommend one of the following:

1. Create a VirtualBox VM from the provided OVA file
2. Create a VM on the local PC/MAC and install devstack & PyCharm manually
3. Use a VM on a cloud
 
## Option 1 - Create a VirtualBox VM from the provided OVA file
This is the recommended way to setup the environment. However, it requires downloading OVA file (around 4GB size) from Internet. If you are having problems downloading this file, consider using Option 2.

### Pre-requisites
* At least 8G of memory
* 20 GB free storage
* VirtualBox installed and configured (If VirtualBox is not installed, get the binaries for PC/MAC from https://www.virtualbox.org/wiki/Downloads and follow the instructions from https://www.virtualbox.org/manual/ch01.html#intro-installing
* Shutdown all VMs, if you have any of them running)

### Step 1 - Download the OVA file
Download the OVA file and save it the local disk. The Link to the OVA file will be provided separately.

### Step 2 - Import OVA file
Follow these steps to import OVA file
* Start VirtualBox
* Click on "File -> Import Appliance"
* Point to the downloaded OVA file
* Accept the default "Appliance settings" and click on "Import"

The above process will install a fully equipped VM, however VM will not be started auotmatically. 
To start the VM, goto VirtualBox and select the new VM from the list. Click on the "Start" button to start the VM.

### Step 3 - Additional configuration
PyCharm uses inotify to monitor directories for changes. By default, ubuntu's inotify limit is set to 8192. For PyCharm debugging to work, we need to set it to a higher value. See https://confluence.jetbrains.com/display/IDEADEV/Inotify+Watches+Limit for more information. Run the following commands:

* find the current limit

 `cat /proc/sys/fs/inotify/max_user_watches`
     
* change the current limit

 `sudo sysctl fs.inotify.max_user_watches=16384`

* permanently change the limit

 `echo 16384 | sudo tee -a /proc/sys/fs/inotify/max_user_watches`

## Option 2 - Install devstack & PyCharm manually
Please see the insructions [http://wiringtheplanet.blogspot.com/2016/09/installing-devstack-and-pycharm-for.html?view=classic] for installing PyCharm and Devstack manually on local PC/MAC.

## Option 3 - Setup a VM on the Cloud
You can setup a VM on any cloud that can provide a public IP address for a VM. Use the instructions from Option 2 to install devstack and PyCharm.



