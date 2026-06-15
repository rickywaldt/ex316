# OADP for Virtual Machines

OpenShift APIs for Data Protection.

Velero is the core upstream tool for backup and restore operations.

A CSI snapshot typically lives on the local storage cluster. Data Mover is an OADP feature that uses Kopia to upload the CSI snapshot to a backup location like an S3 bucket.

This is important for disaster recovery. If the storage cluster dies, then the snapshot goes with it.

Another benefit of Kopia is that it maintains a backup repository and it is aware of what has already uploaded from the previous backup. Meaning, Data Mover via Kopia enables incremental backups that is much faster and require less storage. CSI snapshot alone cannot do this.
