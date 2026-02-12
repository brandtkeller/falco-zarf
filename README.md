# Falco Zarf Package

This is a very basic Zarf package for Falco with the sidekick and sidekick ui enabled - capable for offline and/or airgapped environments. 

## How to use this Package

[Install Zarf]() for the machine you'll use for package creation and deployment (typically the same machine for a demo)

Deploy a Kubernetes cluster - Kind/K3d will suffice

Run `zarf init` and confirm `y` for downloading the init package and confirm `y` to install the init package into cluster
(Git server is not required for this demo)

Now that we have an initialized cluster - we can create the package. 

From this repository run `zarf package create .` - this will produce a `zarf-package-falco-<arch>-0.42.1.tar.zst` tarball containing all artifacts in the manifest.

Run `zarf package deploy `zarf-package-falco-<arch>-0.42.1.tar.zst` and confirm `y` to deploy the package.

Verify installation with kubectl (zarf tools kubectl) or k9s (zarf tools monitor) 