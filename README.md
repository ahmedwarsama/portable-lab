k3d cluster create lab1 \                                    
  --agents 3 \
  --k3s-arg '--flannel-backend=none@server:*' \
  --k3s-arg '--disable-network-policy@server:*' \
  --k3s-arg '--cluster-cidr=192.168.0.0/16@server:*' \
  --k3s-arg "--disable=traefik@server:*" \
  --no-lb
