oc create secret docker-registry ibm-regcred --docker-server=cp.icr.io --docker-username=cp --docker-password=${IBM_CR_PASSWORD}

oc adm policy add-scc-to-user privileged -z umserver-sa

helm upgrade --install umserver webmethods/universalmessaging -f ./um-values.yaml
