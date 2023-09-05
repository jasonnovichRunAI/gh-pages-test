# Run:ai version 2.12

## Version 2.12.4

### Release date

June 2023

#### Fixed issues

| Internal ID | Description |
|-----------|--------------|
| RUN-10129 | Fixed an issue where logs of completed trainings were not displayed in the *UI*. |

## Version 2.12.3

### Release date

May 2023

<!-- RUN-9922 -->

* Added an option in the *UI* to login as a local user in OpenShift environments.

#### Fixed issues

|Internal ID|Description|
|-----------|--------------|
| RUN-10052 | Fixed an issue where a *UI* change is needed to submit a workload after a template was used to create a job. |
| RUN-10000 | Fixed a *UI* issue that affected some users, where the job submission form wasn't working due to a missing value in a JWT token. |
| RUN-9576 | Added a missing endpoint (`projectDepartment`) to the API documentation site. |

## Version 2.12.1

### Release date

May 2023

<!-- RUN-9323 -->
Improved the readability of unsuccessful node scheduling in the message log.

#### Fixed issues

|Internal ID|Description|
|-----------|--------------|
| RUN-9326 | Fixed an issue that affected the dashboard where projects created with fractional GPUs, display the number of GPUs rounded down to nearest whole number. |
| RUN-9039 | Fixed an issue that displays jobs as interactive-preemptible after cycling the `preemptible` flag from on to off. |

## Version 2.12.0

### Release date

May 2023

#### Release content

##### Compatibility

* Removed support for OpenShift 4.8 and 4.9, and Kubernetes 1.21 and 1.22.

* Added support for OpenShift 4.12 and Kubernetes 1.27.

* The `runai top job` command was deprecated.

**Single sign on**

When SSO is enabled, you can still create and authenticate with Local users. For configuration of local users and SSO users, see [Create a new user](../admin/admin-ui-setup/admin-ui-users.md#create-a-user).

##### Researcher tools enhancements

**OpenShift Dev Spaces**

Added support fort Openshift Dev Spaces custom resource definitions using the RunAI scheduler.

<!-- RUN-9352 / RUN-8824 --> **Training Experience**

Added a new feature that allows the researcher to provision a training job in a project using a wizard like flow.

<!-- RUN-8789 -->
**DeepSpeed Integration**

Added integration and certification with DeepSpeed for multi pod using open-mpi. See [DeepSpeed Integration](../admin/integration/deepspeed.md).

**Cluster API**

<!-- RUN-8880 -->
Added `Stop`, `Suspend`, and `Resume` jobs options to [Submitting Workloads via YAML](../developer/cluster-api/submit-yaml.md).

**Comet Integration**

Comet builds tools that help data scientists, engineers, and team leaders accelerate and optimize machine learning and deep learning models. This integration with Run:ai provides organizations of every size a platform to build better ML models faster. For more information, see [Comet](https://www.comet.com/site/){target=_blank}. For configuration information, see [Comet integration](../admin/integration/comet.md).

#### Known issues

None

#### Fixed issues

|Internal ID|Description|
|-----------|--------------|
| RUN-6827 | Fixed an issue where the ellipsis remains in the Dashboard when using Firefox after a long idle time. |
| RUN-8621 | Fixed the error response to 204 when changing to a custom logo. |
| RUN-8662 | Fixed grayed out submit button when using a template with pvc. |
| RUN-8890 | Fixed a scheduler panic when both a project and a department use the same name. |
| RUN-9035 | Fixed an issue that allowed a scheduler from any node pool to delete reservation pods created on a different node pool which may have caused a failure to schedule jobs with fractional GPU allocations. |
| RUN-9089 | Added the `port forward` CLI command. |
| RUN-9166 | Fixed incorrect response about resource availability in messages indicating why a specific job failed to schedule. |
| RUN-9259 | Fixed an issue where cluster sync requests are not working at scale due to a large number of requests. |
