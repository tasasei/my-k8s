Add this to `~/.bashrc`
```
export WORDPRESS_PASSWORD=$(kubectl get secret --namespace public wordpress -o jsonpath="{.data.wordpress-password}" | base64 -d)
export WORDPRESS_MARIADB_ROOT_PASSWORD=$(kubectl get secret --namespace public wordpress-mariadb -o jsonpath="{.data.mariadb-root-password}" | base64 -d)
export WORDPRESS_MARIADB_PASSWORD=$(kubectl get secret --namespace public wordpress-mariadb -o jsonpath="{.data.mariadb-password}" | base64 -d)
export WORDPRESS_MARIADB_PVC=$(kubectl get pvc -n public -l app.kubernetes.io/instance=my-wordpress,app.kubernetes.io/name=mariadb,app.kubernetes.io/component=primary -o jsonpath="{.items[0
].metadata.name}")
```
export WORDPRESS_PASSWORD=$(kubectl get secret --namespace public my-wordpress -o jsonpath="{.data.wordpress-password}" | base64 -d)
export WORDPRESS_MARIADB_ROOT_PASSWORD=$(kubectl get secret --namespace public my-wordpress-mariadb -o jsonpath="{.data.mariadb-root-password}" | base64 -d)
export WORDPRESS_MARIADB_PASSWORD=$(kubectl get secret --namespace public my-wordpress-mariadb -o jsonpath="{.data.mariadb-password}" | base64 -d)
export WORDPRESS_MARIADB_PVC=$(kubectl get pvc -n public -l app.kubernetes.io/instance=my-wordpress,app.kubernetes.io/name=mariadb,app.kubernetes.io/component=primary -o jsonpath="{.items[0].metadata.name}")