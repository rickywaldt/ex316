# Clone

## Sealed clone from golden image

1. From the console stop the VM.
2. Run virtctl guestfs <pvc>.
3. Run virt-sysprep -a /dev/vda.
4. Create a VirtualMachineClone YAML.
5. Apply the YAML.
6. Run virtctl start <vm>.

## Sealed clone from console

After step 3 above:

1. From the console click Actions > Clone.
2. Optionally check "Start VM after creation", click Clone.

## Clone a disk (DataVolume)

1. Create a DataVolume YAML with source.pvc pointing to the source PVC.
2. Run oc apply -f dv.yaml.
3. Run oc get datavolume and wait for Succeeded.
4. Stop the target VM: Actions > Stop.
5. Go to Configuration > Storage > Add disk, select the cloned PVC, set interface to VirtIO, click Save.
6. Start the VM: Actions > Start.
