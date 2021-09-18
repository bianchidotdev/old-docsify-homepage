Bare Metal Kubernetes Setup
=============

!> This is an incomplete guide. It may or may not ever be finished. Check out [private_cloud](private_cloud/index.md) for a complete guide.

## What this is
This is one of many ways to set up kubernetes at home. 

It contains certain components:
- Example OS setup
- External Networking
- HTTPS for the cluster
- K3s Setup for multiple nodes

We'll show the setup of a varied server ecosystem

## Prereqs
Hardware:
- 1, 3, or more servers
  - Raspberry Pi
  - Old desktop or laptop
  - Rackmount server
  - Cloud instances
  - VM on any of the above

Software (on your development machine):
- [`kubectl`](https://kubernetes.io/docs/tasks/tools/)
- [`k3sup`](https://github.com/alexellis/k3sup) - "ketchup"

### Mac Install Instructions

```bash
brew install kubernetes-cli
brew install k3sup
```