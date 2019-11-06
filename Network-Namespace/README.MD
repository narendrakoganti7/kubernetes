## Network Namespace

create network namespace in linux server

`ip netns add namespacename`

List the network namespace

`ip netns`

Check network address

`ip -n namespace link`

List the route in network

`route`

List the route in namesapce network

`ip netns exec web route`

when you create namespace there is no connection to network. so if you want to connect network need to create virtual wire

`ip link add veth-web type veth peer name veth-db`

create connection between veth and namespace

`ip link set veth-web netns web`

link with ip address
`ip -n web addr add 192.168.0.188 dev veth-web`

namespace bring up

`ip -n web link set verth-web up`
