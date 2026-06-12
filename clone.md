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

1. Create a dv template ```oc get dv <dv-name> -o yaml > dv.yaml```.
2. Edit the dv.yaml, then ```oc apply -f dv.yaml```.
3. Stop the target VM from the console or cli.
4. Click on Configuration > Storage > Add disk and select Volume with the cloned pvc and interface VirtIO.
5. Start the VM.
