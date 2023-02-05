# Setting up Homelab using Harvester HCI
 
So I've set up my home lab using Harvester HCI and I've some set of images. 
I will try to automate some of the steps I take using ansible or terraform(if needed) for future use


## Images
- [TrueNAS](https://download.truenas.com/TrueNAS-SCALE-Bluefin/22.12.0/TrueNAS-SCALE-22.12.0.iso)
- [Ubuntu Server 22.04](https://releases.ubuntu.com/22.04.1/ubuntu-22.04.1-live-server-amd64.iso)
- [pfSense-CE-2.6.0-RELEASE-amd64](https://atxfiles.netgate.com/mirror/downloads/pfSense-CE-2.6.0-RELEASE-amd64.iso.gz)


## setting first VM
I have set up an ubuntu VM with the following specs
Template: harvester-public/iso-image-base-template
CPU: 2
Memory: 4GiB
Volumes:
    - Image volume
        - type: cd-rom
        - size: 10GB
        - image: ubuntu

    - Volume
        - type: disk
        - size: 50GB

The image volume is used to act as a bootable drive to install the OS for the first time. you can eject this volume once its been used.


## Setting up pfsense
---
pfsense is basically a router and firewall in a software

