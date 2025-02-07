---

copyright: 
  years: 2022, 2022
lastupdated: "2022-06-13"

keywords: kubernetes, containers

subcollection: containers


---

# Kubernetes version 1.24 change log
{: #changelog_124}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.24. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}

## Overview
{: #changelog_overview}

Unless otherwise noted in the change logs, the {{site.data.keyword.containerlong_notm}} provider version enables Kubernetes APIs and features that are at beta. Kubernetes alpha features, which are subject to change, are disabled.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security) for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}

## Version 1.24 change log
{: #124_changelog}

Review the version 1.24 change log.
{: shortdesc}

### Changelog for master fix pack 1.24.1_1523 and worker node fix pack 1.24.1_1522, released 9 June 2022
{: #1241_1522}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.21.5 | v3.23.1 | See the [Calico release notes](https://projectcalico.docs.tigera.io/archive/v3.23/release-notes/){: external}. The **default** BGP configuration found in the `default` [BGPConfiguration](https://projectcalico.docs.tigera.io/reference/resources/bgpconfig){: external} resource has been updated to set `nodeMeshMaxRestartTime` to `30m`.  This default change is only applied if the cluster does not have a custom BGP configuration. The previous default value was `120s`. |
| CoreDNS | 1.8.7 | 1.9.2 | See the [CoreDNS release notes](https://github.com/coredns/coredns/blob/v1.9.2/notes/coredns-1.9.2.md){: external}. |
| etcd | v3.4.18 | v3.5.4 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.4){: external}. |
| GPU device plug-in and installer | 382ada9 | 2b0b6d1 | Updated image for [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032){: external}, [CVE-2021-3634](https://nvd.nist.gov/vuln/detail/CVE-2021-3634){: external}, [CVE-2021-3737](https://nvd.nist.gov/vuln/detail/CVE-2021-3737){: external} and [CVE-2021-4189](https://nvd.nist.gov/vuln/detail/CVE-2021-4189){: external}. |
| {{site.data.keyword.blockstoragefull}} driver and plug-in | None | v2.2.5 | The {{site.data.keyword.blockstoragefull}} driver and plug-in component is now installed on clusters running classic infrastructure. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.23.7-4 | v1.24.1-4 | Updated to support the Kubernetes `1.24.1` release and `Go` version `1.18.2`. [Disabling load balancer NodePort allocation](https://kubernetes.io/docs/concepts/services-networking/service/#load-balancer-nodeport-allocation){: external} is not supported for VPC load balancers. |
| Kubernetes | v1.23.7 | v1.24.1 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.24.1){: external}. |
| Kubernetes configuration | N/A | N/A | Updated the [feature gate configuration](/docs/containers?topic=containers-service-settings#feature-gates). |
| Kubernetes CSI snapshotter CRDs | v4.2.1 | v5.0.1 | See the [Kubernetes container storage interface (CSI) snapshotter release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v5.0.1){: external}. |
| Kubernetes Dashboard | v2.4.0 | v2.5.0 | See the [Kubernetes Dashboard release notes](https://github.com/kubernetes/dashboard/releases/tag/v2.5.0){: external}. |
| Kubernetes DNS autoscaler | 1.8.4 | 1.8.5 | See the [Kubernetes DNS autoscaler release notes](https://github.com/kubernetes-sigs/cluster-proportional-autoscaler/releases/tag/1.8.5){: external}. |
| Kubernetes Metrics Server | v0.6.0 | v0.6.0 | Updated to run with a highly available configuration. For more information on this configuration, see the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.6.0){: external}. |
| Kubernetes NodeLocal DNS cache | 1.21.4 | 1.22.2 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.2){: external}. |
| Pause container image | 3.6 | 3.7 | See the [pause container image release notes](https://github.com/kubernetes/kubernetes/blob/master/build/pause/CHANGELOG.md){: external}. | 
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.23.7_1531 (master) and 1.23.7_1532 (worker node)" caption-side="top"}

