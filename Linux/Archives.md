---
title: Archives
description: 
published: true
date: 2021-10-30T10:35:04.238Z
tags: 
editor: markdown
dateCreated: 2021-10-29T17:39:55.394Z
---

## tar
```bash
# Création
tar cvf archive.tar fichiers/dossiers
tar zcvf archive.tar.gz fichiers/dossiers # gzip

# Extraction
tar xvf archive.tar
tar zxvf archive.tar.gz # gzip
```

## zip
```bash
# Instalaltion sur Debian
apt install zip unzip

# Création
zip archive.zip fichiers
zip -r archive.zip dossiers

# Extraction
unzip archive.zip
```

## rar
```bash
# Instalaltion sur Debian
apt install rar unrar-free

# Création
rar a archive.rar fichiers
rar a -r archive.rar dossiers

# Extraction
unrar x archive.rar
```

## 7z
```bash
# Instalaltion sur Debian
apt install p7zip

# Création
p7zip -k fichiers/dossiers

# Extraction
p7zip -d archive.rar.7z
```

## Fonction
```bash
# Usage: ex <file>
ex ()
{
  if [ -f $1 ] ; then
    case $1 in
      *.tar.bz2)   tar xjf $1   ;;
      *.tar.gz)    tar xzf $1   ;;
      *.bz2)       bunzip2 $1   ;;
      *.rar)       unrar x $1     ;;
      *.gz)        gunzip $1    ;;
      *.tar)       tar xf $1    ;;
      *.tbz2)      tar xjf $1   ;;
      *.tgz)       tar xzf $1   ;;
      *.zip)       unzip $1     ;;
      *.Z)         uncompress $1;;
      *.7z)        7z x $1      ;;
      *)           echo "'$1' cannot be extracted via ex()" ;;
    esac
  else
    echo "'$1' is not a valid file"
  fi
}
```