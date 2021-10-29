# SCP command

Syntax
```bash
scp [OPTION] [user@]SRC:]file1 [user@]DEST:]file2
```

where is
* OPTION – options which accept the command: ssh configuration, recursively, etc
* SRC – is a source source host
* DEST – is a destination host

## SCP copy local file to remote system
### SCP copy local file under remote folder
```bash
scp /mnt/test/test.txt ubuntu@10.130.10.10:/home/ubuntu/test_folder/myfile.txt
```
This command will copy `test.txt` to the remote file, you could provide another
name filename for remote system

### SCP copy local file to remote folder
```bash
scp /mnt/test/test.txt ubuntu@10.130.10.10:/home/ubuntu/test_folder
```
This command will copy the `test.txt` under the `test_folder` on remote machine
 with the same filename as original

## SCP copy local folder to remote folder
```bash
scp /mnt/test ubuntu@10.130.10.10:/home/ubuntu/test_folder
```
All files from `/mnt/test` will be copied recursively under the `test_folder`

## SCP copy remote file to local system
```bash
scp ubuntu@10.130.10.10:/home/ubuntu/test_folder/myfile.txt /mnt/test/remote_file.txt
```

## SCP copy files between two remote systems
```bash
scp ec2-user@18.135.23.123:/opt/my_folder/test.txt ubuntu@10.130.10.10:/home/ubuntu/myfile.txt
```

## SCP options
* `-r` – copy recursively
* `-P` – specifing the SSH port (default: 22)
