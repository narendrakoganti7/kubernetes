## glusterfs setup on ubuntu

In this setup two master servers and 2 client needed.

install glusterfs package in 2 master servers
- setup hosts files for two servers 
- install glusterfs pacakages
- peer the nodes
- create mount point on two nodes
- create gluster volume and start the volume

**Setup hosts file:**
````
vi /etc/hosts
10.0.0.11 node1
10.0.0.12 node2
````
**Install glusterfs server packages for both node1 and node2**
````
apt install software-properties-common
apt update
apt install glusterfs-server -y
````
**peer the nodes**
````
gluster peer probe node2
peer probe: success.
gluster peer status
Number of Peers: 1

Hostname: node2
Uuid: fec0ed55-2848-4656-97ab-45a82baa9538
State: Peer in Cluster (Connected)
````
**create mount point**

simplest way to create mount point , it is just for practice propose.  
````
fdisk /dev/sdb 
mkfs.xfs -i size=512 /dev/sdb1
echo "/dev/sdb1 /export/sdb1 xfs defaults 0 0"  >> /etc/fstab
mount -a
````
**create gluster volume**
````
gluster volume create datavol replica 2 transport tcp node1:/export/appdata/brick/ node2:/export/appdata/brick/
gluster volume status
gluster volume start

root@node1:~# gluster volume start datavol
volume start: datavol: success
root@node1:~# gluster volume status datavol
Status of volume: datavol
Gluster process                             TCP Port  RDMA Port  Online  Pid
------------------------------------------------------------------------------
Brick node1:/export/appdata/brick     49152     0          Y       14487
Brick node2:/export/appdata/brick       49152     0          Y       10194
Self-heal Daemon on localhost               N/A       N/A        Y       14508
Self-heal Daemon on node2               N/A       N/A        Y       10215

Task Status of Volume datavol
------------------------------------------------------------------------------
There are no active volume tasks
````
master replication completed .

### client side configurations:

`apt-get install gluster-client`

**mount gluster filesystem in client**

`mount -t glusterfs node1:/datavol /mnt/glusterfs`


