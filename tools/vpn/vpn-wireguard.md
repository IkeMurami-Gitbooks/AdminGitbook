# VPN WireGuard

Настройка

```
$ sudo apt install wireguard
```

link: [https://www.wireguard.com/quickstart/](https://www.wireguard.com/quickstart/)

`wg` — wireguard configure utility.

## Configure

1. Add new interface: `ip link add dev wg0 type wireguard` (or `wireguard-go wg0`)
2. An IP address and peer can be assigned with ifconfig(8) or ip-address(8): `ip address add dev wg0 192.168.2.1/24`\
   Or, if there are only two peers total, something like this might be more desirable: `ip address add dev wg0 192.168.2.1 peer 192.168.2.2`
3. The interface can be configured with keys and peer endpoints with the included wg(8) utility: `wg setconf wg0 myconfig.conf`\
   or `wg set wg0 listen-port 51820 private-key /path/to/private-key peer ABCDEF... allowed-ips 192.168.88.0/24 endpoint 209.202.254.14:8172`
4. The interface can then be activated with ifconfig(8) or ip-link(8): `ip link set up dev wg0`

There are also the `wg show` and `wg showconf` commands, for viewing the current configuration. Calling `wg` with no arguments defaults to calling `wg show` on all WireGuard interfaces.

## Key Generation

```
$ umask 077
$ wg genkey > privatekey
$ wg pubkey < privatekey > publickey
```

## Use configs

1. Generate key pairs for client and server:

```
SERVER_PRIVKEY=$( wg genkey )
SERVER_PUBKEY=$( echo $SERVER_PRIVKEY | wg pubkey )
CLIENT_PRIVKEY=$( wg genkey )
CLIENT_PUBKEY=$( echo $CLIENT_PRIVKEY | wg pubkey )
```

1. Create server and client configs:

Server (/etc/wireguard/wg0.conf):

```
[Interface]
Address = 10.9.0.1/24
PrivateKey = $SERVER_PRIVKEY
[Peer]
PublicKey = $CLIENT_PUBKEY
AllowedIPs = 10.9.0.2/32
```

Client (/etc/wireguard/wg0.conf):

```
[Interface]
PrivateKey = $CLIENT_PRIVKEY
Address = 10.9.0.2/24
[Peer]
PublicKey = $SERVER_PUBKEY
AllowedIPs = 0.0.0.0/0
Endpoint = 1.2.3.4:51820 # Внешний IP сервера
PersistentKeepalive = 25 
```

1. Up wireguard interface:

Server: `sudo wg-quick up /etc/wireguard/wg0.conf` (we can use `systemd`: `sudo systemctl start wg-quick@wg0.service`)\
Client: `sudo wg-quick up /etc/wireguard/wg0.conf`
