Packer Centos template
==============

Packer template to make VirtualBox images.

Notes
-----
CentOS 64-bit VM, 10G disk, EPEL repo, Puppet 4, no SELinux, no firewall,

Packer version: 0.8.6

Usage
=====

Installing Packer
-----------------

Download the latest packer from http://www.packer.io/downloads.html

Prepare var file
----------------------

`cp vars.json.template vars-example.json`

Example var file for CentOS 7.x:

```json
{
  "iso_url": "http://ftp.ps.pl/pub/Linux/CentOS/7/isos/x86_64/CentOS-7-x86_64-Minimal-1611.iso",
  "iso_checksum": "27bd866242ee058b7a5754e83d8ee8403e216b93d130d800852a96f41c34d86a",
  "iso_checksum_type": "sha256",
  "guest_additions_path": "VBoxGuestAdditions.iso",
  "redhat_release": "7.3",
  "disk_size": "15000"
}

```
Example var file for CentOS 6.x:

```json
{
  "iso_url": "http://centos.po.opole.pl/6/isos/x86_64/CentOS-6.9-x86_64-minimal.iso",
  "iso_checksum": "422af57b493b8af49d485885a730c5a1d955f803fac85aa51311c393168b9080",
  "iso_checksum_type": "sha256",
  "guest_additions_path": "VBoxGuestAdditions.iso",
  "redhat_release": "6.9",
  "disk_size": "10000"
}
```

Running Packer
--------------

`$ packer build -var-file=vars-example.json vagrant-centos.json`
