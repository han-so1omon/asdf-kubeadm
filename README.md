# asdf-kubeadm

[![Build Status](https://travis-ci.org/TheCubicleJockey/asdf-kubeadm.svg?branch=master)](https://travis-ci.org/TheCubicleJockey/asdf-kubeadm)

kubeadm plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Install

```
asdf plugin-add kubeadm https://github.com/TheCubicleJockey/asdf-kubeadm.git
```

## Use

Check out the [asdf documentation](https://asdf-vm.com/#/core-manage-versions?id=install-version) for instructions on how to install and manage versions of kubeadm.

## Architecture Override
The `ASDF_KUBEADM_OVERWRITE_ARCH` variable can be used to override the architecture that is used for determining which `kubeadm` build to download. The primary use case is when attempting to install an older version of `kubeadm` for use on an Apple M1 computer as `kubeadm` was not built for ARM at the time.

### Without `ASDF_KUBEADM_OVERWRITE_ARCH`:

```
% asdf install kubeadm 1.24.3
Downloading kubeadm from https://storage.googleapis.com/kubernetes-release/release/v1.18.17/bin/darwin/arm64/kubeadm
```

### With `ASDF_KUBEADM_OVERWRITE_ARCH`:

```
% ASDF_KUBEADM_OVERWRITE_ARCH=amd64 asdf install kubeadm 1.18.17
Downloading kubeadm from https://storage.googleapis.com/kubernetes-release/release/v1.18.17/bin/darwin/amd64/kubeadm
```

