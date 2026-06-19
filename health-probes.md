# Health probes for VM

## ReadinessProbe

If the readinessProbe fails, then the VM's pod is marked as not ready and it is removed from the service endpoints until it's marked as ready again.
