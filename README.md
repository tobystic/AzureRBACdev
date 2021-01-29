# Create a custom Role Definition for Azure Firewall Network Infrastructure admin
 

This RBAC template is a subscription level template that will create a new role definition and role assignemnt for a firewall admin. The action field
may be edited using actions for your custom role and assigning it to a given Principal ID

------------------------------------------------------------------------------------------------------------------------------------------  



This template will enable a firewall admin to create and define an RBAC role (to make changes to a firewall's network infrastructure operations) and will be assignable at the subscription scope.  

The template can be edited for the different admin permission levels using the Actions field to specify permissions.


[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ftobystic%2FAzureRBACdev%2Fmain%2Fazuredeploy.json%3Ftoken%3DABK3IS74XQVGSJ5GY4AODSC7VLFAG)  



You can add/modify/delete as needed. For more information, see [Understand Azure role definitions](https://docs.microsoft.com/azure/role-based-access-control/role-definitions). 
To learn more about how to deploy the template, see the [quickstart](https://docs.microsoft.com/azure/role-based-access-control/custom-roles-template) article.  


*NOTE: Role Definitions use a GUID for the name, this must be unique for every role assignment on the group. 
The roleDefName parameter is used to seed the guid() function with this value, change it for each deployment. 
You can supply a guid or any string, as long as it has not been used before when assigning the role to the resourceGroup.*
