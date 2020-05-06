# colab_ssh_vscode
Tutorial on how to ssh to colab and use vscode locally\
As colab blocks all incoming connections there is no way to ssh directly.\
Hence we have to use ssh reverse tunneling.

# Step 1
Create your own public facing local server. I used a local ubuntu 18.04 VM for this but in reality anything works.
# Step 2 create your own private public key
Use `ssh-keygen` to create a public-private keypair. Add public key to your local server. A more detailed tutorial can be seen [here](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-1604).
# Step 3
See `colab_ssh_vscode.ipynb`\
On colab:
* Install Openssh server
* Upload private key
* Set root password
* Set up reverse ssh
You can now ssh into colab using 
```
ssh root@localhost -p 9999
```
localhost as it has been forwarded to your local machine
# Step 4 set up vscode
If your server is your personal machine just use vscode remote extension to `ssh root@localhost -p 9999`\
If your server is a vm or another machine you need a [jump-host](https://code.visualstudio.com/blogs/2019/10/03/remote-ssh-tips-and-tricks#_proxycommand)
