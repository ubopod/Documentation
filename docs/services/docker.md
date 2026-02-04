# Docker

**Services**  
Docker

![Docker](assets/images/services/docker.png)

*Image: Docker apps (placeholder).*

The **Docker** service manages the Docker daemon (install, start, stop via system manager) and containerized apps: images, containers, run/stop, and registry credentials. The Apps menu and Docker settings use this state.

## What you see

- **State** (`DockerState`) — `DockerServiceState` (install/run status), images list (`ImageState`: name, status, docker id, metadata), registry usernames.
- **Actions** — `DockerInstallAction`, `DockerStartAction`, `DockerStopAction`, `DockerSetStatusAction`, `DockerStoreUsernameAction`, `DockerRemoveUsernameAction`; per-image: `DockerImageFetchAction`, `DockerImageRunAction`, `DockerImageStopAction`, `DockerImageRemoveAction`, etc.
- **Implementation** — `ubo_app/services/080-docker/`: docker_app, docker_composition, docker_container, docker_image, docker_images, menus, reducer, setup, ubo_handle; assets include Envoy template. System manager performs Docker install/start/stop.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Apps](../home/apps.md)
- [Home → Settings → Docker](../home/settings/docker.md)
- [Home → Settings → Docker → Service](../home/settings/docker-service.md)
