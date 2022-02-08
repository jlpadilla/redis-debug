
## HOW TO RUN THIS SCRIPT:
```
oc login ... <RHACM Hub>
oc exec -it search-redisgraph-0 -n open-cluster-management -- /bin/bash < redis-debug.sh
```

## DESCRIPTION:
This script collects data about the Redisgraph instance usage by RHACM to debug issues with the search service.
Output data is anonymized and only shows total counts of different resources.

## DATA COLLECTED:
1. Redis INFO (https://redis.io/commands/info)
2. RHACM Resource Statistics:
   - Total Resource count
   - Total uids (must match total resources, uid duplication causes problems)
   - Total Cluster count
   - Resource count by cluster
   - Resource count by kind
   - Namespaces count by cluster
   - Resource count per cluster/namespace
   - Kubernetes node count by cluster
   - Resources containing too many labels.
3. RHACM Edges Statistics:
   - Total Edge count
   - Edge count by cluster
   - Total Inter-cluster edges count
   - Intercluster edge count by cluster (hub to cluster)
   - Edges by edge type