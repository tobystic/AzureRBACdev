## Role Based Access Control (RBAC) for Azure Firewall  

&nbsp;  

Network security requirements involve providing limited access and granting administrative permissions to users within a network. Role assignments are the way you control access to Azure back end and infrastructure resources. If the [built-in roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles) do not meet the specific needs of your organization, Azure Role Based Access Control (RBAC) allows account owners to create [custom roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/custom-roles) that an administrator can assign to Users/User groups.  

You can [configure role assignments](https://docs.microsoft.com/en-us/azure/role-based-access-control/role-assignments-steps) after you have defined the scope, either via Azure Portal, PowerShell, CLI or RestAPI.  

In some instances, the built-in roles may be either too permissive or insufficient for the assignment that is required. Access should be provided using the principle of least privilege and every role should be carefully created with the user’s duties in mind, as a security control when creating user privileges. In this situation, you will also need to know what role actions are available.  

In this article, we discuss the actions that may be used to create security conscious roles and templates that you can use to create and assign your role with some examples. Once you understand the boundaries for the role you are trying to create, you can use the template below or modify it by carefully selecting the actions required and assigning it to the user. 

\\insert image

There are various levels of administrative roles you might be looking to assign, and this may be done at a management group level, subscription level, resource group level or resource level. Azure RBAC focuses on managing user [actions](https://docs.microsoft.com/en-us/azure/role-based-access-control/resource-provider-operations)  at these different scopes.  
&nbsp;  

*The following 3 examples are quite common in network scenarios*: 

**Firewall Security Reader role**: This administrator requires mostly reader privileges as maybe required in an auditor role. The permission grants visibility into existing rules and other properties of the firewall. This user is therefore only able to view and not make changes.  


**Firewall Security Administrator role**: This role is assigned to an admin that is responsible for the security configurations in the network. Access control is used to manage connectivity, making sure actions are carefully assigned. This admin can analyze the security risk of each connection via the network and application rules and make changes as required.  

**Network Infrastructure Administrator role**: This role has more overarching rights to change the infrastructure of the firewall from a network operations perspective, but would not necessarily need access to change network and application rules like the security admin. Permissions in this role include [FirewallWallPolicies](https://docs.microsoft.com/en-us/azure/templates/microsoft.network/firewallpolicies#firewallpolicypropertiesformat-object) attributes such as: Threat Intelligence, DNS settings, Intrusion detection etc. 

To create a custom role, you must provide the following input.  

{  

  "DisplayName": "",  
  "Description": "",  
  "Actions": [ ],  
  "NotActions": [ ],  
  "DataActions": [ ],  
  "NotDataActions": [ ],  
  "AssignableScopes": [ ]  
  
  &nbsp;  
    } 
&nbsp;  

You can find the description of each requirement above in this [article](https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azroledefinition?view=azps-4.8.0#description). To configure Azure roles using PowerShell, follow the steps to [create a custom role](https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azroledefinition?view=azps-4.8.0). 

You can click the “Deploy to Azure” button below to deploy a template for the Network infrastructure role discussed above from Github. You can use this custom template by editing the “action” field for the appropriate set of actions list in the samples below. Then provide the Principal ID(Object ID) of the user to assign the role. You can find a detailed [step by step guide here](https://docs.microsoft.com/en-us/azure/firewall-manager/rule-hierarchy#create-custom-roles-to-access-the-rule-collection-groups).  



[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ftobystic%2FAzureRBACdev%2Fmain%2Fazuredeploy.json%3Ftoken%3DABK3IS74XQVGSJ5GY4AODSC7VLFAG)  



You can add/modify/delete as needed. For more information, see [Understand Azure role definitions](https://docs.microsoft.com/azure/role-based-access-control/role-definitions). 
To learn more about how to deploy the template, see the [quickstart](https://docs.microsoft.com/azure/role-based-access-control/custom-roles-template) article.  


*NOTE: Role Definitions use a GUID for the name, this must be unique for every role assignment on the group. 
The roleDefName parameter is used to seed the guid() function with this value, change it for each deployment. 
You can supply a guid or any string, as long as it has not been used before when assigning the role to the resourceGroup.*
