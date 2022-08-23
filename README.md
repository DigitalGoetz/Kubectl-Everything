# Kubectl Everything

This little Kubectl plugin (Bash script, really) is intended to give a fairly easy means of checking for the items returned by the "Kubectl get all" command, but also include some of the items that are omitted (perhaps it should really be "kubectl get some"?)

The items currently listed when the plugin is run presently includes everything in the requested namespace/context pair (including some non-namespace scoped resources... those are just currently in my list of things I check when integrating/diagnosing issues; feel free to augment the script!)  The current lineup includes:

  * Pods
  * Deployments
  * Services
  * ConfigMaps
  * Secrets
  * StatefulSets
  * DaemonSets
  * Roles
  * RoleBindings
  * Custom Resource Definitions
  * Events
  * PersistentVolumes
  * PersistentVolumeClaims
  * ReplicaSets

## Installation

Take the script file from this repo, ensure that it can be executed and place it somewhere visible to your PATH environment variable.

For example:

```bash
git clone git@github.com:DigitalGoetz/kubectl-everything.git
cd kubectl-everything
chmod +x kubectl-everything
sudo cp kubectl-everything /usr/local/bin/
```

## Usage

```bash
kubectl everything [options]

The following options are available:
-n, --namespace <value>: Sets the Namespace to query for all resources
-c, --context <value>: Sets the Context to query for all resources
-h, --help: Presents Usage details for this plugin

Example:
    # Presents all resources from the current context's 'applications' namespace
    kubectl everything -n applications 

    # Presents all resources from the 'dev' context's 'sandbox' namespace
    kubectl everything --context dev -namespace sandbox
```