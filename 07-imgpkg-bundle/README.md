# Packaging configuration as OCI artifacts with imgpkg

kbld -f bundle/config.yml --imgpkg-lock-output bundle/.imgpkg/images.yml

imgpkg push -b ghcr.io/thomasvitale/simple-app-bundle:v1.0.0 -f bundle

imgpkg pull -b ghcr.io/thomasvitale/simple-app-bundle:v1.0.0 -o pulled-bundle

kbld -f bundle/config.yml -f bundle/.imgpkg/images.yml | kapp deploy -a simple-app -f- -y

kapp delete -a simple-app

imgpkg copy -b ghcr.io/thomasvitale/simple-app-bundle:v1.0.0 --to-repo ghcr.io/thomasvitale/air-gapped/simple-app-bundle
