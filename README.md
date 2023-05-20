# ansible
```shell
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

# prometheus
```shell
apt install prometheus-node-exporter

curl -s http://127.0.0.1:9100/metrics | curl --data-binary @- http://127.0.0.1:9091/metrics/job/node/instance/"192.168.1.2:9100"
```

# nfs
```shell
# server
sudo apt-get update
sudo apt-get install nfs-kernel-server
sudo mkdir -p /nfs
sudo chown nobody:nogroup /nfs
# Modify the exports file (/etc/exports).
# /nfs    *(rw,sync,no_subtree_check,no_root_squash)
sudo systemctl restart nfs-kernel-server

# client
sudo apt update
sudo apt install nfs-common
sudo mkdir -p /nfs
sudo mount 192.168.1.2:/nfs /nfs
```
