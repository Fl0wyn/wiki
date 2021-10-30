---
title: Exemples
description: 
published: true
date: 2021-10-30T17:37:24.039Z
tags: 
editor: markdown
dateCreated: 2021-10-30T17:37:24.039Z
---

## Envoyer un mail
```powershell
# Construction du mail
$From = "me@example.com"
$Mdp = "password"
$To = "you@example.com"
$SMTPServer = "smtp.example.com"
$SMTPPort = 587
$Subject = "Hello"
$Body = "World"

# Connexion SMTP
$Username = "admin@example.com"
$PWord = ConvertTo-SecureString –String $mdp –AsPlainText -Force
$Credential = New-Object System.Management.Automation.PSCredential ($Username, $PWord)

Send-MailMessage -SmtpServer $SMTPServer -Port $SMTPPort -To $To -Credential $Credential -From $From -Subject $Subject -Body $Body
```  
