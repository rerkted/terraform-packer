# Integrating Packer and Terraform Using Bash to create a AMI

* _Bash_:  To create a key-pair (on Windows needing OpenSSH on the path) for SSH login.

* _Packer_: To build a simple AMI image based on Ubuntu.

* _Terraform_: To upload the public key information to AWS, create a security group allowing SSH access, and launch an EC2 instance based on the AMI that we created using Packer. 

## Usage 

```
git clone https://gitlab.com/ererk/packer-terraform-aws-cdp.git
cd packer-terraform-aws-cdp
terraform init
chmod u+x cloud_CDP.sh
./cloud_CDP.sh
```

You should see the CDP message of the day when the script automatically logs you in.  Note that creating the AMI, deploying it, and logging you in will take some time (typically 5-10 minutes).

## Cleanup

After exiting out of the SSH script, you can use the "destroy.sh" script to delete the resources that Terraform created. You will have to delete AMI creation seperately. 
