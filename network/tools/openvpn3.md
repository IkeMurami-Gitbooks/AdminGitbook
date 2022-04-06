# openvpn3

Консольный клиент OpenVPN Connect

## Install (ubuntu 20.04)

```
# wget https://swupdate.openvpn.net/repos/openvpn-repo-pkg-key.pub
# apt-key add openvpn-repo-pkg-key.pub

$DISTRO = focal
# wget -O /etc/apt/sources.list.d/openvpn3.list https://swupdate.openvpn.net/community/openvpn3/repos/openvpn3-$DISTRO.list
# apt update

# apt install openvpn3
```

&#x20;Supported distributions:

|  **Distribution** |  **Release** |  **Release name** ($DISTRO) |
| ----------------- | ------------ | --------------------------- |
|  Debian           |  9           |  stretch                    |
|  Debian           |  10          |  buster                     |
|  Ubuntu           |  16.04       |  xenial                     |
|  Ubuntu           |  18.04       |  bionic                     |
|  Ubuntu           |  19.10       |  eoan                       |
|  Ubuntu           |  20.04       |  focal                      |
|  Ubuntu           |  20.10       |  groovy                     |

## Usage

```
Добавить серт:
openvpn3 config-import -c test.ovpn [-n NAME]

список: 
openvpn3 configs-list

Старт сессии
openvpn3 session-start -c test.ovpn
```
