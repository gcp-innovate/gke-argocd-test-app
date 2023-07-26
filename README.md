# gke-argocd-test-app
 gke-argocd-test-app

# Pre-requisites

# First deploy a GKE cluster using a pipeline.
# Then deploy Argo CD on GKE cluster and deploy argocd in argocd name space

# kubectl create ns argocd
# kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
# Expose Argocd as LB service.
# Access Argocd va GUI console.


Argo CD's primary job is to make sure that your desired state, stored in Git, matches your running state on your Kubernetes installation. It does this by comparing Kubernetes declarations (stored in YAML or JSON in Git) with the running state. Argo CD does this by treating a group of related manifests as an atomic unit. This atomic unit is called an Application, in Argo CD. 

Here we shall use this repository which contains YAML files for test application (deployment, services and namesace)

We shall deploy on GKE via Argo CD.
Post deployment we shall check the configuratiions of the pods and services.
We shall then make change manually by logging to GKE worker node. If changes are applied, they shall be automatically revert to whatever code is on Git as ArgoCD would detect a drift and automatically change it.
