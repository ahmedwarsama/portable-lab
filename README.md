Install k3d.
```
wget https://github.com/k3d-io/k3d/releases/download/v5.8.3/k3d-linux-amd64
chmod +x k3d-linux-amd64
mv k3d-linux-amd64 /usr/local/bin/k3d
```
Deploy the cluster without flannel and LB since cilium will be used for this.
```
k3d cluster create lab1 \
  --agents 3 \
  --k3s-arg '--flannel-backend=none@server:*' \
  --k3s-arg '--disable-network-policy@server:*' \
  --k3s-arg '--cluster-cidr=192.168.0.0/16@server:*' \
  --k3s-arg "--disable=traefik@server:*" \
  --no-lb
```
