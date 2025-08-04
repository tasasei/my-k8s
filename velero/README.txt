helm repo update
helm upgrade velero vmware-tanzu/velero -f value.yaml --set-file credentials.secretContents.cloud=cr.txt

helm install velero vmware-tanzu/velero -f value.yaml --set-file credentials.secretContents.cloud=cr.txt
