# Run:ai Version 2.8

Trying to lint this.
A change for push ci test.
## Release Date

 November 2022 

## Release Content
<!-- 
* Now supporting _spread_ scheduling strategy as well. For more information see [scheduling strategies](../Researcher/scheduling/strategies.md). -->

### Node Pools

Node Pools is a new method for managing GPU and CPU resources by __grouping the resources__ into distinct pools. With node pools:

* You allocate Project and Department resources from these pools to be used by Workloads. 
* The administrator controls which workloads can use which resources, allowing an optimized utilization of resources according to more accurate customer needs. 


### User Interface Enhancements

* The _Departments_ screen has been revamped and new functionality added, including a new and clean look and feel, and improved search and filtering capabilities.
* The _Jobs_ screen has been split into 2 tabs for ease of use:
    * _Current_:  (the default tab) consists of all the jobs that currently exist in the cluster. 
    * _History_:  consists of all the jobs that have been deleted from the cluster. Deleting Jobs also deletes their Log (no change).

### Installation improvements 

The Run:ai user interface [requires a URL address](../admin/runai-setup/cluster-setup/cluster-prerequisites.md#cluster-url) to the Kubernetes cluster. The requirement is relevant for SaaS installation only. 

In previous versions of Run:ai the administrator should [provide an IP address](../admin/runai-setup/cluster-setup/cluster-prerequisites.md#cluster-ip) and Run:ai would automatically create a DNS entry for it and a matching trusted certificate. 

In version 2.8,  the default is for the Run:ai administrator to provide a [DNS and a trusted certificate](../admin/runai-setup/cluster-setup/cluster-prerequisites.md#domain-name). 

The older option still exists but is being deprecated due to complexity.

### Inference 
The Deployment details page now contains the URL for the Inference service 


### Hyperparameter Optimization (HPO)

HPO Jobs are now presented as a single line in the Job List rather than a separate line per experiment.
