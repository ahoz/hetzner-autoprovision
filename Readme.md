# Provision VMs on Hetzer using Terraform and Ansible

## Requirements

- Terraform (Master Branch: v0.13)
- Ansible
- Hetzner
- Hetzner Cloud Api Token

## Configure variables

Move *variables.tf.example* to *variables.tf*. All variables in _variables.tf_ needs to be set in order to provision vm's. 

| Field                     | Description                                                  |
| ------------------------- | ------------------------------------------------------------ |
| hcloud_token              | Your Hetzner cloud project api token                         |
| ssh_key                   | Your SSH key Name stored in your Hetzner cloud project       |
| hcloud_ssh_key_local_path | SSH root user key file path on your client                   |
| server_count              | Number of nodes you want to provision (max 100 nodes)        |
| server_name               | Server name. (Used as prefix on multi-node provisions)       |
| root_password             | Node root password                                           |
| ssh_user_username         | New ssh user username                                        |
| ssh_user_password         | New ssh user password                                        |
| ssh_user_keyfile_path     | New ssh user keyfile path                                    |
| ssh_port                  | New ssh port                                                 |
| location                  | Hetzner vm location (https://docs.hetzner.cloud/#locations-get-all-locations) |
| server_type               | Hetzner server type (https://docs.hetzner.cloud/#server-types) |
| image                     | Hetzner image (only ubuntu images supported, https://docs.hetzner.cloud/#images) |

## Custom settings

### Firewall

In order to set custom firewall rules *rules.v4* and *rules.v6* can be edited.

### SSH

In order to set custom SSH settings *sshd_config* can be edited.

## Provisioning

```bash
terraform init
terraform plan
terraform apply
```





