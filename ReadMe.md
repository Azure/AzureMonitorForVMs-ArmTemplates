# ARM Templates to deploy Azure Monitor for VMs

This download contains onboarding templates for different scenarios:

### Virtual Machines:
- ExistingVmOnboarding: Use this template to enable Azure Monitor for VMs if the Virtual Machines already exists.
- NewVmOnboarding: Use this template to create a Virtual Machine and onboard it to Azure Monitor for VMs.

### Virtual Machine Scale Sets:
- ExistingVmssOnboarding: Use this template to enable Azure Monitor for VMs if the Virtual Scale Sets already exists.
- NewVmssOnboarding: Use this template to create a Virtual Machine Scale Sets and onboard it to Azure Monitor for VMs.

> Note: If Virtual Machines Scale Sets are already present and the upgrade policy is set to 'Manual', Azure Monitor for VMs will not be enabled for instances by default after running 'ExistingVmssOnboarding' template. You have Manually upgrade the instances.

### Configure Workspace:
- ConfigureWorkspace: Use this to enable Azure Monitor for VMs solution on the workspace.

## How to Deploy:
Each folder has a 'Template' and a 'Parameters' file.
Modify the 'Parameters' file with appropriate details, such as Virtual Machine Resource Id, Workspace resource Id, Location, OS Type etc. Do not modify the 'Template' file unless you need to customize it for you particular scenario.

Once details are entered in the 'Parameters' file you can deploy them in multiple ways:

#### 1. Using the portal UI:
You can login to Azure Portal and [deploy this Azure Resource Manager template](https://docs.microsoft.com/azure/azure-resource-manager/resource-manager-quickstart-create-templates-use-the-portal) along with modified parameters.

#### 2. Powershell:
If using Powershell, please run the following command:

```sh
New-AzResourceGroupDeployment -Name OnboardCluster -ResourceGroupName <ResourceGroupName> -TemplateFile <Template.json> -TemplateParameterFile <Parameters.json>
```

#### 3. Azure CLI:
If using Azure CLI, please run the following command:

```sh
az login
az account set --subscription "Subscription Name"
az group deployment create --resource-group <ResourceGroupName> --template-file <Template.json> --parameters <Parameters.json>
```

### Links:
[Azure Monitor for VMs (preview)](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-overview)

[Deploy Azure Monitor for VMs (preview)](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-onboard)

[GA FAQ](https://docs.microsoft.comazure/azure-monitor/insights/vminsights-ga-release-faq)
