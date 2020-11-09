# Create a Role Definition for Azure Firewalladmin


[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fsubscription-deployments%2Fcreate-role-def%2Fazuredeploy.json)

This template is a subscription level template that will create a new role definition for a firewall admin. 
The actions include reading and writing to firewall's network infrastructure operations and will be assignable at the subscription scope. 
You can add/modify/delete as needed. For more information, see [Understand Azure role definitions](https://docs.microsoft.com/azure/role-based-access-control/role-definitions). 
To learn more about how to deploy the template, see the [quickstart](https://docs.microsoft.com/azure/role-based-access-control/custom-roles-template) article.

*NOTE: Role Definitions use a GUID for the name, this must be unique for every role assignment on the group. 
The roleDefName parameter is used to seed the guid() function with this value, change it for each deployment. 
You can supply a guid or any string, as long as it has not been used before when assigning the role to the resourceGroup.*
