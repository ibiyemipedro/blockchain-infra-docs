**DOCKER**

**_Check the logs of a container_**

`docker logs container_name --tail 100 -f`

---

**_SSH_**

**_Generate key pairs ssh_**

`ssh-keygen -t rsa -b 4096 -C "iyouemail"`

---

**_LINUX COMMANDS_**

To view your available disk devices and their mount points (if applicable) to help you determine the correct device name to use. The output of `lsblk` removes the `/dev/ prefix` from full device paths.:

`lsblk`

Display disk usage in a more human-readable format by adding the -h option:

`df -h`

Check the size of items in a directory:

`sudo du`

---

Find file

1. find . -name thisfile.txt

If you need to know how to find a file in Linux called thisfile.txt, it will look for it in current and sub-directories.

2. find /home -name \*.jpg

Look for all .jpg files in the /home and directories below it.

3. find . -type f -empty

Look for an empty file inside the current directory.

4. find /home -user randomperson-mtime 6 -iname ".db"

Look for all .db files (ignoring text case) that have been changed in the preceding 6 days by a user called randomperson.

---

**_MONGODB DOCKER COMMANDS_**
Login to mongodb terminal running on docker
`docker exec -it mongodb mongo`
