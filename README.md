# AzureImageBuilder
Image Builder in Azure for VM Templates

Image Builder setup Using PowerShell 

**Step 1: Install required Modules**

Install-Module -Name  'Az.ImageBuilder'
Install-Module -Name 'Az.ManagedServiceIdentity'
![image](https://user-images.githubusercontent.com/102250876/162425567-aa1d3da7-a0bc-43b6-995a-0aa00b5fd441.png)

**Step 2: Register features required**

**#Register VM Template Preview feature**

Register-AzProviderFeature -ProviderNamespace Microsoft.VirtualMachineImages -FeatureName VirtualMachineTemplatePreview
![image](https://user-images.githubusercontent.com/102250876/162425698-01981f4f-4170-4b40-9c99-e0c904fd06ab.png)
Wait for that to change from registering state to registered state, it will take some time. You can monitor its status by using below command

Get-AzProviderFeature -ProviderNamespace Microsoft.VirtualMachineImages -FeatureName VirtualMachineTemplatePreview
![image](https://user-images.githubusercontent.com/102250876/162425905-cc610450-b907-4e04-a8ef-0d041020816c.png)
![image](https://user-images.githubusercontent.com/102250876/162425947-f6526d26-c297-4fcb-8cb5-5b000db860aa.png)

**# Register resource providers**

Get-AzResourceProvider -ProviderNamespace Microsoft.Compute, Microsoft.KeyVault, Microsoft.Storage, Microsoft.VirtualMachineImages |
Where-Object RegistrationState -ne Registered |
Register-AzResourceProvider
![image](https://user-images.githubusercontent.com/102250876/162426716-446bc468-411e-406f-b59a-69b28258eec0.png)

Adding Changes from VS Code Using Myfirst-feature Branch
sdlkajsf
