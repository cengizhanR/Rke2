# Rke2
Rke2Installation
#RKE2 Instalaltion
#The RKE2 Kubernetes API Server uses port 6443, while the Rancher server will be served via the NGINX Ingress on ports 80 and 443.
# RKE2 will generate one and place it at /var/lib/rancher/rke2/server/node-token
#The RKE2 config file needs to be created manually. You can do that by running touch /etc/rancher/rke2/config.yaml as a privileged user.
#Note that the rke2 server process listens on port 9345 for new nodes to register. 
Two cleanup scripts, rke2-killall.sh and rke2-uninstall.sh, will be installed to the path at:
/usr/local/bin for regular file systems
/opt/rke2/bin for read-only and brtfs file systems
INSTALL_RKE2_TAR_PREFIX/bin if INSTALL_RKE2_TAR_PREFIX is set
A kubeconfig file will be written to /etc/rancher/rke2/rke2.yaml.
A token that can be used to register other server or agent nodes will be created at /var/lib/rancher/rke2/server/node-token
echo -e "[keyfile]\nunmanaged-devices=interface-name:cali*;interface-name:flannel*" > /etc/NetworkManager/conf.d/rke2-canal.conf
systemctl reload NetworkManager
