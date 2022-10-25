# Getting tilt to run offline

1) Remove cmd_button (which is an extension fetched on every tiltfile load)
2) Remove observability for tilt-settings.
2) Ensure docker base images (golang + distroless) are downloaded using docker pull.
3) Set deploy-cert-manager to false
4) Create a Cluster using the kubecon-22-na scripts/create-kind-cluster.sh (Which includes the kind-load commands for e.g. cert manager
5) Deploy cert manager using the raw yamls - `kubectl apply -f clusterctl/repository/cert-manager/v1.9.1/cert-manager.yaml`
6) Run `tilt up`

Clusters and ClusterClasses from the kubecon-na-22 repo should be used (as they contain the correct images)
