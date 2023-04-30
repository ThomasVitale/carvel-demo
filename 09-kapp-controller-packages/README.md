# Composable platforms with kapp-controller

kubectl create ns platform-packages

kctrl package repository add -r platform-packages \
  --url ghcr.io/thomasvitale/platform-packages:0.0.1 \
  -n platform-packages

kctrl package install -i cert-manager \
  -p cert-manager.packages.thomasvitale.com \
  -v 1.11.1 \
  -n platform-packages

imgpkg copy -b ghcr.io/thomasvitale/platform-packages:0.0.1 --to-repo ghcr.io/thomasvitale/air-gapped/platform-packages
