# Templates with ytt

ytt -f config

ytt -f config | kapp deploy -a hello-app -f- -y

k port-forward svc/hello-app 8080:80

ytt -f config --data-values-file values.yml 

ytt -f config --data-values-file values.yml | kapp deploy -a hello-app -f- -y

k port-forward svc/hello-app 8080:80

kapp delete -a hello-app -y
