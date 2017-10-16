# consul-cluster

## To run consul cluster:

### 1) Move to consul-cluster directory.
*git clone repository if it does not exist already*

`git clone https://github.com/mkam423/consul-cluster.git`

`cd consul-cluster`

### 2) Change to the current most updated and clean working version of cluster.
`git checkout consolidated_cluster`


### 3) Create the consul cluster.
Use `kubectl create -f consul.yaml` to create entire cluster.


### 4) Check to see everything is up and running.
##### Check the claim and volume to ensure binding:

`kubectl get pv` and `kubectl get pvc`

The status should show up as bound for the claim and persistent volume. The binding for the claim should have the name of the volume that it's bound to within the description. This name should align with that which is in the yaml file.

##### Check the service and statefulset to ensure both both up:

Use `kubectl get svc | grep consul` and `kubectl get statefulsets | grep consul` to view the successful creations of the service and statefulset.

##### Check the creation of pods designated by the statefulset are running:

Use `kubectl get pods | grep consul` to see creation of the pods.

3 pods named consul-0, consul-1, and consul-2 should create and end up in a running state.
