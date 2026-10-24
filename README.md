# Task 24: Create a Cloud Snapshot or Backup

## Objective
Create an Amazon EBS snapshot to demonstrate cloud backup and recovery.

## AWS Resources
- **Cloud provider:** Amazon Web Services (AWS)
- **Service:** Amazon EC2 / Elastic Block Store (EBS)
- **Instance name:** `veda-task24-backup-demo`
- **Instance type:** `t3.micro`
- **Source volume ID:** `vol-0c86f1aa631c40013`
- **Snapshot name:** `veda-task24-backup-snapshot`
- **Snapshot ID:** `snap-0c8734895c695906d`
- **Source volume size:** 8 GiB
- **Snapshot status:** Completed
- **Snapshot progress:** 100%

## Implementation
1. Launched an Amazon Linux 2023 EC2 instance.
2. Configured an 8 GiB General Purpose SSD (gp3) EBS root volume.
3. Opened the EC2 Volumes page and identified the attached volume.
4. Created an EBS snapshot with a meaningful description and name tag.
5. Verified that the snapshot reached Completed status at 100%.
6. Stopped the EC2 instance to reduce compute charges.

## Recovery Procedure
To recover a disk from the snapshot:

1. Open the AWS EC2 console in the same AWS Region.
2. Navigate to **Elastic Block Store → Snapshots**.
3. Select snapshot `snap-0c8734895c695906d`.
4. Choose **Actions → Create volume from snapshot**.
5. Select a compatible Availability Zone and review the volume settings.
6. Create the new volume and wait until its state is Available.
7. Attach the new volume to a suitable EC2 instance in the same Availability Zone.
8. Follow the operating system's disk and filesystem recovery procedure before accessing the recovered data.

**Note:** Creating a volume from a snapshot restores the disk contents as of the snapshot time. It does not automatically replace the original root disk or guarantee application-level consistency.

## Backup vs. Replication
- **Backup:** A recoverable copy retained for restoration after data loss or accidental changes.
- **Replication:** Maintains another copy of data or a service, often to improve availability and reduce downtime.

A snapshot provides a recovery point but is not, by itself, a complete disaster-recovery strategy.

## Cost Considerations
EBS volumes and snapshots may incur storage charges. The EC2 instance has been stopped to reduce compute charges, but its root volume remains attached and can still incur storage charges. Snapshot storage may also be billable.

## Evidence
The `screenshots/` directory contains the final AWS snapshot evidence.

## Conclusion
Successfully created and verified an Amazon EBS snapshot. Documented the resource identifiers, backup process, recovery steps, and cost considerations.
