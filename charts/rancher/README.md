helm upgrade -i rancher rancher-2.12.0.tgz \
--set hostname=rancher.local --set bootstrapPassword=admin \
--set replicas=1 --set global.cattle.psp.enabled=false \
--create-namespace -n cattle-system
