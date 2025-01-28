Recovery Services Vault -- Backup policy type of VM --the instant restore recovery snapshot 7 days, retained until the next available backup gets to be available.

retention range is another configuration-- different backup points daily, weekly -- just like the snapshot backups, these can be set to be retained for however long you need it for.

tiering can also be enabled but will depend on the retention period set.


When you navigate to the VM and there is a Backup blade, you can select the type of consistency. - application or file-system consistency.

Two types of policy sub types - Enhanced or Standard, the enhanced has support for Trusted Launch Azure Vm and support of Ultra Disks and Premium SSD V2.
