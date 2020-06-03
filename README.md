# aws-tf-workspace
Terraform workspace deployed in AWS with Terraform and awscli

# deploy the workstation with your tool of choice:

# Prerequisites
 - aws credentials
 - aws EC2 SSH keyPair


## TLDR

1) set auto vars
    - admin source address
    - aws key name
    
```bash
    terraform init
    terraform plan
    terraform apply
```
## Options:
- [CFT](https://console.aws.amazon.com/cloudformation/home)

- [Terraform](https://terraform.io)

- [Terraform Cloud](https://app.terraform.io/)

## Variables
- projectPrefix
    - project prefix/tag for all object names
      
      eg: "user-build-sca-"
- awsRegion
    - aws region where build and resources are created
    
        eg: "us-east-1"
- instanceType
    - instance typesize default is 4x16.
    
        eg: "m4.xlarge"
- awsKeyName
    - Existing aws keypair name
    
        eg: "myAws-keyPair"
- adminSrcAddr
    - admin source address https://www.ipchicken.com/ with cidr mask ip/32
    
        eg: "1.1.1.1/32"
- repositories
    - Comma seperated list of repositories to clone

        eg: "https://github.com/f5devcentral/terraform-aws-f5-sca.git,https://github.com/f5devcentral/terraform-aws-bigip.git"
- onboardScript
    - url to onboard script to template

        eg: "https://raw.githubusercontent.com/vinnie357/workspace-onboard-bash-templates/master/terraform/aws/sca/onboard.sh"

## env variables
- AWS_ACCESS_KEY_ID 
- AWS_SECRET_ACCESS_KEY
- AWS_DEFAULT_REGION

## Connect with VS Code Remote Development
- https://code.visualstudio.com/docs/remote/remote-overview

    Open Extensions menu: 

    ![alt text][vscodeExtensions]

    [vscodeExtensions]: images/vscodeExtensions.PNG "vscode extensions"

    Add Remote Devpack Extensions: 

    ![alt text][devPack]

    [devPack]: images/remoteDevPack.PNG "Remote Dev Pack"

    Configure Remote SSH extension: 

    ![alt text][remoteExt] ![alt text][remoteConfig]

    ![alt text][sshConfig]

    [remoteExt]: images/remoteIcon.PNG "Remote SSH icon"

    [remoteConfig]: images/remoteConfig.PNG "Remote SSH config"

    [sshConfig]: images/sshConfig.PNG "SSH config"

## Optional Extensions
- https://marketplace.visualstudio.com/items?itemName=mauve.terraform

## Known issues
- ssh ids on reapply
    ```bash
        @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
        @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
        @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
    ```
    win:
        
        ssh-keygen -f "c:\\Users\\user/.ssh/known_hosts" -R 18.210.163.252
    linux:

        ssh-keygen -f "/root/.ssh/known_hosts" -R 18.210.163.252
- VScode Remote
     
     settings
     
     extensions installed


check for inspect folders
