# Rook-Ceph

This deploys Rook-Ceph via Argo CD using the same kustomize app pattern as the other workloads.

## Storage Math (replication size = 3)

- Every volume is replicated across 3 OSDs (`size: 3`).
- Usable capacity is about one-third of total raw disk.
- Example: `3 x 1TB raw` -> about `1TB usable`.
- Example: `6 x 2TB raw` -> about `4TB usable`.

## Disk Placeholders

Disks are intentionally left blank in `cluster.yaml`.

Edit this section and add device names when ready:

```yaml
spec:
  storage:
    nodes:
      - name: node1
        devices:
          - name: /dev/sdb
```

# NOTE: COME BACK TO THIS WHEN I HAVE DEDICATED DISKS
