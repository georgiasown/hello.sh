# internally developed programs/scripts

Q: Where do I install internally written programs/scripts?

A: Here!

## A suggested process that should allow for both ease of usage and flexibility

- we want our programs to run naturally
- we may need to have flexibility on the storage location, due to things such as containerization / cloud datastores etc.

This folder houses internally developed scripts and programs for $myorgdir.
This folder is meant to house production version of internally developed programs
for system-wide (usr/local/bin) or root (usr/local/sbin) use.
The scripts can be linked to directories to place them on the path or lib location
e.g. usr/local/bin, usr/local/sbin, usr/local/lib

## example installation

```shell
#set myorgdir variable to match your actual environment for example "/some/companyname"
myorgdir=actualfoldernamehere
#get local script
sudo curl --output "$myorgdir/usr/local/bin/hello.sh" \
 --location "https://github.com/georgiasown/hello.sh/raw/main/hello.sh"
#show in filesystem
sudo ls -al $myorgdir/usr/local/bin/hello.sh
#review the script content
sudo cat $myorgdir/usr/local/bin/hello.sh
#set permissions for all users to execute
sudo chmod a+x $myorgdir/usr/local/bin/hello.sh
#show new permissions
sudo ls -al $myorgdir/usr/local/bin/hello.sh
#link it to make it available in path
sudo ln -s $myorgdir/usr/local/bin/hello.sh /usr/local/bin/hello.sh
#show link
ls -al /usr/local/bin/hello.sh
#run it
hello.sh
```

## example uninstall

```shell
#set myorgdir variable to match your actual environment for example "/some/companyname"
myorgdir=actualfoldernamehere
#remove the symlinked version from path
sudo rm /usr/local/bin/hello.sh
#remove the program from $myorgdir completely...
sudo rm $myorgdir/usr/local/bin/hello.sh
```
