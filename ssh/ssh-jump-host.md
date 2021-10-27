# SSH Jump host

If you don't have access to an instance in a private network but you have a
jump host (bastion) with public ip address within the same private network, then
this jump host could be a bridge between you and an an instance

The next command will connect
```bash
ssh -i "<ssh_pem_file>" \
  -o "ProxyCommand ssh -i "<ssh_pem_file>" -W %h:%p <jump_host_user>:<jump_host_ip>" \
  <instance_user>:<instance_host>
ssh -i "aws_ireland.pem" \
  -o "ProxyCommand ssh -i "aws_ireland.pem" -W %h:%p ec2-user@34.240.210.182" \
  ubuntu@10.120.10.160
```
_NOTE_: Be sure, you've added <path_to_ssh_pem_file> to the jump host
and private instances
