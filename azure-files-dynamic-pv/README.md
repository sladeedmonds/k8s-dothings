# Dynamic PersistentVolumeClaim
See https://learn.microsoft.com/en-us/azure/aks/azure-files-dynamic-pv

This example creates dynamic storage and mounts it to a pod.  The storage account doesn't exist prior, hence it is _dynamic_.

Apply with kubectl apply.
1. Create a storage class with azure-file-sc.yaml
2. Create a persistent volume claim with azure-file-pvc.yaml
3. Create a pod that uses the pvc

kubectl get pvc managed-standard-retain should show 'Bound'.
You can confirm the mount with kubectl exec azure-pvc-files-pod -- mount|grep azure