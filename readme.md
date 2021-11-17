# Template readme for "internal programs" folder

<!--might want to leave a copy of this in your "internal programs" folder ($myorgdir) to help others -->

This folder houses internally developed scripts and programs for $myorgdir.
This folder is meant to house production version of internally developed programs
for system-wide (usr/local/bin) or root (usr/local/sbin) use.
The scripts can be linked to directories to place them on the path or lib location
usr/local/bin, usr/local/sbin, usr/local/lib - for example

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
