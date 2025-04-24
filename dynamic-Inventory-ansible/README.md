# Ansible Dynamic Inventory for AWS EC2

This project demonstrates the use of Ansible's dynamic inventory feature to manage AWS EC2 instances. The dynamic inventory is configured to automatically fetch EC2 instances based on specific filters (e.g., running instances) and tags (e.g., `Name=test`). This makes managing cloud infrastructure easier and more efficient.

## Requirements

- Ansible 2.9 or later
- AWS Access (via environment variables, AWS credentials file, or IAM roles)
- `amazon.aws` Ansible collection (for AWS EC2 dynamic inventory plugin)

## Project Structure

├── ansible.cfg
├── inventory/
│   └── ec2.ini
├── playbooks/
│   └── playbook.yml



# execute playbook  (This will trigger the playbook to target EC2 instances dynamically discovered from AWS using the ec2.ini configuration)

ansible-playbook -i inventory/ec2.ini playbooks/playbook.yml


# with this entire configuration, the dynamic inventroy would look something like below:

[tag_Name_webserver]
instance-public-ip-1
instance-public-ip-2

[tag_Name_db]
instance-public-ip-3

