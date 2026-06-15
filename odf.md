# OpenShift Data Foundation

When you install the ODF operator, you'll get Storage > Object Storage. You will also have the option to create a OBC (Object Storage Claim). It's conceptually similar to a PVC (Persistent Volume Claim) where you request a persistent volume (block or file storage)/mountable disk. With OBC you request object storage/S3-compatible bucket.

This bucket lives inside the cluster. It's essentially onsite S3 object storage. The equivalent is AWS S3 or MinIO/Garage, but these live outside of the cluster.

When you create a OBC, you will also get a secret with the Access Key and Secret Key for the bucket and a configmap with the host/endpoint and bucket name.
