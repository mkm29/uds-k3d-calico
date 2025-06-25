# Airgap Flavor

This package can be deployed fully airgapped by using the `airgap` flavor. The airgap deployment process loads images in the following order:

1. **K3d images**: Required for the k3d cluster to spin up, loaded into Docker using `docker load`
2. **Calico CNI images**: All Tigera Operator and Calico component images are loaded into the k3d cluster
3. **UDS Dev Stack images**: MetalLB, NGINX, MinIO, and other dev stack images are loaded using `k3d image load`

## Considerations

The version of `k3s` that is deployed by the `airgap` flavor is static and not configurable. 