# Universal Messaging deployment in K8S / OCP

deploy-um.yml: plain K8S manifests, which expose a 9000 nsp port as well as a 9001 nhp port, translated into port 80 at service level.

To activate the 9001 nhp port, use the following command:
`kubectl exec -it umserver-0 -- runUMTool.sh AddHTTPInterface -rname=nsp://localhost:9000 -adapter=0.0.0.0 -port=9001`

um-values.yaml: deployment using a Helm chart, only exposing a 9000 nsp port.

