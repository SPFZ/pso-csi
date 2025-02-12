# Changelog

## v6.2.2-rc1 (01/28/2022)

#### Bug fixes and enhancements:

* Bug fix for using FlashArray NVMeoF-RDMA when other local NVMe controllers exist on hosts
* Bug fix for FlashArray with both NVMeoF-FC and NVMeoF-RDMA configured

## v6.2.1 (11/15/2021)

#### Bug fixes and enhancements:

* Fix KB unit issue for NodeGetVolumeStats CSI call
* Support FlashBlade Safe Mode.
* Upgrade apiextensions.k8s.io API version from v1beta1 to v1.
* [#196](https://github.com/purestorage/pso-csi/pull/196) Update intrusions CRD v1 to be backward-compatible
* Upgrade CSIDriver apiVersion from v1beta1 to v1
* FibreChannel + NVME bug fixes.
* Fix volume resize failures

## v6.2.0 (08/20/2021)

#### Features:

* FlashArray NVMeoF-RoCE support (NVMeoF using RDMA over Converged Ethernet) officially goes GA
* Enable FlashBlade filesystem hard limit by default upon creation (existing filesystems will not be affected)

#### Bug fixes and enhancements:

* Bug fix for using FC SAN type on FlashArray Purity 6.0+
* Bug fix for DB reconstruction tool when found devices with no UUIDs
* NVMeof-RoCE support bug fixes and improvements
* Topology feature performance improvement
* Bug fix for [#166](https://github.com/purestorage/pso-csi/issues/166) iSCSI CIDR not passed to pso-db pods 

## v6.2.0-rc1 (07/22/2021)

#### Features:

* FlashArray NVMeoF-RoCE support (NVMeoF using RDMA over Converged Ethernet)
* If you want to try the NVMeoF-RoCE feature, a fresh PSO installation is required.

## v6.1.1 (04/12/2021)

#### Bug fixes and enhancements:

* Add missing toleration to db pods
* [Support DB pods StatefulSet node-affinity and topology](https://github.com/purestorage/pso-csi/blob/master/docs/db-topology.md)
* [#90](https://github.com/purestorage/pso-csi/issues/90) Enhance PSO log debug level
* [#141](https://github.com/purestorage/pso-csi/issues/141) Set Default Cockroach DB version to v20.2.6	

#### Known issues:
* Snapshots created from imported volume don't show ready to use.
* Database volume is mounted as read-only and result in CrashLoopBackOff status of a db pod.

## v6.1.0 (02/24/2021)

#### Features:

* Provided upgrade path from PSO 5.x to PSO 6.x [doc](./docs/csi-5to6-upgradepath.md).

## v6.0.5 (01/11/2021)

#### Enhancements:

* Support PX-Backup for remote snapshot restore.

#### Bug fixes:

* Fixed [#90](https://github.com/purestorage/pso-csi/issues/90) PSO log debug level.

#### Known issues:

* Snapshots created from imported volume don't show ready to use

## v6.0.4 (11/26/2020)

#### Major Features:

* Ephemeral volume support.

#### Enhancements:

* CSI 1.3 compliance.
* Improve volume provisioning performance when topology is enabled.
* Add default cockroach DB pod memory limit to 1GB.

#### Bug Fixes:

* Fix volume attach failure when active cluster is enabled.
* Fix failure when image contains port as suffix of repository.
* Fix volume resize bug.

## v6.0.3 (10/07/2020)

#### Enhancements:

* Enabled support to import snapshots from Pure Flash Array(FA). This applies to snapshots that were created directly on the Flash Array outside of K8S
* Added support for Platform9.
* Improved handling of NFS versions and support for mounting volumes that were provisioned prioir to NFS v4.1 upgrade
* Fixed race condition issue in cockrachdb operator that created more pods than needed
* Fixed Issue90: Log level in values.yaml not honored
* Support for REST API v2.0

## v6.0.2 (09/15/2020)

#### Bugfixes:

* Added values to specify `psctl` and `cockroach` image tags and names to enable dark sites.
* Increased node replacement threshold to prevent unnecessary database node migrations.
* Added OpenShift `MachineConfig` to enable Red Hat Container OS deployments.

## v6.0.1 (08/24/2020)

#### Enhancements:

* Update helm chart name from `pureStorageDriver` to `pure-pso` to meet the rigid helm chart naming convention.

## v6.0.0 RC (06/30/2020)

#### Major Features:

* Stateful PSO to persist volumes metadata. 

#### Enhancements:

- [#9](https://github.com/purestorage/pso-csi/issues/9) - FlashBlade NFS 4.1 Support and FB-NFS Access Control via Export Rules.

#### Bug Fixes:
