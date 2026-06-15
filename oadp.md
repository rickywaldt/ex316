# OADP for Virtual Machines

OpenShift APIs for Data Protection.

Velero is the core upstream tool for backup and restore operations.

A CSI snapshot typically lives on the local storage cluster. Data Mover is an OADP feature that uses Kopia to upload the CSI snapshot to a backup location like an S3 bucket.

This is important for disaster recovery. If the storage cluster dies, then the snapshot goes with it.

Another benefit of Kopia is that it maintains a backup repository and it is aware of what has already uploaded from the previous backup. Meaning, Data Mover via Kopia enables incremental backups that is much faster and require less storage. CSI snapshot alone cannot do this.

Velero talks to the Kubernetes CSI Snapshot API and the request goes to the CSI plug-in (e.g. Ceph) which creates the CSI volume snapshot. Data Mover then uses Kopia to read the data from the volume snapshot and uploads it to object storage.

The process is as follows:

1. Read - Reads the data from the CSI volume snapshot.
2. Deduplicate - Splits the data into chunks, then check already uploaded chunks, and only process the new chunks.
3. Compress - Compresses the new chunks to reduce size.
4. Encrypt - Encrypts the compressed chunks.
5. Upload - Uploads the chunks to object storage.

Velero backs up the K8s resources and packages them into a tar archive and uploads to object storage. This is the desired (spec) and actual (status) state as described in the resource definitions stored in etcd.

So both the backed up resource definitions + the Data Mover gives a complete restorable disaster-proof backup
