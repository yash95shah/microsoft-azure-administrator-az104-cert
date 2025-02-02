Azure App Services -

deployment slots change the url of the webapp

all you really need to do is specify the tech stack and the OS

deployment center helps to set up a local git repo and remote it with a url that they have with authenticating over a username/password credential pair.

Run $webApp = Get-AzWebApp -ResourceGroupName \$rsgGroup

infinite loop command to send http request 

while (\$true) { Invoke-WebRequest -Uri  \$webApp.DefaultHostName \}

Go to the Process Explorer to monitor instances and resource utilization.

additional settings custom domains, private endpoints, private dns integration, certifictes,



Azure VMSS :- 

Uniform vs Flex Orchestration

uniform for stateless, identitical instances.
everything managed through the vmss api
max capacity for VMS (with FD guarantees) 100
instances can be all spot or all on-demand. The disks that are supported are managed or unmanaged

flex for ha for identical or different sku and machine types
it offers orchestration management through standard vm apis.
max capacity for VMS (with FD guarantees) 1000
For flex orchestration:
there is a comparison based on whether there is max spreading vs fixed spreading and whether memory preserving updates are supported or not. (B,D,E,F series and max configurability, platformFaultDomainCount =1, G,H,L,M,N do not support )
counts for instances 1000 vs 200, you can mix spot and on-demand instances, GP and specialty SKUs.

The comparison for monitoring application health for flex and availability set - application health extension, for uniform, in addition, the load balancer probe can also be used.
If there is fixed spreading (fault domain) - for flex there can be 2-3 FD spread (depends on regional max) and 1 for zonal deployment, for uniform 2,3,5 FD, 1,5 for zonal deployments, 2-3 FDs depending on regional max for availability sets. Only for flex orchestration can you assign VMs to actual fault domains.

Networking wise, you would need to explicitly set outbound connectivity for flex orchestration.

Creation of the VMSS:-
Azure CLI
az vmss create (orchestration mode flag, admin username flag, generate-ssh-keys flag, vm-sku, image)
az vm list / az vm show
az vmss stop/ az vm deallocate (difference is stopped instances still cost, storage charges)
az vmss update 
az vm disk attach
az vm create with the --vmss flag will attach it to the vmss.
Powershell
New-AzResourceGroup for new resource group creation.
set credentials $cred = Get-Credential
New-AzVmss ` pass in the credential as -Credential $cred
Get-AzVM
Update-VMSS
$vmss=Get-AzVmss and then change the .sku.capacity for the created variable.
Stop-AzVM, Start-AzVmss, Restart-AzVmss