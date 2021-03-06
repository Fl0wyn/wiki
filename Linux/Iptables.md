---
title: Iptables
description: 
published: true
date: 2021-10-30T10:35:50.652Z
tags: 
editor: markdown
dateCreated: 2021-10-29T17:50:17.711Z
---

## Installation sur Debian
```bash
apt install iptables ipset
```

## Configuration
1. Copier la listes des règles iptables dans le fichier `/root/firewall.sh` et les modifier puis le rendre éxécutable
```bash
curl -L https://git.io/JeSL5 > /root/firewall.sh
chmod +x /root/firewall.sh
```
2. Tester et vérifier l'exécution du script
```bash
bash /root/firewall.sh
iptables -L
```

3. Rendre les règles non-volatiles
```bash
iptables-save > /etc/firewall.conf
```

4. Ouvrez `/etc/network/if-up.d/iptables` et ajoutez ce qui suit
```bash
#!/bin/bash
iptables-restore < /etc/firewall.conf
```

5. Le rendre exécutable
```bash
chmod +x /etc/network/if-up.d/iptables
```

## Administration
Modifier les Règles
```bash
vim /root/firewall.sh
bash /root/firewall.sh
iptables-save > /etc/firewall.conf
```

Voir les IP bannies depuis le fichier `banip.txt`
```bash
iptables -L INPUT -nv --line-numbers | grep DROP
```

Voir les IP bannies depuis ipset
```bash
ipset -L
```

> Créer un fichier `banip.txt` et ajouter des ip à bannir manuelement
{.is-info}
