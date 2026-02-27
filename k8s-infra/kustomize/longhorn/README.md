# Longhorn

This deploys Longhorn via Argo CD (app-of-apps pattern).

## Storage Behavior

- Longhorn stores data on node disks under `/var/lib/longhorn` by default.
- Default replica count is usually 3.
- With 3 replicas, usable capacity is approximately one-third of raw disk capacity.

Example:
- `3 x 500Gi raw` across nodes -> about `500Gi usable`.
