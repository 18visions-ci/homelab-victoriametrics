 Homelab VictoriaMetrics

This repository contains an Ansible playbook and roles to install and configure [VictoriaMetrics](https://victoriametrics.com/) on an Ubuntu 22.04 server. It includes tasks for setting up a user, installing the binary, configuring the service, and mounting an NFS share for data storage.

## Features

- Mounts an NFS share from an Unraid NAS for data storage.
- Creates a dedicated `victoriametrics` user.
- Installs the VictoriaMetrics binary from the specified version.
- Configures and starts the VictoriaMetrics systemd service.

## Prerequisites

- Ansible installed on your control machine.
- An Ubuntu 22.04 server with sudo access.
- An NFS share available on your NAS.

## Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/18visions-ci/homelab-victoriametrics.git
   cd homelab-victoriametrics
   ```

2. Update the variables in main.yaml to match your environment:

- nas_server: Your NAS hostname or IP.
- nas_share: The NFS share path on your NAS.
- victoria_metrics_version: The desired version of VictoriaMetrics.

Run the playbook:
```bash
ansible-playbook main.yaml -i <inventory_file>
```
Replace <inventory_file> with the path to your Ansible inventory file.

Variables
The following variables can be customized in main.yaml:

- nas_mount_point: Local mount point for the NFS share.
- nas_server: Hostname or IP of the NAS.
- nas_share: Path to the NFS share on the NAS.
- victoria_metrics_dir: Directory for VictoriaMetrics data.
- victoria_metrics_bin: Path to the VictoriaMetrics binary.
- victoria_metrics_version: Version of VictoriaMetrics to install.
