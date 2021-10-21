# kubectl debug-patch

Troubleshoot deployments, statefulsets or daemonsets with a
bring-your-own debug image.


## Usage

```sh
kubectl debug-patch deployment my-app --image ubuntu:20.04
```


After the debug sidecar has been patched, you can start debugging with:

```sh
kubectl exec -it deployment/my-app -c debug -- sh
```


Once finished, you can remove the debug sidecar:

```sh
kubectl debug-patch deployment my-app --undo
```

:warning: The sidecar is patched into the deployment, so kubectl apply ignores the sidecar.
The only way to remove it is with a patch.


## Installation

Using [krew](https://krew.sigs.k8s.io/): coming soon

Using curl:

```sh
curl -LO https://github.com/reegnz/kubectl-debug-patch/raw/master/kubectl-debug_patch
chmod +x ./kubectl-debug_patch
sudo mv ./kubectl-debug_patch /usr/local/bin/kubectl-debug_patch
```
