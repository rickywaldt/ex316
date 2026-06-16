# Restore

When you restore a VM to a new namespace, the VM uses the same MAC address and firmware UUID. Use the following two labels in the restore manifest to generate a new MAC address and firmware UUID:

```velero.kubevirt.io/clear-mac-address: "true"```
```velero.kubevirt.io/generate-new-firmware-uuid: "true"```
