# Azure Cloud Shell / Azure CLI Commands

These commands were used to inspect and inventory the lab resources from Azure Cloud Shell.

## Show the resource group

```bash
az group show \
  --name rg-cloud-security-lab \
  --query "{Name:name,Location:location}" \
  -o table
```

## Inventory resources in the resource group

```bash
az resource list \
  --resource-group rg-cloud-security-lab \
  --query "[].{Name:name,Type:type,Location:location}" \
  -o table
```

> Note: A Linux subnet and NSG were initially staged during the lab, but no Linux VM was deployed. The final documented architecture focuses on the completed Windows environment.
