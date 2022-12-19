# Commande de base


## Pour Démarrer
### Initialiser un dépot en local
```
git init
```

### Pour rattacher votre dépôt local à un dépot distant
```
git remote add <name_repot> <url_depot_distant>
git remote -v
git push <name_repot> <remote_repot>
```
#git remote -v permet de voir si le dépot est bien raccordé et ou l'on push et on récupère les sources

#### exemple
```
git remote add origin http://github.com/monRepot
git remote -v
git push origin master
```


### Cloner un projet depuis un dépôt distant
```
git clone <url_depot> <repertoire_cible>
```


## Commande pour visualiser, enregistrer des modifications, annuler des actions

### Connaitre le status
#### Voir l'état du fichier modifié, indexé, validé
```
git status
```

```
git status -s
```

#### Les indicateurs
```
' ' = unmodified

M = modified

T = file type changed (regular file, symbolic link or submodule)

A = added

D = deleted

R = renamed

C = copied (if config option status.renames is set to "copies")

U = updated but unmerged

X          Y     Meaning
-------------------------------------------------
         [AMD]   not updated
M        [ MTD]  updated in index
T        [ MTD]  type changed in index
A        [ MTD]  added to index
D                deleted from index
R        [ MTD]  renamed in index
C        [ MTD]  copied in index
[MTARC]          index and work tree matches
[ MTARC]    M    work tree changed since index
[ MTARC]    T    type changed in work tree since index
[ MTARC]    D    deleted in work tree
            R    renamed in work tree
            C    copied in work tree
-------------------------------------------------
D           D    unmerged, both deleted
A           U    unmerged, added by us
U           D    unmerged, deleted by them
U           A    unmerged, added by them
D           U    unmerged, deleted by us
A           A    unmerged, both added
U           U    unmerged, both modified
-------------------------------------------------
?           ?    untracked
!           !    ignored
-------------------------------------------------
```

#### Visualiser ce qui a été modifié mais pas encore indexé
````
git diff
````

#### Visualiser ce qui a été modifié et indexé
````
git diff --staged
````

#### Visualiser ce qui a été indexé jusqu'à maintenant
````
git diff --cached
````

### Ajouter des fichier
#### Ajouter tous les fichiers modifiés
```
git add .
```

#### Ajouter un fichier 
```
git add <chemin_du_fichier\nom_de_fichier>
```

#### Ajouter tous les fichiers d'un certain types exemple  
```
git add *.c
```
```
git add *.cs
```
```
git add *.html
```
etc...

### Valider les fichiers
```
git commit -m "mon message"
```

### Effacer les fichier 
````
git rm <le_fichier> 
````
Il n'y aura plus de suivi de version et sera retiré du dépot. Exemple retirer tous les logs entrés par erreur
````
git rm log/\*.log
````

### Déplacer des fichiers
````
git mv nom_fichier_origine nom_cible
````


### Annuler une actions

````
git commit --amend
````



## Consultation de l'historique
````
git log
````
Logger le minimum d'information
````
git log --pretty=oneline
````
Rajouter un format dans les log
````
git log --pretty=format:"%h - %an, %ar : %s"
````
Intégrer un graphique
````
git log --pretty=format:"%h %s" --graph
````

````
Option Description du formatage
%H Somme de contrôle du commit
%h Somme de contrôle abrégée du commit
%T Somme de contrôle de l’arborescence
%t Somme de contrôle abrégée de l’arborescence
%P Sommes de contrôle des parents
%p Sommes de contrôle abrégées des parents
%an Nom de l’auteur
%ae E-mail de l’auteur
%ad Date de l’auteur (au format de l’option -date=)
%ar Date relative de l’auteur
%cn Nom du validateur
%ce E-mail du validateur
%cd Date du validateur
%cr Date relative du validateur
%s Sujet
````

## Pour avoir de l'aide

````
git help <la_commande>
````

````
git <la_commande> --help
````

````
man git-<la_commande>
````