# Rook

Examples from git clone --single-branch --branch v1.5.9 https://github.com/rook/rook.git

lsblk
NAME                                                                                                  MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
loop0                                                                                                   7:0    0   55M  1 loop /snap/core18/1880
loop1                                                                                                   7:1    0 71.3M  1 loop /snap/lxd/16099
loop2                                                                                                   7:2    0 29.9M  1 loop /snap/snapd/8542
sr0                                                                                                    11:0    1 1024M  0 rom
vda                                                                                                   252:0    0   45G  0 disk
├─vda1                                                                                                252:1    0    1M  0 part
├─vda2                                                                                                252:2    0    1G  0 part /boot
└─vda3                                                                                                252:3    0   44G  0 part
  └─ubuntu--vg-ubuntu--lv                                                                             253:0    0   22G  0 lvm  /
vdb                                                                                                   252:16   0   50G  0 disk

Install rook:
```
cd rook/cluster/examples/kubernetes/ceph
kubectl create -f crds.yaml -f common.yaml -f operator.yaml
kubectl create -f cluster.yaml
```

Storage:
```
kubectl create -f storageclass.yml
```

Rook tools:
```
kubectl create -f toolbox.yml
```

MySQL demo:
```
kubectl create -f mysql-demo.yaml
```

# object storage

Create object storage:
```
kubectl create -f 
```

Create user:
```
radosgw-admin user create --uid rook-user --display-name "A rook rgw User" --rgw-realm=my-store --rgw-zonegroup=my-store
```

Export variables
```
export AWS_HOST=
export AWS_ENDPOINT=
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
```
