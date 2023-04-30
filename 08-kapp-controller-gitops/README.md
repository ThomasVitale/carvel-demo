# Continuous deployment of application via GitOps with kapp-controller

kapp deploy -a kapp-controller -y \
  -f https://github.com/carvel-dev/kapp-controller/releases/latest/download/release.yml

kubectl apply -f config/rbac.yml

kubectl apply -f config/config.yml

kubectl port-forward svc/simple-app 8080:80

kubectl delete -f config
