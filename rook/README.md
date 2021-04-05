# Rook

Examples from git clone --single-branch --branch v1.5.9 https://github.com/rook/rook.git

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
