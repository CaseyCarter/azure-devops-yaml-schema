---
title: AzurePowerShell@2 - Azure PowerShell v2 task
description: Run a PowerShell script within an Azure environment (task version 2).
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# AzurePowerShell@2 - Azure PowerShell v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run a PowerShell script within an Azure environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Azure PowerShell v2
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@2
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Connection Type. Default: 'ConnectedServiceNameARM'.
    #azureClassicSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Required. Script Type. Default: 'FilePath'.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Script Arguments. 
    #azurePowerShellVersion: 'OtherVersion' # 'LatestVersion' | 'OtherVersion'. Azure PowerShell Version. Default: 'OtherVersion'.
    preferredAzurePowerShellVersion: # string. Required when TargetAzurePs = OtherVersion. Preferred Azure PowerShell Version.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureConnectionType"::: -->
:::moniker range="<=azure-pipelines"

**`azureConnectionType`** - **Azure Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. Type: string. Allowed values: 'ConnectedServiceName', 'ConnectedServiceNameARM'. Default value: 'ConnectedServiceNameARM'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptType`** - **Script Type**<br>
Type: string. Required. Allowed values: 'FilePath', 'InlineScript'. Default value: 'FilePath'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of the script: File Path or Inline Script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **Script Path**<br>
Type: string. Optional. Use when ScriptType = FilePath.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of the script. Should be fully qualified path or relative to the default working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Inline"::: -->
:::moniker range="<=azure-pipelines"

**`Inline`** - **Inline Script**<br>
Type: string. Optional. Use when ScriptType = InlineScript.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the script to execute.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional parameters to pass to PowerShell.  Can be either ordinal or named parameters.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurePowerShellVersion"::: -->
:::moniker range="<=azure-pipelines"

**`azurePowerShellVersion`** - **Azure PowerShell Version**<br>
Input alias: `TargetAzurePs`. Type: string. Allowed values: 'LatestVersion', 'OtherVersion'. Default value: 'OtherVersion'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In case of hosted agents, the supported Azure PowerShell Versions are: 2.1.0, 3.8.0, 4.2.1, 5.1.1 and 6.7.0(Hosted VS2017 Queue).
To pick the latest version available on the agent, select "Latest installed version".

For private agents you can specify preferred version of Azure PowerShell using "Specify version".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preferredAzurePowerShellVersion"::: -->
:::moniker range="<=azure-pipelines"

**`preferredAzurePowerShellVersion`** - **Preferred Azure PowerShell Version**<br>
Input alias: `CustomTargetAzurePs`. Type: string. Required when TargetAzurePs = OtherVersion.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Preferred Azure PowerShell Version needs to be a proper semantic version eg. 1.2.3. Regex like 2.\*,2.3.\* is not supported. The Hosted VS2017 Pool currently supports Azure module versions: 2.1.0, 3.8.0, 4.2.1, 5.1.1 and AzureRM module versions: 2.1.0, 3.8.0, 4.2.1, 5.1.1, 6.7.0.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: azureps |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->