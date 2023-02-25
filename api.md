| NAME                            | SHORTNAMES                           | APIVERSION                           | NAMESPACED                     | KIND                        |
|---------------------------------|--------------------------------------|--------------------------------------|--------------------------------|-----------------------------|
| bindings                        | v1                                   | true                                 | Binding                        |                             |
| componentstatuses               | cs                                   | v1                                   | false                          | ComponentStatus             |
| configmaps                      | cm                                   | v1                                   | true                           | ConfigMap                   |
| endpoints                       | ep                                   | v1                                   | true                           | Endpoints                   |
| events                          | ev                                   | v1                                   | true                           | Event                       |
| limitranges                     | limits                               | v1                                   | true                           | LimitRange                  |
| namespaces                      | ns                                   | v1                                   | false                          | Namespace                   |
| nodes                           | no                                   | v1                                   | false                          | Node                        |
| persistentvolumeclaims          | pvc                                  | v1                                   | true                           | PersistentVolumeClaim       |
| persistentvolumes               | pv                                   | v1                                   | false                          | PersistentVolume            |
| pods                            | po                                   | v1                                   | true                           | Pod                         |
| podtemplates                    | v1                                   | true                                 | PodTemplate                    |                             |
| replicationcontrollers          | rc                                   | v1                                   | true                           | ReplicationController       |
| resourcequotas                  | quota                                | v1                                   | true                           | ResourceQuota               |
| secrets                         | v1                                   | true                                 | Secret                         |                             |
| serviceaccounts                 | sa                                   | v1                                   | true                           | ServiceAccount              |
| services                        | svc                                  | v1                                   | true                           | Service                     |
| mutatingwebhookconfigurations   | admissionregistration.k8s.io/v1      | false                                | MutatingWebhookConfiguration   |                             |
| validatingwebhookconfigurations | admissionregistration.k8s.io/v1      | false                                | ValidatingWebhookConfiguration |                             |
| customresourcedefinitions       | crd,crds                             | apiextensions.k8s.io/v1              | false                          | CustomResourceDefinition    |
| apiservices                     | apiregistration.k8s.io/v1            | false                                | APIService                     |                             |
| controllerrevisions             | apps/v1                              | true                                 | ControllerRevision             |                             |
| daemonsets                      | ds                                   | apps/v1                              | true                           | DaemonSet                   |
| deployments                     | deploy                               | apps/v1                              | true                           | Deployment                  |
| replicasets                     | rs                                   | apps/v1                              | true                           | ReplicaSet                  |
| statefulsets                    | sts                                  | apps/v1                              | true                           | StatefulSet                 |
| tokenreviews                    | authentication.k8s.io/v1             | false                                | TokenReview                    |                             |
| localsubjectaccessreviews       | authorization.k8s.io/v1              | true                                 | LocalSubjectAccessReview       |                             |
| selfsubjectaccessreviews        | authorization.k8s.io/v1              | false                                | SelfSubjectAccessReview        |                             |
| selfsubjectrulesreviews         | authorization.k8s.io/v1              | false                                | SelfSubjectRulesReview         |                             |
| subjectaccessreviews            | authorization.k8s.io/v1              | false                                | SubjectAccessReview            |                             |
| allowlistedv2workloads          | auto.gke.io/v1                       | false                                | AllowlistedV2Workload          |                             |
| allowlistedworkloads            | auto.gke.io/v1                       | false                                | AllowlistedWorkload            |                             |
| horizontalpodautoscalers        | hpa                                  | autoscaling/v2                       | true                           | HorizontalPodAutoscaler     |
| cronjobs                        | cj                                   | batch/v1                             | true                           | CronJob                     |
| jobs                            | batch/v1                             | true                                 | Job                            |                             |
| certificatesigningrequests      | csr                                  | certificates.k8s.io/v1               | false                          | CertificateSigningRequest   |
| backendconfigs                  | bc                                   | cloud.google.com/v1                  | true                           | BackendConfig               |
| leases                          | coordination.k8s.io/v1               | true                                 | Lease                          |                             |
| endpointslices                  | discovery.k8s.io/v1                  | true                                 | EndpointSlice                  |                             |
| events                          | ev                                   | events.k8s.io/v1                     | true                           | Event                       |
| flowschemas                     | flowcontrol.apiserver.k8s.io/v1beta2 | false                                | FlowSchema                     |                             |
| prioritylevelconfigurations     | flowcontrol.apiserver.k8s.io/v1beta2 | false                                | PriorityLevelConfiguration     |                             |
| memberships                     | hub.gke.io/v1                        | false                                | Membership                     |                             |
| capacityrequests                | capreq                               | internal.autoscaling.gke.io/v1alpha1 | true                           | CapacityRequest             |
| nodes                           | metrics.k8s.io/v1beta1               | false                                | NodeMetrics                    |                             |
| pods                            | metrics.k8s.io/v1beta1               | true                                 | PodMetrics                     |                             |
| storagestates                   | migration.k8s.io/v1alpha1            | false                                | StorageState                   |                             |
| storageversionmigrations        | migration.k8s.io/v1alpha1            | false                                | StorageVersionMigration        |                             |
| frontendconfigs                 | networking.gke.io/v1beta1            | true                                 | FrontendConfig                 |                             |
| managedcertificates             | mcrt                                 | networking.gke.io/v1                 | true                           | ManagedCertificate          |
| serviceattachments              | networking.gke.io/v1                 | true                                 | ServiceAttachment              |                             |
| servicenetworkendpointgroups    | svcneg                               | networking.gke.io/v1beta1            | true                           | ServiceNetworkEndpointGroup |
| ingressclasses                  | networking.k8s.io/v1                 | false                                | IngressClass                   |                             |
| ingresses                       | ing                                  | networking.k8s.io/v1                 | true                           | Ingress                     |
| networkpolicies                 | netpol                               | networking.k8s.io/v1                 | true                           | NetworkPolicy               |
| runtimeclasses                  | node.k8s.io/v1                       | false                                | RuntimeClass                   |                             |
| updateinfos                     | updinf                               | nodemanagement.gke.io/v1alpha1       | true                           | UpdateInfo                  |
| poddisruptionbudgets            | pdb                                  | policy/v1                            | true                           | PodDisruptionBudget         |
| clusterrolebindings             | rbac.authorization.k8s.io/v1         | false                                | ClusterRoleBinding             |                             |
| clusterroles                    | rbac.authorization.k8s.io/v1         | false                                | ClusterRole                    |                             |
| rolebindings                    | rbac.authorization.k8s.io/v1         | true                                 | RoleBinding                    |                             |
| roles                           | rbac.authorization.k8s.io/v1         | true                                 | Role                           |                             |
| priorityclasses                 | pc                                   | scheduling.k8s.io/v1                 | false                          | PriorityClass               |
| secretproviderclasses           | secrets-store.csi.x-k8s.io/v1        | true                                 | SecretProviderClass            |                             |
| secretproviderclasspodstatuses  | secrets-store.csi.x-k8s.io/v1        | true                                 | SecretProviderClassPodStatus   |                             |
| volumesnapshotclasses           | snapshot.storage.k8s.io/v1           | false                                | VolumeSnapshotClass            |                             |
| volumesnapshotcontents          | snapshot.storage.k8s.io/v1           | false                                | VolumeSnapshotContent          |                             |
| volumesnapshots                 | snapshot.storage.k8s.io/v1           | true                                 | VolumeSnapshot                 |                             |
| csidrivers                      | storage.k8s.io/v1                    | false                                | CSIDriver                      |                             |
| csinodes                        | storage.k8s.io/v1                    | false                                | CSINode                        |                             |
| csistoragecapacities            | storage.k8s.io/v1                    | true                                 | CSIStorageCapacity             |                             |
| storageclasses                  | sc                                   | storage.k8s.io/v1                    | false                          | StorageClass                |
| volumeattachments               | storage.k8s.io/v1                    | false                                | VolumeAttachment               |                             |
| audits                          | warden.gke.io/v1                     | false                                | Audit                          |                             |
