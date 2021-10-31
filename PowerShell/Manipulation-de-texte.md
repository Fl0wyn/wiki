---
title: Manipulation de texte
description: 
published: true
date: 2021-10-31T17:12:43.115Z
tags: 
editor: markdown
dateCreated: 2021-10-31T15:29:54.477Z
---

## Select-Object
|:computer:|:newspaper:|
|-|-|
|`Select-Object -first 1`| Afficher la 1er ligne |
|`Select-Object -last 2`| Afficher les 2 dernières lignes |
|`Select-Object -Property Message`| Afficher le champ "Hello" |

## Select-String
|:computer:|:newspaper:|
|-|-|
|`Select-String -Pattern Hello`| Afficher le mot 'Hello' |
|`Select-String -Pattern Hello -CaseSensitive`| Afficher stictement le mot 'Hello' |

## Split
|:computer:|:newspaper:|
|-|-|
|`("Hello World" | %{$_.Split(' ')[0]}`| Afficher le 1er champ |
|`($abc | Out-String).trim() | %{$_.Split(' ')[-1]}`| Afficher le dernier champ d'un STRING |

## replace
|:computer:|:newspaper:|
|-|-|
|`$abc -replace 'w|\.'`| Supprimer les caractères 'w' et '.' |