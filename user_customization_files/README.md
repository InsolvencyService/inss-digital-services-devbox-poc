# User Customization Files

When creating a DevBox instance, you have the option to apply a customization file. This allows you to add additional installation or configuration tasks on top of the selected DevBox image.

For example, you can create a DevBox image that contains only Visual Studio 2026 and VSCode. By applying a customization file, you can automate the installation of additional tools such as Node.js or Notepad++.

## Steps to Create a Custom Developer Image

1. Browse to [https://devbox.microsoft.com](https://devbox.microsoft.com)
2. Click the **New dev box** button in the top left of the page.
3. Enter any name for the DevBox instance.
4. Select an image from the Project list (e.g., `Platform-Developer-Image-8vCPU-32GB-256GB`).
5. Check the **Apply customizations** checkbox.
6. Choose to either upload a customizations YAML file from disk or download from a repository.
7. After uploading, click the **Validate** button.
8. Click the **Create** button.

---

## Example Customization YAML: `my-customization.yaml`

> **Note:**
> - `tasks` will be installed during image creation.
> - `userTasks` will be installed after the user has signed in for the first time after image instance creation. **Warning**, You might need to confirm security dialogs for some installations to succeed, SQL Server is an example of this.

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
    description: "Install Chrome"
    parameters:
      package: Google.Chrome

  - name: winget
    description: "Install Postman"
    parameters:
      package: Postman.Postman

  - name: ~/winget
    description: "Install Microsoft SQLServer 2022 Developer"
    parameters:
      package: Microsoft.SQLServer.2022.Developer
```   
