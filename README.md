# consul-cluster

## To run consul cluster:

### 1) change to consul-cluster directory
*git clone repository if it does not exist already*

`git clone https://github.com/mkam423/consul-cluster.git`

`cd consul-cluster`

### 2) Currently the most updated and clean working version of cluster.
`git checkout cluster_v1`

### 3) Create persistent volume storage first.
`kubectl create -f pv.yaml`

### 4) Create claim to bind to the persistent volume.
`kubectl create -f pvc.yaml`

### 5) Check the claim and volume binds
`kubectl get pv` and `kubectl get pvc`

### 6) kubectl create -f consul.yaml

You should be able to see the service and statefulset for consul create successfully. Double check to see if they are there:

`kubectl get svc | grep consul` and `kubectl get statefulsets | grep consul`

You should also be able to get the pods and see them come up.

`kubectl get pods | grep consul`

3 pods named consul-0, consul-1, and consul-2 should create and end up in a running state.
