# Health probes for VM

## ReadinessProbe

If the readinessProbe fails, then the VM's pod is marked as not ready and it is removed from the service endpoints until it's marked as ready again.

## LivenessProbe

If the livenessProbe fails, then the VM is restarted.

## Watchdog

The Linux kernel writes to /dev/watchdog on a regular interval that is less than the timeout. If there's no writes within the interval, the timer expires and the configured action fires, e.g. shutdown.
