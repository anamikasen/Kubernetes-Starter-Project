# Kubernetes-Starter-Project
Starter Project to get started with K8s - https://www.youtube.com/watch?v=X48VuDVv0do&amp;t=338s&amp;ab_channel=TechWorldwithNana

# Points covered:
Differences between:
  1. Deployment - Blueprint for the application Pods. You can splecify the number of replicas that you intend to have for the pods here.
     Deployments are stateless. Databases cannot be replicated using deployments. Databases are stateful applications which ensure data persistence.
  2. Pods - are ephemeral. Can crash and a new pod can come in place using the replica set. Pods get their own IP addresses.
  3. Services - are permanent IP addresses that get attached to the pods in case the pods die. This will ensure that the pods can still be communicated with. 

Abstraction layers:
  1. Deployment: Manages replica sets
  2. Replica Set: Manages replicas of a pod
  3. Pods: Encapsulates the container running the Container Runtime Engines (CREs) like Docker etc.
 
 Everything below the Deployment layer is managed by K8s
  
Types of Services:
  1. External Service - to expose the service to communicate with the Internet
  2. Internal Service - to communicate with the pods
  
# Kubernetes Cluster Architecture:
4 parts which run on Master Node:
1. `apiServer` - kubelet; it is a cluster gateway.
2. `Controller Manager` - detects when nodes die and states change. It requests the Scheduler (through the apiServer - kubelet)
3. `kube Scheduler`- starts new pods; has mechanism to decide which pod has capacity to get started.
4. `etcd` - it is the KV store of cluster state. It is the cluster brain. Application data is not stored here.
