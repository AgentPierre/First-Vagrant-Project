# First-Vagrant-Project

A hands-on DevOps learning project: **Building a reproducible development environment using Vagrant and VirtualBox.**

## Overview

This project demonstrates a core DevOps principle: **environment parity**. The Vagrantfile configures a development environment that mirrors production, eliminating the "it works on my machine" problem.

## What You Get

✅ **Ubuntu 22.04 LTS** — matches production  
✅ **2 CPU cores + 2GB RAM** — realistic workload capacity  
✅ **Port forwarding** — access services at `localhost:8000`  
✅ **Shared folders** — live code sync between Windows and VM  
✅ **Reproducible setup** — one command for everyone on the team  

## Prerequisites

- **VirtualBox** — Download from https://www.virtualbox.org/wiki/Downloads
- **Vagrant** — Download from https://www.vagrantup.com/downloads
- **Git** — For cloning this repo

## Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/AgentPierre/First-Vagrant-Project.git
cd First-Vagrant-Project
```

### 2. Start the VM
```bash
vagrant up
```

This downloads the Ubuntu 22.04 box and boots the VM. First run takes 2-5 minutes.

### 3. SSH into the VM
```bash
vagrant ssh
```

You're now inside Ubuntu. Your project files are at `/vagrant`.

### 4. Verify the setup
Inside the VM:
```bash
# Check CPU cores
nproc

# Check available memory
free -h

# Navigate to shared folder
cd /vagrant
ls -la
```

## Common Commands

```bash
vagrant up        # Start the VM
vagrant ssh       # Connect via SSH
vagrant halt      # Pause the VM
vagrant destroy   # Delete the VM (recreate with vagrant up)
vagrant status    # Check VM status
```

## Vagrantfile Breakdown

- **Box:** `ubuntu/jammy64` — Ubuntu 22.04 LTS, 64-bit
- **Memory:** 2048 MB (2 GB)
- **CPUs:** 2 cores
- **Port Forwarding:** Guest 8000 → Host 8000 (for web apps)
- **Shared Folder:** Current directory synced to `/vagrant` in VM

## Learning Notes

This project was built while completing Ben Lambert's Cloud Academy course. Key learnings:

- **Environment parity matters** — Dev and production should match to prevent environment-specific bugs
- **Timeouts are infrastructure constraints** — Vagrant's boot timeout isn't just about OS startup; it's about SSH communication
- **Configuration as code** — One Vagrantfile = identical setup for everyone
- **Interactive learning** — This Vagrantfile was designed through prompt-engineered Claude guides

## Next Steps

- Add Ansible provisioning to automate software installation
- Integrate with CI/CD pipeline
- Explore Terraform for IaC at scale

## Resources

- [Vagrant Documentation](https://www.vagrantup.com/docs)
- [VirtualBox Manual](https://www.virtualbox.org/manual/)
- Ben Lambert's Cloud Academy Course

## License

This project is for learning purposes.
