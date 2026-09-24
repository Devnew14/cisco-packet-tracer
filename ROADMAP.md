# Roadmap Cisco Packet Tracer — Réseaux & Cybersécurité

## 🎯 Objectif

Construire progressivement des laboratoires réseau avec Cisco Packet Tracer afin de maîtriser les bases des réseaux, puis les notions utiles en administration réseau et cybersécurité.

Chaque laboratoire doit contenir :

* une topologie
* une configuration
* des tests
* une vérification du fonctionnement
* une documentation README.md
* un fichier `.pkt`
* un commit Git clair

---

# 🟢 Niveau 1 — Bases réseau

## 01 — Communication LAN ✅

* 2 PC
* 1 switch
* IPv4 statique
* masque de sous-réseau
* câble Ethernet
* `ping`
* `ipconfig`
* simulation Packet Tracer

**Statut : TERMINÉ**

---

## 02 — Routage entre deux réseaux ⬜

Objectifs :

* comprendre le rôle d'un routeur
* créer deux réseaux IP
* configurer les interfaces d'un routeur
* configurer les passerelles
* tester la communication entre deux réseaux

Exemple :

```text
PC1 ─ Switch ─ Router ─ Switch ─ PC2

192.168.1.0/24       192.168.2.0/24
```

Tests :

```text
ping
ipconfig
```

---

## 03 — VLAN ⬜

Objectifs :

* comprendre les VLAN
* créer plusieurs VLAN
* affecter des ports aux VLAN
* comprendre l'isolation réseau

Exemple :

```text
VLAN 10 — Administration
VLAN 20 — Utilisateurs
```

Tests :

* communication entre machines du même VLAN
* absence de communication entre VLAN différents

---

# 🟡 Niveau 2 — Administration réseau

## 04 — Inter-VLAN Routing ⬜

Objectifs :

* permettre la communication entre plusieurs VLAN
* configurer un routeur
* comprendre le principe Router-on-a-Stick
* configurer des sous-interfaces

---

## 05 — DHCP ⬜

Objectifs :

* automatiser l'attribution des adresses IP
* configurer un serveur DHCP
* tester l'obtention automatique d'une IP

Tests :

```text
ipconfig
ipconfig /renew
ping
```

---

## 06 — NAT ⬜

Objectifs :

* comprendre NAT
* configurer NAT statique
* comprendre PAT
* simuler l'accès à un réseau externe

---

# 🟠 Niveau 3 — Sécurité réseau

## 07 — ACL ⬜

Objectifs :

* filtrer le trafic
* autoriser certaines communications
* bloquer certaines communications
* comprendre les ACL Cisco

Exemple :

```text
VLAN Administration → Serveur     ALLOW
VLAN Utilisateurs → Serveur       ALLOW
VLAN Utilisateurs → Administration BLOCK
```

Tests :

```text
ping
```

avant et après l'ACL.

---

## 08 — Réseau sécurisé ⬜

Construire un réseau comprenant :

```text
Internet
   │
 Router
   │
 Firewall
   │
 Switch
 ┌─┴─────────────┐
 │               │
VLAN Admin    VLAN Users
 │               │
PC              PC
```

Objectifs :

* segmentation
* filtrage
* ACL
* VLAN
* NAT
* routage

---

# 🔴 Niveau 4 — Projet de synthèse

## 09 — Infrastructure d'entreprise ⬜

Construire une infrastructure complète simulant une petite entreprise.

Exemple :

```text
                    INTERNET
                       │
                     Router
                       │
                    Firewall
                       │
                     Switch
          ┌────────────┼────────────┐
          │            │            │
       VLAN 10      VLAN 20      VLAN 30
       ADMIN        USERS        SERVERS
          │            │            │
        PC/Mgmt       PCs       Web/DNS/DHCP
```

À documenter :

* architecture
* plan d'adressage IP
* VLAN
* routage
* DHCP
* NAT
* ACL
* services
* tests de connectivité
* tests de sécurité
* résultats

---

# 🛡️ Niveau 5 — Lien avec la cybersécurité

Après Packet Tracer, compléter avec des environnements plus réalistes :

## 10 — Wireshark

Apprendre à analyser :

* ARP
* ICMP
* TCP
* UDP
* DNS
* HTTP

---

## 11 — Linux Networking

Pratiquer :

```bash
ip addr
ip route
ping
traceroute
ss
arp
tcpdump
```

---

## 12 — Analyse réseau / SOC

Combiner :

```text
Réseau
   ↓
Trafic
   ↓
Wireshark / tcpdump
   ↓
Logs
   ↓
SIEM
   ↓
Détection
```

Puis éventuellement intégrer les connaissances avec ton projet **Mini-SIEM**.

---

# 📁 Organisation GitHub

Le dépôt doit progressivement devenir :

```text
cisco-packet-tracer/
│
├── README.md
├── ROADMAP.md
│
├── 01-communication-lan/
│   ├── 01-communication-lan.pkt
│   └── README.md
│
├── 02-routage-inter-reseaux/
│   ├── 02-routage.pkt
│   └── README.md
│
├── 03-vlan/
│   ├── 03-vlan.pkt
│   └── README.md
│
├── 04-inter-vlan/
│   ├── 04-inter-vlan.pkt
│   └── README.md
│
├── 05-dhcp/
│   ├── 05-dhcp.pkt
│   └── README.md
│
├── 06-nat/
│   ├── 06-nat.pkt
│   └── README.md
│
├── 07-acl/
│   ├── 07-acl.pkt
│   └── README.md
│
└── 08-reseau-securise/
    ├── 08-reseau-securise.pkt
    └── README.md
```

## 📈 Progression

```text
LAN
 ↓
Routage
 ↓
VLAN
 ↓
Inter-VLAN
 ↓
DHCP
 ↓
NAT
 ↓
ACL
 ↓
Réseau sécurisé
 ↓
Wireshark
 ↓
Linux réseau
 ↓
SOC / SIEM
```

**Principe :** ne pas chercher à tout apprendre en une journée. Pour chaque laboratoire, comprendre le concept, construire le réseau, casser volontairement quelque chose, diagnostiquer l'erreur, corriger, puis documenter.
