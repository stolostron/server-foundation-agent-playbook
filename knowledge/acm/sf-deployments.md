---
name: Server Foundation Deployments
description: This part of content includes everything about server foundaiton deployments(components).
---

Server Foundation Components are part of the ACM. They exist under different namespaces as deployments.

One component could have multiple deployments.

Here is the table of the components and their namespaces:

| Component                  | Namespace                           | Deployment Name                     | Cluster Type |
| -------------------------- | ----------------------------------- | ----------------------------------- | ------------ |
| cluster-proxy              | multicluster-engine                 | cluster-proxy                       | Hub          |
| cluster-proxy              | multicluster-engine                 | cluster-proxy-addon-manager         | Hub          |
| cluster-proxy              | multicluster-engine                 | cluster-proxy-addon-user            | Hub          |
| import controller          | multicluster-engine                 | managedcluster-import-controller-v2 | Hub          |
| foundation                 | multicluster-engine                 | ocm-controller                      | Hub          |
| foundation                 | multicluster-engine                 | ocm-webhook                         | Hub          |
| foundation                 | multicluster-engine                 | ocm-proxyserver                     | Hub          |
| ocm operator               | multicluster-engine                 | cluster-manager                     | Hub          |
| metrics                    | multicluster-engine                 | clusterlifecycle-state-metrics-v2   | Hub          |
| klusterlet                 | open-cluster-management-agent       | klusterlet                          | Managed      |
| klusterlet-agent           | open-cluster-management-agent       | klusterlet-agent                    | Managed      |
| work-manager               | open-cluster-management-agent-addon | klusterlet-addon-workmgr            | Managed      |
| cluster-proxy              | open-cluster-management-agent-addon | cluster-proxy-proxy-agent           | Managed      |
| msa/managed-serviceaccount | open-cluster-management-agent-addon | managed-serviceaccount-addon-agent  | Managed      |
