# Run:ai version 2.13

## Release content

### Dashboards
<!-- RUN9530/9577 New Dashboard for Quota management -->
* Added a new dashboard for **Quota management**, which provides an efficient means to monitor and manage resource utilization within the AI cluster. The dashboard filters the display of resource quotas based on *Departments*, *Projects*, and *Node pools*. For more information, see [Quota management dashboard](../admin/admin-ui-setup/dashboard-analysis.md#quota-management-dashboard).

* Added to the **Overview dashboard**, the ability to filter the cluster by one or more node pools. For more information, see [Node pools](../Researcher/scheduling/using-node-pools.md).

### Node pools

* Added per node pool over-quota priority. Over-quota priority sets the relative amount of additional unused resources that an asset can get above its current quota. For more information, see [Over-quota priority](../Researcher/scheduling/the-runai-scheduler.md#over-quota-priority).

<!-- RUN-9960/9961 Per node-pool GPU placement strategy -->
* Run:ai scheduler supports 2 scheduling strategies: Bin Packing (default) and Spread. For more information, see [Scheduling strategies](../Researcher/scheduling/strategies.md). You can configure the scheduling strategy in the node pool level to improve the support of clusters with mixed types of resources and workloads. For configuration information, see [Creating new node pools](../Researcher/scheduling/using-node-pools.md#creating-new-node-pools).

* Added Node pool selection as part of the workload submission form. This allows researchers to quickly determine the list of node pools available and their priority. Priority is set by dragging and dropping them in the desired order of priority. In addition, when the node pool priority list is locked by a policy, the list isn't editable by the Researcher even if the workspace is created from a template or copied from another workspace.

### PVC data sources
<!-- RUN-9826/10186 Support PVC from block storage -->
* Added support for PVC block storage in the *New data source* form. In the *New data source* form for a new PVC data source, in the *Volume mode* field, select from *Filesystem* or *Block*. For more information, see [Create a PVC data source](../Researcher/user-interface/workspaces/create/create-ds.md#create-a-pvc-data-source).

<!-- RUN-8904/8960 - Cluster wide PVC in workspaces -->
* Added support for making a PVC data source available to all projects. In the *New data source* form, when creating a new PVC data source, select *All* from the *Project* pane.

### Metrics

* GPU device level DCGM Metrics are collected per GPU and presented by Run:ai in the Nodes table. Each node contains a list of its embedded GPUs with their respective DCGM metrics. See [DCGM Metrics](https://docs.nvidia.com/datacenter/dcgm/latest/user-guide/feature-overview.html#metrics){target=_blank} for the list of metrics which are provided by NVidia DCGM and collected by Run:ai. Contact your Run:ai customer representative to enable this feature.

### Projects
<!-- RUN-9312/9313 Projects V2 -->
* Improved the **Projects** UI for ease of use. **Projects** follows UI upgrades and changes that are designed to make setting up of components and assets easier for administrators and researchers. To configure a project, see [Projects](../admin/admin-ui-setup/project-setup.md).

### Workspaces

<!-- RUN-9359/9360 Incorporating Node Pools in Workspaces -->
* Added support of associating workspaces to node pool.
The association between workspaces and node pools is done using *Compute resources* section. In order to associate a compute resource to a node pool, in the *Compute resource* section, press *More settings*. Press *Add new* to add more node pools to the configuration. Drag and drop the node pools to set their priority.

### Time limit duration

* Improved the behavior of any workload time limit (for example, *Idle time limit*) so that the time limit will affect existing workloads that were created before the time limit was configured. This is an optional feature which provides help in handling situations where researchers leave sessions open even when they do not need to access the resources. For more information, see [Limit duration of interactive training jobs](../admin/admin-ui-setup/project-setup.md#limit-duration-of-interactive-and-training-jobs).

* Improved workspaces time limits. Workspaces that reach a time limit will now transition to a state of `stopped` so that they can be reactivated later.

* Added time limits for training jobs per project. Administrators (Department Admin, Editor) can limit the duration of Run:ai Training jobs per Project using a specified time limit value. This capability can assist administrators to limit the duration and resources consumed over time by training jobs in specific projects. Each training job that reaches this duration will be terminated.

### Workload assets

<!-- RUN-8862/9292 - Department as a workspace asset creation scope - phase 1 -->
* Extended the collaboration functionality for any workload asset such as *Environment*, *Compute resource*, and some *Data source types*. These assets are now shared with **Departments** in the organization in addition to being shared with specific projects, or the entire cluster.

<!-- RUN-9364/10850 Search box for cards in V2 assets -->
* Added a search box for card galleries in any asset based workload creation form to provide an easy way to search for assets and resources. To filter use the asset name or one of the field values of the card.

### Credentials

<!-- RUN-9843/9852 - Allow researcher to create docker registry secrets -->
* Added *Docker registry* to the *Credentials* menu. Users can create docker credentials for use in specific projects for image pulling. To configure credentials, see [Configuring credentials](../admin/admin-ui-setup/credentials-setup.md#configuring-credentials).

<!-- RUN-8453/8454/8927 Technical documentation of 'Projects new parameters and options' use existing namespace, status, and more added to projects v2-->

### Policies
<!-- RUN-10588/10590 Allow workload policy to prevent the use of a new pvc -->
* Improved policy support by adding `DEFAULTS` in the `items` section in the policy. The `DEFAULTS` section sets the default behavior for items declared in this section. For example, this can be use to limit the submission of workloads only to existing PVCs. For more information and an example, see Policies, [Complex values](../admin/workloads/policies.md#complex-values).

### Researcher API

<!-- RUN-8631/8880 Researcher API for train jobs -->
* Extended researcher's API to allow stopping and starting of workloads using the API. For more information, see [Submitting Workloads via HTTP/REST](../developer/cluster-api/submit-rest.md).

### Integrations
<!-- RUN-9651/9652 Schedule and support of Elastic Jobs (Spark) -->
* Added support for Spark and Elastic jobs. For more information, see [Running Spark jobs with Run:ai](../admin/integration/spark.md#).
<!-- RUN-9024/9027 Ray Support - schedule and support of Ray Jobs -->
* Added support for Ray jobs. Ray is an open-source unified framework for scaling AI and Python applications. For more information, see [Integrate Run:ai with Ray](../admin/integration/ray.md#integrate-runai-with-ray).

* Added integration with Weights & Biases Sweep to allow data scientists to submit hyperparameter optimization workloads directly from the Run:ai UI. To configure sweep, see [Sweep configuration](../admin/integration/weights-and-biases.md#sweep-configuration).

<!-- RUN-9510 -->
* Added support for XGBoost. XGBoost, which stands for Extreme Gradient Boosting, is a scalable, distributed gradient-boosted decision tree (GBDT) machine learning library. It provides parallel tree boosting and is the leading machine learning library for regression, classification, and ranking problems. For more information, see [runai submit-dist xgboost](../Researcher/cli-reference/runai-submit-dist-xgboost.md)

### Compatibility

* Added support for multiple OpenShift clusters. For configuration information, see [Installing additional Clusters](../admin/runai-setup/self-hosted/ocp/additional-clusters.md).

### Installation

* The manual process of upgrading Kubernetes CRDs is no longer needed when upgrading to the most recent version (2.13) of Run:ai.

* From Run:ai 2.12 and above, the control-plane installation has been simplified and no longer requires the creation of a *backend values* file. Instead, install directly using `helm` as described in [Install the Run:ai Control Plane](../admin/runai-setup/self-hosted/k8s/backend.md#install-the-control-plane).

* From Run:ai 2.12 and above, the air-gapped, control-plane installation now generates a `custom-env.yaml` values file during the [preparation](../admin/runai-setup/self-hosted/k8s/preparations.md#prepare-installation-artifacts) stage. This is used when installing the [control-plane](../admin/runai-setup/self-hosted/k8s/backend.md#install-the-control-plane).
