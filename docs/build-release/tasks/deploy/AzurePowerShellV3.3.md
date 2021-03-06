---
title: Azure PowerShell
description: Run a PowerShell script within an Azure environment
ms.topic: reference
ms.prod: devops
ms.technology: devops-cicd
ms.assetid: 72A1931B-EFFB-4D2E-8FD8-F8472A07CB62
ms.manager: dastahel
ms.author: dastahel
ms.date: 05/04/2018
monikerRange: 'VSTS'
---

# Deploy: Azure PowerShell

![](_img/azurepowershell.png) Run a PowerShell script within an Azure environment

## Arguments

<table><thead><tr><th>Argument</th><th>Description</th></tr></thead>
<tr><td>Azure Connection Type</td><td>(Optional) </td></tr>
<tr><td>Azure Classic Subscription</td><td>(Required) Azure Classic subscription to configure before running PowerShell</td></tr>
<tr><td>Azure Subscription</td><td>(Required) Azure Resource Manager subscription to configure before running PowerShell</td></tr>
<tr><td>Script Type</td><td>(Optional) Type of the script: File Path or Inline Script</td></tr>
<tr><td>Script Path</td><td>(Optional) Path of the script. Should be fully qualified path or relative to the default working directory.</td></tr>
<tr><td>Inline Script</td><td>(Optional) Enter the script to execute.</td></tr>
<tr><td>Script Arguments</td><td>(Optional) Additional parameters to pass to PowerShell.  Can be either ordinal or named parameters.</td></tr>
<tr><td>ErrorActionPreference</td><td>(Optional) Select the value of the ErrorActionPreference variable for executing the script.</td></tr>
<tr><td>Fail on Standard Error</td><td>(Optional) If this is true, this task will fail if any errors are written to the error pipeline, or if any data is written to the Standard Error stream.</td></tr>
<tr><td>Azure PowerShell Version</td><td>(Optional) In case of hosted agents, the supported Azure PowerShell Versions are: 2.1.0, 3.8.0, 4.2.1 and 5.1.1(Hosted VS2017 Queue), 3.6.0(Hosted Queue).
To pick the latest version available on the agent, select "Latest installed version".

For private agents you can specify preferred version of Azure PowerShell using "Specify version"</td></tr>
<tr><td>Preferred Azure PowerShell Version</td><td>(Required) Preferred Azure PowerShell Version needs to be a proper semantic version eg. 1.2.3. Regex like 2.\*,2.3.\* is not supported. The Hosted VS2017 Pool currently supports versions: 2.1.0, 3.8.0, 4.2.1, 5.1.1</td></tr>
[!INCLUDE [temp](../_shared/control-options-arguments.md)]
</table>

::: moniker range="vsts"

## YAML snippet

```YAML
# Azure PowerShell
# Run a PowerShell script within an Azure environment
- task: AzurePowerShell@3
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # Optional. Options: connectedServiceName, connectedServiceNameARM
    #azureClassicSubscription: # Required when azureConnectionType == ConnectedServiceName
    #azureSubscription: # Required when azureConnectionType == ConnectedServiceNameARM
    #scriptType: 'FilePath' # Optional. Options: filePath, inlineScript
    #scriptPath: # Optional
    #inline: '# You can write your azure powershell scripts inline here. # You can also pass predefined and custom variables to this script using arguments' # Optional
    #scriptArguments: # Optional
    #errorActionPreference: 'stop' # Optional. Options: stop, continue, silentlyContinue
    #failOnStandardError: false # Optional
    #azurePowerShellVersion: 'OtherVersion' # Optional. Options: latestVersion, otherVersion
    #preferredAzurePowerShellVersion: # Required when azurePowerShellVersion == OtherVersion
```

::: moniker-end

## Q&A

<!-- BEGINSECTION class="md-qanda" -->

<!-- ENDSECTION -->
