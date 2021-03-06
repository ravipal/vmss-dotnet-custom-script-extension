# VMSS Custom Script Extension for dotnet core

This repo contains scripts to update your Azure Virtual Machine Scale Set model to have dotnet core runtime installed, using VMSS custom script extensions and the dotnet-install script: https://github.com/dotnet/docs/blob/master/docs/core/tools/dotnet-install-script.md

## How this works

The custom script extension for VMSS can download a script and execute it on a VMSS. The Install-DotnetRuntimeVMSS.ps1 script is the script you run to update the VMSS model with this extension. The Install-DotnetVMSS.ps1 script is the script that's downloaded to the VMSS node and executed to do the install. The Install-DotnetVMSS.ps1 also adds the install directory to the system path.

## How to use the extension

1. In the Install-DotnetRuntimeVMSS.ps1 file, you can add parameters to the `$commandToExecute` variable, which will control the version, release channel and install directory for dotnet. Use this for reference: https://github.com/dotnet/docs/blob/master/docs/core/tools/dotnet-install-script.md.

2. Update the VMSS model by running the Install-DotnetRuntimeVMSS.ps1 script.

## Troubleshooting

- dotnet core requirements: https://docs.microsoft.com/en-us/dotnet/core/windows-prerequisites?tabs=netcore2x
- VMSS extension FAQ: https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-faq#extensions