# Screen

## Listes des commandes
|💻|💬|
|-|-|
|`screen -S session1`| Créer un nouveau screen en nommant la session|
|`screen -ls`| Afficher les screen existants|
|`screen -r`| Rattacher un screen existant|
|`screen -r 13313`| Se rattacher au screen 13313 ou session1|
|`screen -d 13313`| Forcer le détachement du screen 13313|
|`screen -wipe`| Supprimer un screen mort|
|`screen -dmS session1 apt update`| Lancer la commande apt update dans la session session1|


## Navigation entre les terminaux
|💻|💬|
|-|-|
|<kbd>CTRL</kbd> + <kbd>a</kbd> suivi de <kbd>d</kbd>| Détacher le screen|
|<kbd>CTRL</kbd> + <kbd>a</kbd> suivi de <kbd>D</kbd>| Quitter le screen|
|<kbd>CTRL</kbd> + <kbd>a</kbd> suivi de <kbd>n</kbd>| Aller au terminal suivant|
|<kbd>CTRL</kbd> + <kbd>a</kbd> suivi de <kbd>p</kbd>| Aller au terminal précédent|
|<kbd>CTRL</kbd> + <kbd>a</kbd> suivi de <kbd>2</kbd>| Aller au terminal 2|
|<kbd>CTRL</kbd> + <kbd>a</kbd> suivi de <kbd>w</kbd>| Lister les terminaux actuels avec leur nom|