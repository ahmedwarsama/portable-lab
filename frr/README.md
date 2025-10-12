Run the frr container:
```
docker run -d --name frr \
  --privileged \
  --network k3d-lab1 \
  -v ./frr.conf:/etc/frr/daemons \
  frrouting/frr:latest
```

Configure BGP:
```
docker exec -it frr vtysh
conf t
router bgp 65001
neighbor 172.21.0.2 remote-as 65500
neighbor 172.21.0.3 remote-as 65500
neighbor 172.21.0.4 remote-as 65500
neighbor 172.21.0.5 remote-as 65500
```
