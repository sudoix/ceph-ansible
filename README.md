# ceph-ansible

https://docs.ceph.com/en/reef/cephadm/install/#cephadm-deploying-new-cluster

First, determine what version of Ceph you wish to install. You can use the releases page to find the latest active releases. For example, we might find that 18.2.1 is the latest active release.

Use curl to fetch a build of cephadm for that release.

```
CEPH_RELEASE=18.2.0 # replace this with the active release
curl --silent --remote-name --location https://download.ceph.com/rpm-${CEPH_RELEASE}/el9/noarch/cephadm
```

Ensure the cephadm file is executable:

```
chmod +x cephadm
```

With cephadm you can install the repo on your OS:

```
./cephadm add-repo --release reef
```

You can find the release name on this link: https://docs.ceph.com/en/latest/releases/

Update the repo and install cephadm:

```
apt update
apt install cephadm
```

```
cephadm bootstrap --mon-ip <server ip> 
```

Add hosts to the cluster:

```
