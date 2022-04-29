# vSRX
Virtual Juniper SRX firewall

Prepare modular firewall Juniper SRX5k in virtual environment, so need to map the functionality of the SRX5k in servers x86_64 with virtual SRX software.
RE SRX5k - control plane vSRX3
SPC SRX5k - data plane vSRX3
IOC SRX5k - interfaces: managment, zone Internet, zone trust
routers - DC gateways, L3VPN per zone, BGP routing and auto-FBF ECMP load balancing (consistent-hash source-IP [trust], destination-IP [Internet])

# server x86_64 - baremetal + linux kernel kvm/vhost-net/iSCSI/NVMe + cloud-init + KVM/libviert/qemu + k8s/kubevirt
Infrastructure
VM: ansible-control-node - module junos_netconf, LCM of the SRX config, SRX CLI commands 

initial config: set fxp0 dhcp, set root password, set user netconfig

Download vSRX3 from https://support.juniper.net/support/downloads/?p=vsrx3

junos-vsrx3-x86-64-22.1R1.10.qcow2
junos-vsrx3-x86-64-22.1R1.10.scsi.ova

https://www.xmodulo.com/convert-ova-to-qcow2-linux.html

