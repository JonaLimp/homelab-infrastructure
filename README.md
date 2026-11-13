
# Homelab Infrastructure

A Fedora-based self-hosted infrastructure project focused on reliability, security, automation, and technical learning.

## Objectives

- Operate a reliable Fedora home server.
- Deploy and manage services using Podman.
- Provide secure remote access through WireGuard.
- Manage infrastructure through version-controlled definitions.
- Automate configuration with Ansible.
- Document architecture, troubleshooting, and operational procedures.

## Infrastructure

| Component | Technology |
|---|---|
| Host OS | Fedora Linux |
| Container Engine | Podman |
| Media Server | Jellyfin |
| Media Management | Radarr, Sonarr |
| Downloads | SABnzbd |
| Remote Access | WireGuard |
| Administration | SSH |
| Version Control | Git |
| Automation | Ansible (planned) |

## Repository Structure

- `services/` – Container and service definitions
- `networking/` – VPN and network configuration
- `system/` – Host configuration and storage
- `automation/` – Infrastructure automation
- `docs/` – Architecture and operational documentation

