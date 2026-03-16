# Terraform Modules

This folder contains **reusable Terraform modules** for provisioning infrastructure across multiple cloud platforms, including **AWS, Azure, GCP, and OpenStack**.  

Modules allow you to:

- Standardize infrastructure components across projects  
- Avoid code duplication  
- Make Terraform code easier to maintain and scale  
- Implement best practices in Infrastructure as Code (IaC)

---

## Current Modules

| Module Name       | Purpose                                           | Cloud Providers                  |
|------------------|---------------------------------------------------|---------------------------------|
| `vm-module`       | Provision virtual machines                        | AWS / Azure / GCP / OpenStack   |
| `network-module`  | Create networks, subnets, and routing rules      | AWS / Azure / GCP / OpenStack   |
| `storage-module`  | Create storage resources (S3, Blob, Buckets, Cinder) | AWS / Azure / GCP / OpenStack |
| `security-module` | Security groups, firewall rules, and policies    | AWS / Azure / GCP / OpenStack   |

---

## How to Use a Module

To use a module in your Terraform configuration:

```hcl id="0fzwsb"
module "vm" {
  source        = "../modules/vm-module"
  vm_name       = "VM001"
  instance_type = "t2.micro"
  region        = "ap-south-1"
  ami_id        = "ami-0f5ee92e2d63afc18"
}
