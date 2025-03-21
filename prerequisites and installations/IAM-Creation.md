### **Identity and access management**

Root user is a super user which has highest level of privileges, which may even delete aws account. As a devops engineer, we need to use only IAM users .

Through **IAM** we can create **users and user groups**, **grant permission to created users**

IAM is mainly used for **authentication and authorization**

**Role based access control(RBAC)** is mainly used to grant authentication and autherization

## **eg:**
Let's take one small example like **Bank**. Assume you are holding account in a particular bank. When i need to enter a bank security gaurd will check whether you have account in a bank, then he allows., this is called **authentication**.
when you enter into a bank , you have only permission to reach helpdesk this is called **autherization**.
Whereas, **BankManager** has all permissions where he can go to gold secure area, employee area that means he has authentication and authorization.

## **Authentication**: user | user groups
## **Authorization**: Roles | policies (permissions)
when permissions are provided user can do **CRUD** operations in AWS account.

**Administrator access** in giving permissions for full access this is done after creating a user and  in attaching policies 

# **Step-by-Step IAM User Creation**

### **Step 1: Log in to AWS Console**
- Go to [AWS Management Console](https://aws.amazon.com/console/)
- Sign in with your **Root Account**
- Navigate to **IAM Dashboard**

### **Step 2: Open IAM Users Section**
- Click on **Users** in the left navigation pane
- Click **Add User**

### **Step 3: Enter User Details**
- Provide a **User Name** (e.g., `devops-user`)
- Select **AWS Credential Type**:
  - **Access Key – Programmatic Access** (for CLI, SDKs, API access)
  - **Password – AWS Management Console Access** (for GUI access)
- Click **Next**

### **Step 4: Assign Permissions**
- Choose how to set permissions:
  - **Attach Existing Policies Directly** (e.g., `AdministratorAccess`, `PowerUserAccess`, `ReadOnlyAccess`)
  - **Add to a Group** (recommended for better management)
  - **Copy from Another User**
- Click **Next**

### **Step 5: Add Tags (Optional)**
- Assign metadata like `Department: DevOps`, `Project: E-Commerce`
- Click **Next**

### **Step 6: Review and Create User**
- Review all details carefully
- Click **Create User**

### **Step 7: Download Credentials**
- Download the **Access Key ID & Secret Access Key** (if programmatic access is enabled)
- Save these credentials securely (they won’t be shown again)
- Click **Close**
