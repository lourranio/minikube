# minikube
minikube

## PROBLEM 1
λ minikube start --driver=virtualbox
* minikube v1.28.0 on Microsoft Windows 10 Pro 10.0.19043 Build 19043
* Using the virtualbox driver based on existing profile
* Starting control plane node minikube in cluster minikube
* Creating virtualbox VM (CPUs=4, Memory=4000MB, Disk=20000MB) ...
! StartHost failed, but will try again: creating host: create: precreate: This computer doesn't have VT-X/AMD-v enabled. Enabling it in the BIOS is mandatory
* Creating virtualbox VM (CPUs=4, Memory=4000MB, Disk=20000MB) ...
* Failed to start virtualbox VM. Running "minikube delete" may fix it: creating host: create: precreate: This computer doesn't have VT-X/AMD-v enabled. Enabling it in the BIOS is mandatory

X Exiting due to HOST_VIRT_UNAVAILABLE: Failed to start host: creating host: create: precreate: This computer doesn't have VT-X/AMD-v enabled. Enabling it in the BIOS is mandatory
* Suggestion: Virtualization support is disabled on your computer. If you are running minikube within a VM, try '--driver=docker'. Otherwise, consult your systems BIOS manual for how to enable virtualization.
* Related issues:
  - https://github.com/kubernetes/minikube/issues/3900
  - https://github.com/kubernetes/minikube/issues/4730
  
  
  " Failed to start virtualbox VM. Running "minikube delete" may fix it: creating host: create: precreate: This computer doesn't have VT-X/AMD-v enabled. Enabling it in the BIOS is mandatory "
  
  
  ## SOLUTION 1
  
  λ ```minikube start --no-vtx-check```
  
  or
  
  ```minikube start --driver=virtualbox --no-vtx-check```
