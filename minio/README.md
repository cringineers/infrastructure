# Minio
This project uses minio [chart](https://artifacthub.io/packages/helm/bitnami/minio) from bitnami.

To deploy:
1. `kubectl create namespace minio`
2. `kubectl apply -f ./secret.yaml` -n minio
3. `helm repo add bitnami https://charts.bitnami.com/bitnami`
4. `helm install minio bitnami/minio --namespace minio --values ./values.yaml`
