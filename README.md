<div align="center">

<img src="snap/gui/openidea.png" alt="OpenIDEA logo" width="128" />

# OpenIDEA

**Edit code, manage projects and connect to remote development environments.**

[![openidea](https://snapcraft.io/openidea/badge.svg)](https://snapcraft.io/openidea)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64, arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [OpenIDEA](https://github.com/l0ng-ai/openidea), a desktop IDE with code intelligence, Git, a terminal and remote development. OpenIDEA is not affiliated with JetBrains.

</div>

---

## Getting Started

<a href="https://snapcraft.io/openidea"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install openidea
openidea
```

Open a project under your home directory, for example `~/Projects/my-app`.

## Configure

Use the application's settings. Settings, credentials and downloaded tools stay inside `~/snap/openidea/current`; there are no `snap set` options.

Language servers and SDKs can be installed through the application's tool settings where supported. Tools requiring an additional runtime, such as Node or Python, need a compatible runtime inside the snap's writable directories.

For projects on removable storage:

```bash
sudo snap connect openidea:removable-media
```

## Limitations

- The terminal and project commands remain confined. Host SDKs, coding agents, global Git/SSH configuration and top-level hidden home directories are not automatically accessible. Configure credentials inside the application.
- Docker integration and attaching a debugger to host processes are unavailable. Downloaded tools must also work under confinement; availability varies by architecture.
- Desktop updates come through `snap refresh openidea`. Language-tool and plugin installation remain available.

## Build

```bash
git clone https://github.com/sidalit/openidea-snap.git
cd openidea-snap
sudo snap install snapcraft --classic
snapcraft pack
```

```bash
sudo snap install --dangerous ./openidea_*.snap
openidea
```

The single-instance D-Bus slot may require Snap Store approval before publication.

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/openidea-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/l0ng-ai/openidea/issues).

## License

Snap packaging: [MIT](LICENSE).
