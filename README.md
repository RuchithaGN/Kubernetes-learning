# Kubernetes-learning
I’m thrilled to share that I’ve recently deepened my understanding of Kubernetes and its key components! 

Kubernetes has become an essential tool for managing containerized applications, and diving into its architecture has been both challenging and rewarding. Here’s what I’ve learned so far:

✅ Pods: The smallest deployable units in Kubernetes, containing one or more containers.
✅ Nodes: Physical or virtual machines that run Kubernetes workloads. 
✅ Services: Enable stable network access to Pods, even as they scale or move.
✅ Deployments: Manage the lifecycle and scaling of applications. 
✅ ConfigMaps & Secrets: Manage configuration and sensitive data securely. 
✅ Ingress: Define HTTP and HTTPS routing rules for services.


It’s been an exciting journey, and I’m looking forward to continuing to build my expertise in cloud-native technologies



These are all important components of Kubernetes. Here's a breakdown of each:

1. Scheduler
Role: The Kubernetes Scheduler is responsible for deciding which node (machine) in the cluster should run a pod. It ensures that the pods are scheduled on nodes that have enough resources (CPU, memory) and meet other constraints.
Functionality: It listens for newly created pods that do not have an assigned node and selects the best node based on resource availability and other policies.


2. API Server
Role: The API Server is the front-end for the Kubernetes control plane. It exposes the Kubernetes API and acts as the entry point for all REST commands used to interact with the cluster.
Functionality: It validates and processes API requests, both internal and external, and communicates with the etcd key-value store to retrieve and store cluster state. All components interact with the API Server.


3. Controllers
Role: Kubernetes Controllers are responsible for maintaining the desired state of the cluster by continuously monitoring resources (like Pods, Deployments, and ReplicaSets) and making adjustments to match the desired state.
Functionality: For example, a Deployment Controller ensures that the specified number of replicas of a pod are running. If a pod fails, the controller creates a new one to replace it.


4. etcd
Role: etcd is a distributed key-value store used by Kubernetes to store all cluster data, including configuration data, state data, and metadata.
Functionality: It's a reliable storage backend for maintaining the configuration and state of the Kubernetes cluster, including details about nodes, pods, deployments, etc. All other components, like the API Server, rely on etcd for cluster information.


5. Cloud Controller Manager
Role: The Cloud Controller Manager allows Kubernetes to interact with the underlying cloud provider (e.g., AWS, Google Cloud, Azure).
Functionality: It manages cloud-specific resources such as load balancers, storage volumes, and networking. It abstracts cloud-specific functionality, allowing Kubernetes to be used across different cloud platforms.


6. Kubelet
Role: The Kubelet is an agent running on each node in the Kubernetes cluster.
Functionality: It ensures that the containers are running in the pods and works with the container runtime (like Docker or containerd). The Kubelet watches the API server for pod specifications and ensures the containers are running as expected.


7. Kube-Proxy
Role: The Kube-Proxy manages network traffic in the cluster, implementing network rules for Pods.
Functionality: It ensures that network requests to a Service (a stable IP address for a set of pods) are forwarded to the correct pod. It can use either iptables or ipvs to manage the routing of traffic inside the cluster.


8. Control Runtime
Role: The Control Runtime is the set of libraries that are used by Kubernetes controllers and other components to manage the cluster state.
Functionality: It provides the necessary tools for interaction with the API server and for maintaining cluster state. It plays a key role in the controller's ability to watch resources and update them to match the desired state.
