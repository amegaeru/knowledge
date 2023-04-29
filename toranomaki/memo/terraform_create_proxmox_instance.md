```
terraform {
  required_providers {
    proxmox = {
      source = "Telmate/proxmox"
      version = "2.9.13"
    }
  }
}
provider "proxmox" {
  pm_api_url  = "https://pve:8006/api2/json"
  pm_user     = "terraform-prov@pve"
  pm_password = "amegaeru123"
  pm_tls_insecure = true
  # pm_realm = "pve"
  pm_debug = true
  pm_log_levels = {
    _default    = "debug"
    _capturelog = ""
  }
}
variable "ssh_public_key" {
  default = "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCtUXmSp5y9KiGd191irClS8+vcoXE8aELnatlbrkf2ccuDAMiAHIzrNRRLAb9z5IxD/J1xUwv5jX6GqWJGCZaXAG168V91tZKpdzNtBi20yc1FrzCIZFfaVtp9MmDn9RnF5t7O5VzLkLNHFpFust81m4PE3FNwCW2xmoz6fTE/mAh0rIr/jai8KtvQ4kEKH8gH5JI3FBt2VTv1Kfg8VqV01g3FseCawoXDPAk0E0fWfQwY7icydEFhOpLAP72KBL8edDHWUmGsK3UNmqZ7N9rb/xcUNi67P8QZxae4S1iefHkv4g/XpFU8vxM8eg2BcEBQzcZtKNrtkyCGbKBt/CO3hnGRgAMGi855Gdx1+yXDP2Qd1cNMCqIaILtWOAOQtR21rRdpvWkpMule3iWg0PUaJmrIT04tHKER15a9k54BLlQtQw4zXOMlJ1G3nOphNIz5mZCaNjWgNlRfdCrdOhrEtPVaYrO9k8eqx3Ouy23sk2S0jSVem/HLI8OyJpJDkWU= root@localhost.localdomain"
}
resource "proxmox_vm_qemu" "kubernetes" {
  count = 5
  name = "kube-${count.index+1}"
  target_node = "pve"
  memory = "4096"
  os_type = "cloud-init"
  cores = "2"
  clone = "Template-Racky8.6"
  scsihw = "virtio-scsi-single"
  ipconfig0 = "ip=192.168.10.${count.index+1+120}/24"
  sshkeys = var.ssh_public_key

  disk {
    storage = "local-lvm"
    size = "40G"
    type = "scsi"
    iothread = 0
  }
}
```

