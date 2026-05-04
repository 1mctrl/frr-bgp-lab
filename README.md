```
  bsh icon dockerLab  frr + 
   docker exec -it frr-r1 vtysh

Hello, this is FRRouting (version 10.5.4_git).
Copyright 1996-2005 Kunihiro Ishiguro, et al.

1ee7872193eb# show ip bgp summary

IPv4 Unicast Summary:
BGP router identifier 1.1.1.1, local AS number 65001 VRF default vrf-id 0
BGP table version 3
RIB entries 5, using 640 bytes of memory
Peers 2, using 33 KiB of memory

Neighbor        V         AS   MsgRcvd   MsgSent   TblVer  InQ OutQ  Up/Down State/PfxRcd   PfxSnt Desc
10.0.12.2       4      65002        10        11        3    0    0 00:04:30            2        3 N/A
10.0.13.2       4      65003        10        10        3    0    0 00:04:30            2        3 N/A

Total number of neighbors 2
1ee7872193eb# show ip route
Codes: K - kernel route, C - connected, L - local, S - static,
       R - RIP, O - OSPF, I - IS-IS, B - BGP, E - EIGRP, N - NHRP,
       T - Table, v - VNC, V - VNC-Direct, A - Babel, F - PBR,
       f - OpenFabric, t - Table-Direct,
       > - selected route, * - FIB route, q - queued, r - rejected, b - backup
       t - trapped, o - offload failure

IPv4 unicast VRF default:
K>* 0.0.0.0/0 [0/0] via 172.21.0.1, eth0, weight 1, 00:04:35
L * 1.1.1.1/32 is directly connected, lo, weight 1, 00:04:34
C>* 1.1.1.1/32 is directly connected, lo, weight 1, 00:04:34
B>* 2.2.2.2/32 [20/0] via 10.0.12.2, eth0, weight 1, 00:04:32
B>* 3.3.3.3/32 [20/0] via 10.0.13.2, eth1, weight 1, 00:04:32
C>* 10.0.12.0/24 is directly connected, eth0, weight 1, 00:04:34
L>* 10.0.12.1/32 is directly connected, eth0, weight 1, 00:04:34
C>* 10.0.13.0/24 is directly connected, eth1, weight 1, 00:04:34
L>* 10.0.13.1/32 is directly connected, eth1, weight 1, 00:04:34
C>* 172.21.0.0/16 is directly connected, eth0, weight 1, 00:04:35
L>* 172.21.0.2/32 is directly connected, eth0, weight 1, 00:04:35
C>* 172.23.0.0/16 is directly connected, eth1, weight 1, 00:04:35
L>* 172.23.0.3/32 is directly connected, eth1, weight 1, 00:04:35
1ee7872193eb# exit
```

```
  bsh icon dockerLab  frr + 
   docker exec -it frr-r2 vtysh

Hello, this is FRRouting (version 10.5.4_git).
Copyright 1996-2005 Kunihiro Ishiguro, et al.

71944d37f27d# show ip bgp summary

IPv4 Unicast Summary:
BGP router identifier 2.2.2.2, local AS number 65002 VRF default vrf-id 0
BGP table version 3
RIB entries 5, using 640 bytes of memory
Peers 2, using 33 KiB of memory

Neighbor        V         AS   MsgRcvd   MsgSent   TblVer  InQ OutQ  Up/Down State/PfxRcd   PfxSnt Desc
10.0.12.1       4      65001        10        10        3    0    0 00:04:53            2        3 N/A
10.0.23.3       4      65003        10        10        3    0    0 00:04:53            2        3 N/A

Total number of neighbors 2
71944d37f27d# show ip route
Codes: K - kernel route, C - connected, L - local, S - static,
       R - RIP, O - OSPF, I - IS-IS, B - BGP, E - EIGRP, N - NHRP,
       T - Table, v - VNC, V - VNC-Direct, A - Babel, F - PBR,
       f - OpenFabric, t - Table-Direct,
       > - selected route, * - FIB route, q - queued, r - rejected, b - backup
       t - trapped, o - offload failure

IPv4 unicast VRF default:
K>* 0.0.0.0/0 [0/0] via 172.21.0.1, eth0, weight 1, 00:04:58
B>* 1.1.1.1/32 [20/0] via 10.0.12.1, eth0, weight 1, 00:04:55
L * 2.2.2.2/32 is directly connected, lo, weight 1, 00:04:57
C>* 2.2.2.2/32 is directly connected, lo, weight 1, 00:04:57
B>* 3.3.3.3/32 [20/0] via 10.0.23.3, eth1, weight 1, 00:04:55
C>* 10.0.12.0/24 is directly connected, eth0, weight 1, 00:04:57
L>* 10.0.12.2/32 is directly connected, eth0, weight 1, 00:04:57
C>* 10.0.23.0/24 is directly connected, eth1, weight 1, 00:04:57
L>* 10.0.23.2/32 is directly connected, eth1, weight 1, 00:04:57
C>* 172.21.0.0/16 is directly connected, eth0, weight 1, 00:04:58
L>* 172.21.0.3/32 is directly connected, eth0, weight 1, 00:04:58
C>* 172.22.0.0/16 is directly connected, eth1, weight 1, 00:04:58
L>* 172.22.0.2/32 is directly connected, eth1, weight 1, 00:04:58
71944d37f27d# exit
```

```
  bsh icon dockerLab  frr + 
   docker exec -it frr-r3 vtysh

Hello, this is FRRouting (version 10.5.4_git).
Copyright 1996-2005 Kunihiro Ishiguro, et al.

8ddeecd49a05# show ip bgp summary

IPv4 Unicast Summary:
BGP router identifier 3.3.3.3, local AS number 65003 VRF default vrf-id 0
BGP table version 3
RIB entries 5, using 640 bytes of memory
Peers 2, using 33 KiB of memory

Neighbor        V         AS   MsgRcvd   MsgSent   TblVer  InQ OutQ  Up/Down State/PfxRcd   PfxSnt Desc
10.0.13.1       4      65001        11        12        3    0    0 00:05:04            2        3 N/A
10.0.23.2       4      65002        11        12        3    0    0 00:05:04            2        3 N/A

Total number of neighbors 2
8ddeecd49a05# show ip route
Codes: K - kernel route, C - connected, L - local, S - static,
       R - RIP, O - OSPF, I - IS-IS, B - BGP, E - EIGRP, N - NHRP,
       T - Table, v - VNC, V - VNC-Direct, A - Babel, F - PBR,
       f - OpenFabric, t - Table-Direct,
       > - selected route, * - FIB route, q - queued, r - rejected, b - backup
       t - trapped, o - offload failure

IPv4 unicast VRF default:
K>* 0.0.0.0/0 [0/0] via 172.23.0.1, eth0, weight 1, 00:05:10
B>* 1.1.1.1/32 [20/0] via 10.0.13.1, eth0, weight 1, 00:05:07
B>* 2.2.2.2/32 [20/0] via 10.0.23.2, eth1, weight 1, 00:05:07
L * 3.3.3.3/32 is directly connected, lo, weight 1, 00:05:09
C>* 3.3.3.3/32 is directly connected, lo, weight 1, 00:05:09
C>* 10.0.13.0/24 is directly connected, eth0, weight 1, 00:05:09
L>* 10.0.13.2/32 is directly connected, eth0, weight 1, 00:05:09
C>* 10.0.23.0/24 is directly connected, eth1, weight 1, 00:05:09
L>* 10.0.23.3/32 is directly connected, eth1, weight 1, 00:05:09
C>* 172.22.0.0/16 is directly connected, eth1, weight 1, 00:05:10
L>* 172.22.0.3/32 is directly connected, eth1, weight 1, 00:05:10
C>* 172.23.0.0/16 is directly connected, eth0, weight 1, 00:05:10
L>* 172.23.0.2/32 is directly connected, eth0, weight 1, 00:05:10
8ddeecd49a05# exit
```
