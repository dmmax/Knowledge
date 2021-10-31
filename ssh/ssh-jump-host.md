# How to use SSH Jump host
## Description
If you don't have access to an instance in a private network but you have a
jump host (bastion) with public ip address within the same private network, then
this jump host could be a bridge between you and an an instance

## Syntax to use jump host
```bash
ssh -i "<ssh_pem_file>" \
  -o "ProxyCommand ssh -i "<ssh_pem_file>" -W %h:%p <jump_host_user>:<jump_host_ip>" \
  <instance_user>:<instance_host>
```

_NOTE_: Be sure, you've added <ssh_pem_file> to the jump host and private instances

## Example of using Bastion host to SSH
The next command will connect to the address 10.120.10.160 via jump host
34.240.210.182
```bash
ssh -i "aws_ireland.pem" \
  -o "ProxyCommand ssh -i "aws_ireland.pem" -W %h:%p ec2-user@34.240.210.182" \
  ubuntu@10.120.10.160
```

## SSH command options

* `-i` – a path to a file (private key)
* `-v` – verbose mode
* `-q` – quiet mode
