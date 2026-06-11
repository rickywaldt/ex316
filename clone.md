# Clone

## Sealed clone from golden image

1. From the console stop the VM.
2. Run virtctl guestfs <pvc>.
3. Run virt-sysprep -a /dev/vda.
4. Create a VirtualMachineClone YAML.
5. Apply the YAML.
6. Run virtctl start <vm>.
