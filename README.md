# Ingress NGINX Controller (Facets.cloud Fork)

## About This Fork

This is a community-maintained fork of [kubernetes/ingress-nginx](https://github.com/kubernetes/ingress-nginx), created to provide continued security maintenance beyond the upstream project's retirement in March 2026.

### Why This Fork?

The upstream Kubernetes ingress-nginx project announced [retirement](https://www.kubernetes.io/blog/2025/11/11/ingress-nginx-retirement/) with best-effort maintenance ending in March 2026. Several organizations using ingress-nginx will need a longer window to complete their migration to alternatives like Gateway API.

This fork aims to:
- **Extend the maintenance window** until January 1st, 2027
- **Provide security fixes** for critical and high-severity CVEs
- **Maintain compatibility** with supported Kubernetes versions

---

# Ingress NGINX Controller

[![GitHub license](https://img.shields.io/github/license/Facets-cloud/ingress-nginx.svg)](https://github.com/Facets-cloud/ingress-nginx/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/Facets-cloud/ingress-nginx.svg)](https://github.com/Facets-cloud/ingress-nginx/stargazers)

## Overview

ingress-nginx is an Ingress controller for Kubernetes using [NGINX](https://www.nginx.org/) as a reverse proxy and load balancer.

[Learn more about Ingress on the Kubernetes documentation site](https://kubernetes.io/docs/concepts/services-networking/ingress/).

## Usage Recommendations

For new projects, consider using [Gateway API](https://gateway-api.sigs.k8s.io/guides/) implementations as they represent the future of Kubernetes ingress. This fork is intended for organizations with existing ingress-nginx deployments who need additional time to migrate.

Do not use in multi-tenant Kubernetes production installations. This project assumes that users that can create Ingress objects are administrators of the cluster. See the [FAQ](https://kubernetes.github.io/ingress-nginx/faq/#faq) for more.

## Troubleshooting

If you encounter issues, review the [troubleshooting docs](docs/troubleshooting.md) or [search for an issue](https://github.com/Facets-cloud/ingress-nginx/issues). You can also check the [upstream issues](https://github.com/kubernetes/ingress-nginx/issues) for historical context.

## Changelog

See [this fork's releases](https://github.com/Facets-cloud/ingress-nginx/releases) for changes made in this fork. For historical changes, see the [upstream releases](https://github.com/kubernetes/ingress-nginx/releases).

For detailed changes for each release, check the [changelog](./changelog) folder.

### Supported Versions table

Supported versions for the ingress-nginx project mean that we have completed E2E tests, and they are passing for
the versions listed. Ingress-Nginx versions **may** work on older versions, but the project does not make that guarantee.

| Supported | Ingress-NGINX version | k8s supported version         | Alpine Version | Nginx Version | Helm Chart Version |
| :-------: | --------------------- | ----------------------------- | -------------- | ------------- | ------------------ |
|    🔄     | **v1.14.1**           | 1.34, 1.33, 1.32, 1.31, 1.30  | 3.22.2         | 1.27.1        | 4.14.1             |
|    🔄     | **v1.14.0**           | 1.34, 1.33, 1.32, 1.31, 1.30  | 3.22.2         | 1.27.1        | 4.14.0             |
|    🔄     | **v1.13.5**           | 1.33, 1.32, 1.31, 1.30, 1.29  | 3.22.2         | 1.27.1        | 4.13.5             |
|    🔄     | **v1.13.4**           | 1.33, 1.32, 1.31, 1.30, 1.29  | 3.22.2         | 1.27.1        | 4.13.4             |
|    🔄     | **v1.13.3**           | 1.33, 1.32, 1.31, 1.30, 1.29  | 3.22.1         | 1.27.1        | 4.13.3             |
|    🔄     | **v1.13.2**           | 1.33, 1.32, 1.31, 1.30, 1.29  | 3.22.1         | 1.27.1        | 4.13.2             |
|    🔄     | **v1.13.1**           | 1.33, 1.32, 1.31, 1.30, 1.29  | 3.22.1         | 1.27.1        | 4.13.1             |
|    🔄     | **v1.13.0**           | 1.33, 1.32, 1.31, 1.30, 1.29  | 3.22.0         | 1.27.1        | 4.13.0             |
|           | v1.12.8               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.22.2         | 1.25.5        | 4.12.8             |
|           | v1.12.7               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.22.1         | 1.25.5        | 4.12.7             |
|           | v1.12.6               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.22.1         | 1.25.5        | 4.12.6             |
|           | v1.12.5               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.22.1         | 1.25.5        | 4.12.5             |
|           | v1.12.4               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.22.0         | 1.25.5        | 4.12.4             |
|           | v1.12.3               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.21.3         | 1.25.5        | 4.12.3             |
|           | v1.12.2               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.21.3         | 1.25.5        | 4.12.2             |
|           | v1.12.1               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.21.3         | 1.25.5        | 4.12.1             |
|           | v1.12.0               | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.21.0         | 1.25.5        | 4.12.0             |
|           | v1.12.0-beta.0        | 1.32, 1.31, 1.30, 1.29, 1.28  | 3.20.3         | 1.25.5        | 4.12.0-beta.0      |
|           | v1.11.8               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.22.0         | 1.25.5        | 4.11.8             |
|           | v1.11.7               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.21.3         | 1.25.5        | 4.11.7             |
|           | v1.11.6               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.21.3         | 1.25.5        | 4.11.6             |
|           | v1.11.5               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.21.3         | 1.25.5        | 4.11.5             |
|           | v1.11.4               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.21.0         | 1.25.5        | 4.11.4             |
|           | v1.11.3               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.3         | 1.25.5        | 4.11.3             |
|           | v1.11.2               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.0         | 1.25.5        | 4.11.2             |
|           | v1.11.1               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.0         | 1.25.5        | 4.11.1             |
|           | v1.11.0               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.0         | 1.25.5        | 4.11.0             |
|           | v1.10.6               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.21.0         | 1.25.5        | 4.10.6             |
|           | v1.10.5               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.3         | 1.25.5        | 4.10.5             |
|           | v1.10.4               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.0         | 1.25.5        | 4.10.4             |
|           | v1.10.3               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.0         | 1.25.5        | 4.10.3             |
|           | v1.10.2               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.20.0         | 1.25.5        | 4.10.2             |
|           | v1.10.1               | 1.30, 1.29, 1.28, 1.27, 1.26  | 3.19.1         | 1.25.3        | 4.10.1             |
|           | v1.10.0               | 1.29, 1.28, 1.27, 1.26        | 3.19.1         | 1.25.3        | 4.10.0             |
|           | v1.9.6                | 1.29, 1.28, 1.27, 1.26, 1.25  | 3.19.0         | 1.21.6        | 4.9.1              |
|           | v1.9.5                | 1.28, 1.27, 1.26, 1.25        | 3.18.4         | 1.21.6        | 4.9.0              |
|           | v1.9.4                | 1.28, 1.27, 1.26, 1.25        | 3.18.4         | 1.21.6        | 4.8.3              |
|           | v1.9.3                | 1.28, 1.27, 1.26, 1.25        | 3.18.4         | 1.21.6        | 4.8.*              |
|           | v1.9.1                | 1.28, 1.27, 1.26, 1.25        | 3.18.4         | 1.21.6        | 4.8.*              |
|           | v1.9.0                | 1.28, 1.27, 1.26, 1.25        | 3.18.2         | 1.21.6        | 4.8.*              |
|           | v1.8.4                | 1.27, 1.26, 1.25, 1.24        | 3.18.2         | 1.21.6        | 4.7.*              |
|           | v1.7.1                | 1.27, 1.26, 1.25, 1.24        | 3.17.2         | 1.21.6        | 4.6.*              |
|           | v1.6.4                | 1.26, 1.25, 1.24, 1.23        | 3.17.0         | 1.21.6        | 4.5.*              |
|           | v1.5.1                | 1.25, 1.24, 1.23              | 3.16.2         | 1.21.6        | 4.4.*              |
|           | v1.4.0                | 1.25, 1.24, 1.23, 1.22        | 3.16.2         | 1.19.10†      | 4.3.0              |
|           | v1.3.1                | 1.24, 1.23, 1.22, 1.21, 1.20  | 3.16.2         | 1.19.10†      | 4.2.5              |

See [Updating NGINX-Ingress to use the stable Ingress API (July 26, 2021)](https://kubernetes.io/blog/2021/07/26/update-with-ingress-nginx/)
to upgrade to the stable Ingress API before upgrading to Kubernetes 1.22.

## Get Involved

Thanks for taking the time to join our community and start contributing!

- **Contributing**: Contributions are welcome, especially security fixes and Kubernetes compatibility updates.
  - Read [`CONTRIBUTING.md`](CONTRIBUTING.md) for information about the workflow.
  - Submit [GitHub issues](https://github.com/Facets-cloud/ingress-nginx/issues) for bugs or security concerns.

- **Support**:
  - Open an issue in [this repository](https://github.com/Facets-cloud/ingress-nginx/issues) for questions specific to this fork.
  - For general ingress-nginx questions, the [Kubernetes Slack #ingress-nginx-users](https://kubernetes.slack.com/messages/CANQGM8BA/) channel may still be helpful.

## License

[Apache License 2.0](LICENSE)
