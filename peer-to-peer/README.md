# Peer-to-peer communication

When technology users like you and me want to really _own_ our devices and the way we use them, a big stumbling block is the fact that we can initiate communication, but not respond to communication requests. Only servers can do both. This is not a fundamental constraint of the devices we use, or even of the software that runs on them. It is a constraint of the 'ecosystem' of web-sites and mobile-apps that has grown out of the .com-revolution.

So, to overcome this hurdle, we need to empower our devices with the means to respond directly to requests form other devices, without depending on servers that can (either crudely or subtly) interfere with our communication or mine it for precious data for the A.I.-models that earn them lots of money.

The desire for this capability is not new and already has a name: peer-to-peer communication. There are a few problems with peer-to-peer technology:

* It has a bad name, because it is currently used mostly for illegal sharing of copyrighted data (music, films, books)
* It conflicts with Network Address Translation

The bad name can easily be rectified with proper legal society-building applications.

Network Address translation is a solution to a problem with the most common Internet Protocol, IPv4. The problem being that there are more devices that need an internet-address than there are addresses available. The problematic solution is called Network Address Translation, or NAT. By its very nature a device behind a NAT-router can only receive information from another device on the internet after it has connected with it first. In other words, most devices on the internet cannot respond to incoming requests. Servers use a setup that involves port-forwarding and/or a reverse proxy to get around this, but this is not feasible for all devices like phones and game PC's.

Another solution is simply to use a scheme with more addresses. There is such a protocol, but its adoption is far from universal. This is the successor of IPv4: IPv6 (I have no idea what happened to v5).

I would support the idea that the government mandates providers to offer the possibility to get an IPv6 address for every device that they connect to the internet.

In the current situation, where many devices are still using IPv4 behind a NAT-router, we need to be smart about how we connect to each other.

There is a host of techniques for establishing peer-to-peer connections[[1]](#1):

* UDP-punching / STUN / ICE
  * pwnat tries to do this without a server, but works only with outdated NAT-routers
  * STUN needs a server, but only for negotiating the connection; not for the connection itself
* UPnP IGD / NAT-PMP / PCP
* Relay Server

Neither of these techniques works in every situation though (except Relay Server, but that is a solution that re-introduces the problem we wanted to solve in the first place).

I am currently looking into [libp2p](https://github.com/libp2p/libp2p) to see whether it can be used as a basis for the type of node I have in mind.

I am also looking into [tailscale](https://tailscale.com/) to see whether it can be used to create a cluster using the home-servers of myself and a few friends. The cluster would be connected with peer-to-peer links and also accept peer-to-peer connection requests.
* [Headscale](https://github.com/juanfont/headscale)
* [Multi-tailnet](https://jamesguthrie.ch/blog/multi-tailnet-unlocking-access-to-multiple-tailscale-networks/)

The next step would be to join mesh networks.

* [Radical Data](https://github.com/radical-data/mesh)
* [qaul قول](https://qaul.net/)

----

### 1

[How NAT traversal works](https://tailscale.com/blog/how-nat-traversal-works) David Anderson (Tailscale)

----

### 2

[pwnat](https://github.com/samyk/pwnat)

[udp-puncher](https://github.com/node2own/udp-puncher)