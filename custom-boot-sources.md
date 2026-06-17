# Custom Boot Sources

## Golden Images

A golden image is a preconfigured snapshot of a VM that you can use as a boot source to create a VM.

OpenShift can't read QCOW2 format, so we need to create a Custom Golden Image. Simple Containerfile:

```
FROM scratch
ADD --chown=107:107 golden-image.qcow2 /disk/
```

The scratch image is the smallest possible image. Change owner to 107, that is the Qemu guest agent. The golden-image.qcow2 that is locally present in the same directory as this Containerfile, and this will be added or copied to the /disk/ directory.

Now we build and push the image to our registry.

Add the registry URL under "insecureRegistries" after running:
```oc edit hco kubevirt-hyperconverged -n openshift-cnv```
