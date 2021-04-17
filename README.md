# WiX Installer Examples

[![License](https://img.shields.io/github/license/kurtanr/WiXInstallerExamples.svg)](https://github.com/kurtanr/WixInstallerExamples/blob/master/LICENSE)

WiX (Windows Installer XML) is a framework that lets developers create installers (MSIs) for Windows.\
The Repository contains multiple sample installers which demonstrate how to achieve various tasks using WiX.\
Examples use version 3.11.2 of WiX.
</br>
</br>

## How to get WiX

Download binaries using PowerShell from [WiX GitHub](https://github.com/wixtoolset/wix3) (installer is also available):
```PowerShell
$source = 'https://github.com/wixtoolset/wix3/releases/download/wix3112rtm/wix311-binaries.zip'
$destination = Join-Path $PSScriptRoot -ChildPath 'wix311-binaries.zip'
Invoke-WebRequest -Uri $source -OutFile $destination
```

Download from [Chocolatey](https://community.chocolatey.org/packages/wixtoolset):
```
choco install wixtoolset
```

Download [NuGet package](https://www.nuget.org/packages/WiX/):
```
Install-Package WiX
```
</br>

## How to build installers using WiX

Tools that come with WiX are enough to build installers. VisualStudio/MSBuild is not required, but it helps (e.g. IntelliSense support, project templates).\
Extensions that integrate WiX Toolset into Visual Studio [are available](https://marketplace.visualstudio.com/publishers/WixToolset) from Visual Studio 2010 onward.

There are several options for building a WiX project on a machine that does not have 
[WiX Toolset Build Tools](https://marketplace.visualstudio.com/items?itemName=WixToolset.WiXToolset) installed.\
One of them is described here: [Integrating WiX Projects Into Daily Builds](https://wixtoolset.org/documentation/manual/v3/msbuild/daily_builds.html)\
Another is to simply use the [WiX NuGet package](https://www.nuget.org/packages/WiX/) 
(this is what all projects from [01_HelloWorldInstallerUpgradable](01_HelloWorldInstallerUpgradable/) onward use).
</br>
</br>

## List of example projects

|Project/folder name | Description |
|--------------------|-------------|
|[00_HelloWorldInstaller](00_HelloWorldInstaller/) | - minimum installer, not upgradable</br>- does not use [wixproj](https://wixtoolset.org/documentation/manual/v3/msbuild/authoring_first_msbuild_project.html) |
|[01_HelloWorldInstallerUpgradable](01_HelloWorldInstallerUpgradable/) | - minimum installer, upgradable, no ICE warnings</br>- uses wixproj |

## TODO: Planned examples

- x86 and x64 installers
- passing parameters to MSI
- remembering MSI parameters in case of upgrade and repair
- executing custom installer actions
</br>

## Additional reading

- [WiX Toolset Manual](https://wixtoolset.org/documentation/manual/v3/)
- [WiX 3.6: A Developer's Guide to Windows Installer XML](https://github.com/PacktPublishing/WiX-3.6-A-Developer-s-Guide-to-Windows-Installer-XML)
- [ICE Reference](https://docs.microsoft.com/en-us/windows/win32/msi/ice-reference) (ICE = Internal Consistency Evaluators - executed when compiling/linking MSI)
- [Windows Installer Error Messages](https://docs.microsoft.com/en-us/windows/win32/msi/windows-installer-error-messages)
- [MsiExec.exe and InstMsi.exe Error Messages](https://docs.microsoft.com/en-us/windows/win32/msi/error-codes)
- [MsiExec.exe Command-Line Options](https://docs.microsoft.com/en-us/windows/win32/msi/command-line-options)
