# Overlays with ytt

ytt -f config > test.yml

ytt -f config --data-value service_type=LoadBalancer > test.yml

ytt -f config --data-value service_type=Something
