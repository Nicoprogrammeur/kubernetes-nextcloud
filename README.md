# kubernetes-nextcloud

## Introduction

Here are 5 yaml files for setting up a nextcloud application on a kubernetes \n
kubernetes must first be installed and configured to use the `kubectl` commands

Clone the repository

```
git clone https://github.com/Nicoprogrammeur/kubernetes-nextcloud.git
```

### Initialize the cluster

To start the application, go in your Terminal : :

Start the Nextcloud Deploy

```
kubectl apply -f nextcloud-deb.yaml
```

then start its service

```
kubectl apply -f nextcloud-svc.yaml
```

to finish it will be necessary to start the part nginx for the redirection of the requests on the applis nextcloud with the 3 files remaining in this order:

```
kubectl apply -f nginx-ingress-controller.yaml
kubectl apply -f nginx-ingress.yaml
kubectl apply -f nextcloud-ingress.yaml
```

make sure your port 80 and 443 are open for external access
