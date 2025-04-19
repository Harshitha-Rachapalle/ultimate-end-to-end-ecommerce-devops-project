# Connecting Terraform with AWS to Create AWS Resources
terraform  should have user credentials for authentication with AWS
when you run 'terraform apply' command , terraform will make API call with AWS and will create resources.To interact with AWS we need to use access key and secrect access key 
# Install aws cli
### On Windows:
- Download the installer from [AWS CLI Official Site](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- Run the installer and follow the setup instructions.
- Verify installation:
  ```sh
  aws --version
  ```
  # now loginto IAM user

  on right hand side near profile click on security credentials
  - create access key and store or note it somewhere which is very secured and sensitive
 
## **Configure AWS CLI**
- Run the following command to configure AWS credentials:
  ```sh
  aws configure
  ```
- Provide the following details when prompted:
  - AWS Access Key ID
  - AWS Secret Access Key
  - Default region name (e.g., `us-east-1`)
  - Default output format (e.g., `json` or `text`)

**NOTE**: Above command stores AWS credentials in `~/.aws/credentials`, Terraform uses those credentails to interact with AWS.
