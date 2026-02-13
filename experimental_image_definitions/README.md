# Experimental Image Definitions

This folder contains experimental or in-progress image definition YAML files for Dev Box environments. These files are used to test or prototype new configurations before they are promoted to production image definitions.

## Contents

- Each subfolder contains an `imagedefinition.yaml` file and, optionally, additional configuration files (such as DSC YAMLs or settings files).
- These definitions may change frequently and are not guaranteed to be stable.

## Example Customization File

See below for a sample customization YAML (from `platform_developer_user_customizations_file.yaml`):

```yaml
$schema: "1.0"
name: "platform-developer-user-customizations-file"

tasks:
  - name: winget
    description: "Install Microsoft SQL Server Management Studio 21"
    parameters:
      package: Microsoft.SQLServerManagementStudio.21

  - name: winget
    description: "Install NodeJS"
    parameters:
      package: OpenJS.NodeJS

  - name: winget
    description: "Install Notepad++"
    parameters:
      package: Notepad++.Notepad++

  - name: git-clone
    description: "Clone INSS Digital Platform to c:\\repos"
    parameters:
      repositoryUrl: https://github.com/InsolvencyService/inss-digital-services-platform.git
      directory: c:\repos

  - name: git-clone
    description: "Clone INSS Digital Platform POC to c:\\repos"
    parameters:
      repositoryUrl: https://github.com/InsolvencyService/inss-digital-platform-poc.git
      directory: c:\repos

  - name: git-clone
    description: "Clone INSS Digital Platform Prototypes to C:\\Prototypes"
    parameters:
      repositoryUrl: https://github.com/InsolvencyService/inss-digital-services-prototypes.git
      directory: C:\Prototypes

userTasks:
  - name: winget
    description: "Install Postman"
    parameters:
      package: Postman.Postman

  - name: winget
    description: "Install Microsoft SQLServer 2022 Developer"
    parameters:
      package: Microsoft.SQLServer.2022.Developer
```

---

For more information, see the main `README.md` files in the project root and related folders.