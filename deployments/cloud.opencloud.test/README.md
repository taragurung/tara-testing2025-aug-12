

The Keycloak admin account username and password can be found in the `opencloud-keycloak-initial-admin` secret:
```
kubectl get secret opencloud-keycloak-initial-admin -n keycloak \
  -o jsonpath="{.data.username}" | base64 -d; echo

kubectl get secret opencloud-keycloak-initial-admin -n keycloak \
  -o jsonpath="{.data.password}" | base64 -d; echo
```
