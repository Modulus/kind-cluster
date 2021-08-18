# Create cluster
kind create cluster --name kind --config config.yaml

# Deploy ingress controller
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml


# Test ingress
kubectl apply -f https://kind.sigs.k8s.io/examples/ingress/usage.yaml
# should output "foo"
curl localhost/foo
# should output "bar"
curl localhost/bar