# Image Definitions

Image definition files (named `imagedefinition.yaml`) are synced into DevCenter projects and built into actual Image Definitions. Once the images are created, Dev Box Pools can be created on top of these images.

> **Note:** Dev Box Pools will fail creation if the Image Definition generation fails.

Once a Dev Box Pool is successfully created, users can then create Dev Box instances from those images.

---

## Folder Structure & Contents

- **platform-developer-build/**
  - `imagedefinition.yaml`: Image definition for the Platform Developer Build.

- **platform-developer-build-minimum-tools/**
  - `imagedefinition.yaml`: Image definition for the Platform Developer Build with minimum tools.

- **platform-ux-build/**
  - `imagedefinition.yaml`: Image definition for the Platform UX Build.

---

Each folder contains an `imagedefinition.yaml` file that defines the configuration for a specific Dev Box image.

**Note:"" At time of writing there was an issue with the platform-developer-build image defintion.  When adding custom tasks into the defintion files there were inconsistent issues in that either the Dev Box Pool would fail to create or a BAD GATEWAY failure would occur when the user tried to build the Dev Box instance.  As a workaround a Dev Box Pool can be created that targets the AdditionalImages/VS2006-Image-Definition image rather than the platform-developer-build image defintion file and then when the user creates the DevBox apply a user customization file that contains any additional installation tasks.  [See also: User Customization Files README](../user_customization_files/README.md)