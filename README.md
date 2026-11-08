@"
# devops-lab

Local DevOps lab built with Vagrant and VirtualBox: three Rocky Linux 9 VMs for Docker and Ansible practice.

| VM      | IP            | Role                          |
|---------|---------------|-------------------------------|
| control | 192.168.56.10 | Ansible control node, Docker  |
| app1    | 192.168.56.11 | Application host              |
| app2    | 192.168.56.12 | Application host              |

## Usage

    vagrant up        # create and start all VMs
    vagrant ssh control
    vagrant destroy -f

## Notes

- control reaches app1/app2 over SSH with key-based auth (required for Ansible).
- app1 and app2 share the same SSH host key because they are cloned from one box image; this will be fixed with Ansible.
"@ | Set-Content README.md -Encoding utf8