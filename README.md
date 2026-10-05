# VMware-Golden-Templates
This guide walks you through creating a golden template for VMware and using it for automated deployment
Architecture 
CentOS Stream 9 ISO
        │
        ▼
    Base VM
        │
        ├── VMware Tools / open-vm-tools
        ├── cloud-init
        ├── NetworkManager
        ├── SSH
        ├── updates
        └── cleanup cloud-init state
        │
        ▼
    VMware Template
        │
        │ OpenTofu clone
        ▼
    New VM
        │
        ├── hostname
        ├── IP / prefix
        ├── gateway
        ├── DNS
        ├── SSH keys
        ├── users
        └── packages/config

| Components       | Configuration                     |
| ---------------- | --------------------------------- |
| OS               | CentOS Stream 9                   |
| Firmware         | BIOS або EFI                      |
| Disk             | 30–40 GB thin                     |
| SCSI             | VMware Paravirtual                |
| NIC              | VMXNET3                           |
| Network          | DHCP during configure template    |
| SSH              | enabled                           |
| `open-vm-tools`  | installed                         |
| `cloud-init`     | installed                         |
| NetworkManager   | enabled                           |
| SELinux          | Enforcing                         |
| firewalld        | enabled                           |
| hostname         | temporary                         |
| static IP        | ** empty **                       |
| SSH host keys    | delete before template            |
| machine-id       | to clean                          |
| cloud-init state | to clean                          |
| swap             | if need                           |
| packages         | only basic                        |
| user             | create through cloud-init         |
