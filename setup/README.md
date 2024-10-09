Configure kubectl after creation of the cluster

GKE:
gcloud container clusters get-credentials $(terraform output -raw kubernetes_cluster_name) --region $(terraform output -raw region)

Cluster deletion
gcloud container clusters delete CLUSTER_NAME
