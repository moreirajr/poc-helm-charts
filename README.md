# Steps

1 - Push image on docker hub

docker login
docker build -t [dockerhub-user]/[image-name]:tag .
docker tag [image-name]:tag [dockerhub-user]/[image-name]:tag
docker push [dockerhub-user]/[image-name]:tag

2 - Create secrets with Docker credentials

kubectl create secret docker-registry [secret-name] \
  --docker-server=[DOCKER_REGISTRY_SERVER] \
  --docker-username=[DOCKER_USER] \
  --docker-password=[DOCKER_PASSWORD] \
  --docker-email=[DOCKER_EMAIL]

3 - Change repository on values.yaml

4 - Deploy the Helm chart
helm install dotnet-api ./helm

# Kubernetes
- Verify Kubernetes cluster (should see 'docker-compose' when running locally)
kubectl get nodes

- Creates/updates resources in a cluster.
kubectl apply -f [your-file]

- Delete resources
kubectl delete -f [your-file]

- Check the app components
kubectl -n vote get pods

- Interacting with running Pods
kubectl logs [name]

- Show services
kubectl get services

- Show pods
kubectl get pods

- Show deployment
kubectl get deployment

- Describe pods
kubectl describe pod [name]

- Create secrets with Docker credentials
kubectl create secret docker-registry [secret-name] \
  --docker-server=[DOCKER_REGISTRY_SERVER] \
  --docker-username=[DOCKER_USER] \
  --docker-password=[DOCKER_PASSWORD] \
  --docker-email=[DOCKER_EMAIL]

# Helm

- Create a Helm chart
helm create [name]

- Validate the Helm chart
helm lint ./[folder]

- Add a repository from the internet
helm repo add [name] [url]

- Remove a repository from your system
helm repo remove [name]

- Update repositories
helm repo update

- List the charts in the repository you can install
helm search repo [name]

- Deploy the chart
helm install [name] [chart]
helm install --name [name] ./[folder]

- List of deployments (release)
helm list
helm list --all-namespaces

- Remove release
helm uninstall [name]

- Inspect the generated definitions
helm install [chart] --dry-run --debug ./[folder]

- Create a tar package
helm package ./[folder]

- Run a local repository to serve your chart (in a separate terminal window)
helm serve

- Search in the local helm search local
helm search local

- See what is rendered (even when it fails)
helm install --dry-run --disable-openapi-validation [name] ./[folder]

## Cheatsheet
https://kubernetes.io/docs/reference/kubectl/quick-reference/

