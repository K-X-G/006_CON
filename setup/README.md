## Create Kubernetes cluster with Terraform
> Prerequisite
- Comming soon

1. Fetch your project id with `gcloud config get-value project` and replace the value in tfvars file and set your region.
2. Initialize your directory with `terraform init` command.
3. Check if configuration is valid with `terraform validate` command.
4. If not enabled already you need to enable Compute Engine API and Kubernetes Engine API:
    - `gcloud services enable compute.googleapis.com`
    - `gcloud services enable container.googleapis.com`
5. Apply your config with `terraform apply` command.

## Configure kubectl after creation of the cluster

### GKE:
`gcloud container clusters get-credentials $(terraform output -raw kubernetes_cluster_name) --region $(terraform output -raw region)`

## Cluster deletion
`gcloud container clusters delete CLUSTER_NAME`
