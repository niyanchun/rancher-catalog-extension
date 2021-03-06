## Harbor 0.5.0 deployment: distributed (revision 0)

This version deploys `Harbor` 0.5.0 on a Cattle cluster.

All hosts have to have the `harbor-log=true` label (the log container needs to be deployed on all of them).

Also, `Traefik` needs to be enabled on one of the host and a proper DNS configuration needs to be in place.  

Last but not least a storage service for named volumes needs to be available (this catalog entry has been tested with `rancher-nfs` which needs to be activated separately and prior to launch the distributed Harbor deployment).

Note that:
- the `IP/Hostname/FQDN` can be arbitrary set but the `(Traefik) domain` parameter needs to be a domain name that resolves to the host where `Traefik` is running
- this catalog entry only supports `http` (`https` access is not supported)
- because only `http` is supported, the Docker Host pulling/pushing from/to Harbor needs to have the `--insecure-registry` flag properly configured

![](https://github.com/niyanchun/rancher-catalog-extension/blob/master/templates/vmware-harbor/1/distributed.png)
