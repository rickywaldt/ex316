# VM Snapshot

## QEMU guest agent

If you go to the VM overview > diagnostics you will see AgentConnected True. This means that the QEMU guest agent is running. It's important that the status is True if you want to take a snapshot. The agent communicates between the VM and OpenShift, and when you take a snapshot, it will temporarily freezes the OS to ensure that the snapshot is taken in a consistent environment.

If the status is False. You can try to open the console or run ```virtctl console <vm-name>``` and then run ```sudo systemctl start qemu-guest-agent```. Optionally is to take a snapshot when the VM is in a shutdown/stopped state.
