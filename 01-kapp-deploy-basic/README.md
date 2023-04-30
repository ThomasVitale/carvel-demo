# Basic deployment with kapp

kubectl apply -f manifests

kubectl delete -f manifests

kapp deploy -a my-app -f manifests

kapp delete -a my-app

https://tekton.dev/docs/installation/pipelines/

kubectl apply -f https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

kubectl get pods --namespace tekton-pipelines --watch

kubectl delete -f https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

kapp deploy -a tekton-pipelines -f https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

kapp delete -a tekton-pipelines
