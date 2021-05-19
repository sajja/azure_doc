# Azure Vault





#### Soft delete

With soft delete, even if a malicious actor deletes a backup (or backup  data is accidentally deleted), the backup data is retained for 14  additional days, allowing the recovery of that backup item with no data  loss. The additional 14 days of retention for backup data in the "soft  delete" state don't incur any cost to you.





#### Access policy

1. VMs can be allowed
2. Resouce manager is allowed
3. Disk encryption is allowed



## Key Vault authentication options

1. **Application-only**: each application represent a managed identity, and the KVStore grants `objectId` of the application R/W permssions 
2. **User-only**: KVStore grants access to specific users
3. **Application-plus-user** Both `objectId of the application` and `objectid of the user` needs to be specified.

