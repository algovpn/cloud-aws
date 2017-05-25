algovpn.cloud-aws
=========

Adds provider support for AWS to AlgoVPN.

Requirements
------------

Ansible 2.2.0

Role Variables
--------------

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `aws_server_name` | algo | The name of the VPN instance. |
| `region` | us-east-1 | The AWS region to deploy the instance in. |
| `aws_access_key` |  | Your AWS Access Key. |
| `aws_secret_key` |  | Your AWS Secret Key. |
| `cloud_providers.ec2.size`| t2.micro|  The EC2 instance size to be used. |
| `ssh_keys_output_path`| ~/.algovpn/configs | Output path for ssh keys.|
| `ec2_vpc_nets.cidr_block`| 172.16.0.0/16 | add additional paths to the user's `PATH` variable (default is empty).|
| `ec2_vpc_nets.subnet_cidr`| 172.16.254.0/23 | add additional paths to the user's `PATH` variable (default is empty).|

Dependencies
------------
All cloud roles should use the algovpn.ssh_keys helper role to manage
SSH keys.

algovpn.ssh_keys

Example Playbook
----------------

    - hosts: localhost
      roles:
         - { role: algovpn.cloud-aws, aws_server_name: algoforme }

License
-------

MIT

Author Information
------------------

AlgoVPN