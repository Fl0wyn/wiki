---
title: Les conditions
description: 
published: true
date: 2021-10-31T17:33:47.725Z
tags: 
editor: markdown
dateCreated: 2021-10-31T17:33:47.724Z
---

## Structure : if
```powershell
If (test) { 
    $Status = "Success"
}
else {
    $Status = "Failed"
} 
```

## Structure :  case
```powershell
switch ( $VARIABLE ) {
    word1 { $Status = 'Success' }
    word2 { $Status = 'Warning' }
} 
```

## Symboles de test
```powershell
-and # ET 
-or # OU
! # INVERSER
```

## Test : Comparaison
|:computer:|:newspaper:|
|-|-|
|`$val1 -eq $val2`| Vérifie si les valeurs sont égales (EQual) |
|`$val1 -ne $val2`| Vérifie si les valeurs sont différents (No Equal)|
|`$val1 -lt $val2`| Vérifie si val1 est inférieur ( < ) à val2 (Lower Than) |
|`$val1 -le $val2`| Vérifie si val1 est inférieur ou égal ( <= ) à val2 (Lower or Equal) |
|`$val1 -gt $val2`| Vérifie si val1 est supérieur ( > ) à val2 (Greater Than) |
|`$val1 -ge $val2`| Vérifie si val1 est supérieur ou égal ( >= ) à val2 (Greater or Equal) |

