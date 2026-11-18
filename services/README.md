# Media Services

The media stack runs as rootless Podman containers managed by
systemd user services through Podman Quadlet.

## Architecture

| Service | Container | Host Port | Container Port |
|---|---|---:|---:|
| Jellyfin | jellyfin | 8096 | 8096 |
| Radarr | radarr | 7878 | 7878 |
| Sonarr | sonarr | 8989 | 8989 |
| SABnzbd | sabnzbd | 8081 | 8080 |

Radarr, Sonarr and SABnzbd use the `homelab-media` Podman network.
Jellyfin currently uses the default Podman network.

## Persistent Storage

| Host Path | Container Path | Purpose |
|---|---|---|
| `~/homelab/jellyfin/config` | `/config` | Jellyfin configuration |
| `~/homelab/jellyfin/cache` | `/cache` | Jellyfin cache |
| `~/homelab/radarr/config` | `/config` | Radarr configuration |
| `~/homelab/sonarr/config` | `/config` | Sonarr configuration |
| `~/homelab/usenet/config` | `/config` | SABnzbd configuration |
| `~/homelab/usenet/downloads` | `/downloads` | Shared downloads |
| `~/Movies` | `/movies` or `/media` | Movie library |
| `~/TV` | `/tv` | TV library |

Application configuration and media data are stored outside this repository.
Only deployment definitions and documentation are version-controlled.

## Deployment

Quadlet source files are stored in:

`~/.config/containers/systemd/`

The corresponding repository definitions are in the service directories.

After changing a Quadlet file, copy it to the systemd configuration
directory, reload the user systemd manager and restart the affected service.

Example for Radarr:

```bash
cp services/radarr/radarr.container ~/.config/containers/systemd/
systemctl --user daemon-reload
systemctl --user restart radarr.service
```
```
