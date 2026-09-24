# Cisco Packet Tracer — Communication LAN

## Objectif

Mettre en place un réseau local simple permettant à deux ordinateurs de communiquer à travers un switch.

## Topologie

PC0 → Switch → PC1

## Configuration

| Équipement | Interface | Adresse IP | Masque |
|---|---|---|---|
| PC0 | FastEthernet0 | 192.168.1.10 | 255.255.255.0 |
| PC1 | FastEthernet0 | 192.168.1.20 | 255.255.255.0 |

## Matériel

- 2 × PC
- 1 × Switch Cisco 2960
- Câbles Copper Straight-Through

## Tests réalisés

### Test 1 — PC0 vers PC1

```text
ping 192.168.1.20