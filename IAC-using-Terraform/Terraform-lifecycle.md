# Terraform lifecycle

Terraform follows a well-defined lifecycle for managing infrastructure as code. The lifecycle consists of several stages that ensure resources are created, updated, or destroyed in a controlled manner.

Terraform files are written in **hashicorp language(HCL)**

## 1. **Initialization (`terraform init`)**

**eg:** suppose you have created a EKS folder within that you have written a terraforn files which is **main.tf** . The first thing we do when terraform is installed ,
we do Initialzation by using command **`terraform init`**

- Prepares the working directory for Terraform operations.
- Downloads required provider plugins and modules.
- Configures the backend for storing state files.

  ## 2. **Planning (`terraform plan`)**
- Analyzes the existing state and the desired configuration.
- Shows a preview of what actions Terraform will take.
- Helps in reviewing changes before applying them.

  ## 3. **Application (`terraform apply`)**
- Executes the planned changes to create, update, or destroy resources.
- Stores the updated state in the backend.
