# Terraform-aws-keypair

# AWS Infrastructure Provisioning with Terraform

## Table of Contents
- [Introduction](#introduction)
- [Usage](#usage)
- [Module Inputs](#module-inputs)
- [Module Outputs](#module-outputs)
- [License](#license)

## Introduction
This project deploys aws infrastructure using Terraform to create aws-keypair .
## Usage
To use this module, you should have Terraform installed and configured for AWS. This module provides the necessary Terraform configuration for creating AWS resources, and you can customize the inputs as needed. Below is an example of how to use this module:
## Examples

## Example: private_key

```hcl
module "private_keypair" {
  source                     = "git::https://github.com/opz0/terraform-aws-keypair.git?ref=v1.0.0"
  name                       = "private-key"
  environment                = "test"
  label_order                = ["name", "environment"]
  create_private_key_enabled = true
  enable_key_pair            = true
}
```

## Example: s3 complete
```hcl
module "public_keypair" {
  source      = "git::https://github.com/opz0/terraform-aws-keypair.git?ref=v1.0.0"
  name        = "public-key"
  environment = "test"
  label_order = ["name", "environment"]
  public_key  = "ssh-rsa FMR8DFXgwM4rLmXdXXXXXXXXXXXXXXXXXXXXXXXXXtYxXSEb66zp8b/ZcICT2kqMC6suEO3U7IG8wasXCoxOyJ5lqBi8xrmQKBgTZKk6EvO9SSpSishpAP2hafnIuP29RqipraT9UvNeMSbM3/OTjV9I2/KHd/YfSzrUQbnQ6zTgNawyZ8CaRo/Intot3HgU/5PsOKPcTlarb0sFXuWDhdcE+/8TPsjFTPOzMFBDr+H11Oq+cxMoQ/YMXLo/KmokM/km/NfLvEvscuDFzA7JLURiaV33MoQxxIfaTwvrQZ9UJ4gdzd4WhF1sVNB3MP7z07I8pBepJVwca1fTWI9hvn6xK3a6nfD6p8gKiP5xlINMZX7Oi9tmhFuv4vxkYiGZvAI12va9InJFZUQEHmJaIr4g7Faczl5oFK6TYc1FRut9ve4v0JKbz7Od3Uwyqd6rSeHxm/obp1E= satish@satish"

}
```

## Module Inputs
- `name`: The name for the key name.
- `environment`: The environment for your application.
- `public_key`:  The public key material.
- For security group settings, you can configure the ingress and egress rules using variables like:

## Module Outputs
- `id` : The key pair name.
- `arn` :  The key pair ARN.
- `private_key_id`:  The key pair ID.
- Other relevant security group outputs (modify as needed).

## Examples
For detailed examples on how to use this module, please refer to the 'examples' directory within this repository.

## Author
Your Name Replace '[License Name]' and '[Your Name]' with the appropriate license and your information. Feel free to expand this README with additional details or usage instructions as needed for your specific use case.

## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/opz0/terraform-aws-keypair/blob/master/LICENSE) file for details.
