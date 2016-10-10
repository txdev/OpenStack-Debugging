# OpenStack Debugging - Setup

For the OpenStack debugging session, you need to install devstack with PyCharm IDE. There are many options but we recommend one of the following:

1. Create a VirtualBox VM from the provided OVA file
2. Create a VM on the local PC/MAC and install devstack & PyCharm manually
3. Use a VM on a cloud

Option 1 is the easiest and can be setup on PC/MAC. All you have to do is install VirtualBox and then import the OVA file. This will create a VM that has everything you need - Ubuntu 14.04, Devstack, PyCharm and Debug configuration.

If you are having issues downloading the huge OVA file, consider installing from scratch. Please instructions [here](http://wiringtheplanet.blogspot.com/2016/09/installing-devstack-and-pycharm-for.html?view=classic).

The final option is using a VM on a cloud such as AWS, GCE or any public cloud.

## Create a devstack VM from OVA file
Start VirtualBox and import the OVA file. Please follow these steps:

1. Login to the VM using the provided username/password.
2. Open Terminal application
3. Change to devstack directory (cd devstack)
4. Run the following commands to bring volumes online
  1. sudo losetup -f /opt/stack/data/stack-volumes-default-backing-file
  2. sudo losetup -f /opt/stack/data/stack-volumes-lvmdriver-1-backing-file
5. run rejoin.sh


