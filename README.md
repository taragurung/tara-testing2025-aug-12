<img src="https://helm.sh/img/helm.svg" width="100px" height="100px">

# OpenCloud Helm Chart

A Helm chart for deploying OpenCloud on Kubernetes.

## 📑 Table of Contents

- [About](#about)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Upgrading](#upgrading)
- [Uninstalling](#uninstalling)
- [License](#license)

## About

This chart deploys OpenCloud as a single container in your Kubernetes cluster.  
It is intended for development and testing purposes.

## Prerequisites

- Kubernetes 1.19+
- Helm 3.2.0+

## Installation

Add your Helm repository and install the chart:

```sh
helm install opencloud . \
  --namespace opencloud \
  --create-namespace
```

Or, if using a published chart:

```sh
helm repo add opencloud https://your.repo.url/
helm install opencloud opencloud/opencloud \
  --namespace opencloud \
  --create-namespace
```

## Configuration

You can configure the chart using the `values.yaml` file or by setting parameters with `--set`.

Some commonly used parameters:

| Parameter                  | Description                                 | Default                    |
|----------------------------|---------------------------------------------|----------------------------|
| `opencloud.domain`         | Hostname for the ingress                    | `cloud.opencloud.test`     |
| `image.registry`           | Image registry                              | `docker.io`                |
| `image.repository`         | Image repository                            | `opencloudeu/opencloud-rolling` |
| `image.tag`                | Image tag                                   | `"2.1.0"`                  |
| `ingress.enabled`          | Enable ingress controller resource          | `true`                     |
| `resources`                | Resource requests and limits                | `{}`                       |

Override values using `--set`:

```sh
helm install opencloud . \
  --namespace opencloud \
  --set image.tag="2.2.0" \
  --set opencloud.domain="mycloud.example.com"
```

## Upgrading

To upgrade the release:

```sh
helm upgrade opencloud . -n opencloud
```

## Uninstalling

To uninstall the release:

```sh
helm uninstall opencloud -n opencloud
```

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.