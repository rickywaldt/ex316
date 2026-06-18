# Scheduling

## Run strategy

There are four values you could add under the .spec.runStrategy parameter:

- RerunOnFailure: restart if the VM fails.
- Always: ensure the VM is always running.
- Halted: ensure the VM isn't running.
- Manual: no automatic intervention by OpenShift Virt.
