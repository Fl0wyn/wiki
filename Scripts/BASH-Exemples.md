---
title: BASH - Exemples
description: 
published: true
date: 2021-10-30T10:33:01.411Z
tags: 
editor: markdown
dateCreated: 2021-10-29T17:35:46.011Z
---

## Liste des packages a installer
```bash
LISTE_DES_PACKAGES_A_INSTALLER=(
    nano
    git
)

apt install ${LISTE_DES_PACKAGES_A_INSTALLER[@]}
dnf install ${LISTE_DES_PACKAGES_A_INSTALLER[@]}
```  

## Format date
```bash
DATE=$(date +%d-%m-%Y)

echo $DATE
```  

## Format de messages
```bash
SUCCES=$(echo -e "[\e[42m\e[1m SUCCÈS \e[0m"])
ERREUR=$(echo -e "[\e[41m\e[1m ERREUR \e[0m"])
AVERTISSEMENT=$(echo -e "[\e[43m\e[1m AVERTISSEMENT \e[0m"])
INFORMATION=$(echo -e "\e[36m\e[1m->\e[0m")

# ✔
# ✘

echo $SUCCES
echo $ERREUR
echo $AVERTISSEMENT
echo $INFORMATION
```  

## Verification acces internet
```bash
ping -q -c 2 cloudflare.com >/dev/null 2>&1

if [ $? -eq 0 ]; then
    echo "up"
else
    echo "down"
fi
```  

## Multi connexion SSH
```bash
LIST=$(
    cat <<EOF
22;pi@192.168.1.10
2222;pi@192.168.1.20
EOF
)

for i in $LIST; do

    iping=$(echo "$i" | cut -d@ -f2)
    ping -c1 $iping &>/dev/null

    if [ $? = 0 ]; then
        issh=$(echo "$i" | tr -s ';' ' ')
        iuser=$(echo "$i" | cut -d'@' -f1 | cut -d';' -f2)
        scp -P $issh:/home/$iuser/
        ssh -p $issh 'touch fichier_test'
    fi

done
```