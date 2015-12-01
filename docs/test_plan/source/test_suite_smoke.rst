=====
Smoke
=====


Install Fuel VMware DVS plugin.
-------------------------------


ID
##

dvs_install


Description
###########

Check that plugin can be installed.


Complexity
##########

smoke


Steps
#####

    1. Connect to fuel node via ssh.
    2. Upload plugin.
    3. Install plugin.


Expected result
###############

Ensure that plugin is installed successfully using cli, run command 'fuel plugins'. Check name, version and package version of plugin.


Uninstall Fuel VMware DVS plugin.
---------------------------------


ID
##

dvs_uninstall


Description
###########

Check that plugin can be removed.


Complexity
##########

smoke


Steps
#####

    1. Connect to fuel node with preinstalled plugin via ssh.
    2. Remove plugin.


Expected result
###############

Verify that plugin is removed, run command 'fuel plugins'.


Verify that all elements of DVS plugin section meets the requirements.
----------------------------------------------------------------------


ID
##

dvs_gui


Description
###########

Verify that all elements of DVS plugin section meets the requirements.


Complexity
##########

smoke


Steps
#####

    1. Connect to a Fuel web UI with preinstalled plugin.
    2. Create a new environment with following parameters:
        * Compute: KVM/QEMU with vCenter
        * Networking: Neutron with VLAN segmentation
        * Storage: default
        * Additional services: default
    3. Click on the Settings tab and check that section of  DVS  plugin is displayed with all required GUI elements.
    4. Verify that section of DVS plugin is present on the Settings tab.
    5. Verify that check box "Use Neutron VMware DVS ML2 plugin" is enabled by default.
    6. Verify that user can disabled -> enabled DVS plugin by click on check box "Use Neutron VMware DVS ML2 plugin".
    7. Verify that check box "Use VMware DVS ML2 plugin for networking" is enabled by default.
    8. Verify that all labels of DVS plugin section have same font style and color.
    9. Verify that all elements of DVS plugin section are vertical aligned.


Expected result
###############

All elements of DVS plugin section meets the requirements.


Deployment with plugin, controller and vmware datastore backend.
----------------------------------------------------------------


ID
##

dvs_vcenter_smoke


Description
###########

Check deployment with VMware DVS plugin and one controller.


Complexity
##########

smoke


Steps
#####

    1. Connect to a Fuel web UI with preinstalled plugin.
    2. Create a new environment with following parameters:
        * Compute: KVM/QEMU with vCenter
        * Networking: Neutron with VLAN segmentation
        * Storage: default
        * Additional services: default
    3. Add nodes with following roles:
        * Controller
    4. Configure interfaces on nodes.
    5. Configure network settings.
    6. Enable and configure DVS plugin.
    7. Configure settings:
        * Enable VMWare vCenter/ESXi datastore for images (Glance).
    8. Configure VMware vCenter Settings. Add 1 vSphere clusters and configure Nova Compute instances on conrollers.
    9. Deploy cluster.
    10. Run OSTF.


Expected result
###############

Cluster should be deployed and all OSTF test cases should be passed.


Deploy cluster with plugin and ceph datastore backend.
------------------------------------------------------


ID
##

dvs_vcenter_bvt


Description
###########

Check deployment with VMware DVS plugin, 3 Controllers, Compute, 2 CephOSD, CinderVMware and computeVMware roles.


Complexity
##########

smoke


Steps
#####

    1. Connect to a Fuel web UI with preinstalled plugin.
    2. Create a new environment with following parameters:
        * Compute: KVM/QEMU with vCenter
        * Networking: Neutron with VLAN segmentation
        * Storage: Ceph
        * Additional services: default
    3. Add nodes with following roles:
        * Controller
        * Controller
        * Controller
        * Compute
        * CephOSD
        * CephOSD
        * CinderVMware
        * ComputeVMware
    4. Configure interfaces on nodes.
    5. Configure network settings.
    6. Enable and configure DVS plugin.
    7. Configure VMware vCenter Settings. Add 2 vSphere clusters and configure Nova Compute instances on conrollers and compute-vmware.
    8. Verify networks.
    9. Deploy cluster.
    10. Run OSTF.


Expected result
###############

Cluster should be deployed and all OSTF test cases should be passed.
