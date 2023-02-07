Below are instructions on how to install a Run:ai cluster. Before installing, please review the installation prerequisites here: [Run:ai GPU Cluster Prerequisites](cluster-prerequisites.md). 


!!! Important
    We strongly recommend running the Run:ai [pre-install script](cluster-prerequisites.md) to verify that all prerequisites are met. 

## Install Run:ai

Log in to Run:ai user interface at `<company-name>.run.ai`. Use credentials provided by Run:ai Customer Support:

*   If no clusters are currently configured, you will see a Cluster installation wizard
*   If a cluster has already been configured, use the menu on the top left and select "Clusters". On the top right, click "Add New Cluster". 

Using the Wizard:

1. Choose a target Kubernetes platform (see table above)
2. (SaaS only) Provide a domain name for your cluster as described [here](./cluster-prerequisites.md#cluster-url).
3. (SaaS only) Install a trusted certificate to the domain within Kubernetes. 
4. Download a _Helm_ values YAML file ``runai-<cluster-name>.yaml``
5. (Optional) customize the values file. See [Customize Cluster Installation](customize-cluster-install.md)
6. Install [Helm](https://helm.sh/docs/intro/install/)
7. For RKE only, perform the steps [here](./customize-cluster-install.md#rke-specific-setup)
8. Run the `helm` commands as provided in the wizard. 

!!! Info
    To install a specific version, add `--version <version>` to the install command.

## Verify your Installation

*   Go to `<company-name>.run.ai/dashboards/now`.
*   Verify that the number of GPUs on the top right reflects your GPU resources on your cluster and the list of machines with GPU resources appears on the bottom line.

For a more extensive verification of cluster health, see [Determining the health of a cluster](../../troubleshooting/cluster-health-check.md).

## Researcher Authentication

You must now set up [Researcher Access Control](../authentication/researcher-authentication.md). 

## (Optional) Set Node Roles

When installing a production cluster you may want to:

* Set one or more Run:ai system nodes. These are nodes dedicated to Run:ai software. 
* Machine learning frequently requires jobs that require CPU but __not GPU__. You may want to direct these jobs to dedicated nodes that do not have GPUs, so as not to overload these machines. 
* Limit Run:ai to specific nodes in the cluster. 

To perform these tasks. See [Set Node Roles](../config/node-roles.md).

## Next Steps

* Set up Run:ai Users [Working with Users](../../admin-ui-setup/admin-ui-users.md).
* Set up Projects for Researchers [Working with Projects](../../admin-ui-setup/project-setup.md).
* Set up Researchers to work with the Run:ai Command-line interface (CLI). See  [Installing the Run:ai Command-line Interface](../../researcher-setup/cli-install.md) on how to install the CLI for users.
* Review [advanced setup and maintenance](../config/overview.md) scenarios.
