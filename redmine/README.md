Add this to `~/.bashrc`
```sh
export REDMINE_PASSWORD=$(kubectl get secret --namespace default my-redmine -o jsonpath='{.data.redmine-password}' | base64 -d)
export REDMINE_MARIADB_PASSWORD=$(kubectl get secret --namespace default my-redmine-mariadb -o jsonpath='{.data.mariadb-password}' | base64 -d)
export REDMINE_MARIADB_ROOT_PASSWORD=$(kubectl get secret --namespace default my-redmine-mariadb -o jsonpath='{.data.mariadb-root-password}' | base64 -d)
```
