# ansible-docker-nexus
playbook to build nexus server running on docker tls

Role Name
=========

Before running the playbook
- Create hosts file with Server name inside
```
echo "[hosts]
"dds_name" >> hosts
```

TODO
----
- Login - default credentials are admin admin123
- Setup LDAP authentication

TO RUN PLAYBOOK
```
ansible-playbook nexus_playbook.yml -i hosts -u root --extra-vars "dds_name=<server_name> dds_host=<ip>"
```
dds_host = the IP of server
dds_name = server domain name
server_name = nexus-chc / nexus-dfw / nexus-ord

### To start nexus docker container manually
```
mkdir /nexus-data && chown -R 200 /nexus-data
docker run -v /nexus-data:/nexus-data:rw -p 38081:8081 -p 5000:5000 --restart always -d sonatype/nexus3
```
