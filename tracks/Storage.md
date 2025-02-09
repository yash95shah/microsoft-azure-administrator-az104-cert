For SAS authorization to work, auth with shared key needs to be enabled.

If firewall is turned ON for storage account, and the VMs are not part of the firewall CIDR, then they won't have private or public access to the storage acocunt and the backup to the storage acc cannot happen for their correspoding storage account.

VHD can be moved to AZ Blob storage using AZCopy make but it needs to be fixed sized. What is it? It is a file format for a VM

---



What is a sync group and what is cloud tiering

which endpoints will the files be available after 24 hr?



---

Azure File Sync can help sync between cloud and Windows servers.

Cloud Tiering will help free up local space by offloading older files in the cloud.

Use cloud backup and disaster recovery and improve local performance.
