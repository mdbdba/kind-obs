# kind-obs

Create the cluster
```shell
❯ ulimit -n 65536
❯ kind create cluster --config cluster.yaml
Creating cluster "obs-v1" ...
 ✓ Ensuring node image (kindest/node:v1.32.2) 🖼
 ✓ Preparing nodes 📦 📦 📦 📦  
 ✓ Writing configuration 📜 
 ✓ Starting control-plane 🕹️ 
 ✓ Installing CNI 🔌 
 ✓ Installing StorageClass 💾 
 ✓ Joining worker nodes 🚜 
Set kubectl context to "kind-obs-v1"
You can now use your cluster with:

kubectl cluster-info --context kind-obs-v1

Have a nice day! 👋
❯ kubectl cluster-info --context kind-obs-v1
Kubernetes control plane is running at https://127.0.0.1:45051
CoreDNS is running at https://127.0.0.1:45051/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

```

# Boostrap (this will take a few minutes)
```shell
❯ flux --version
  flux version 2.5.1
❯ flux bootstrap github \
--owner=$GITHUB_USER \
--repository=kind-obs \
--branch=main \
--path=./ops \
--personal
► connecting to github.com
► cloning branch "main" from Git repository "https://github.com/mdbdba/kind-obs.git"
✔ cloned repository
► generating component manifests
...
✔ notification-controller: deployment ready
✔ source-controller: deployment ready
✔ all components are healthy



```
