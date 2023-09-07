---
style: dev
title: Atelier terminal
type: Atelier
---

# Voyage au centre de l'ordinateur

[⬅ English version](./)

Tu as déjà pu découvrir lors des quêtes et lors du cours une tonne de commande utile dans la
console.<br>
Le problème, c’est qu’il va t’être difficile de retenir tout ça en si peu de temps !

Pas de stress, dans cet atelier tu vas juste te balader tranquillement dans ton ordinateur, en
utilisant uniquement la console.<br>
Tu peux donc fermer ton gestionnaire de fichier, il te sera totalement inutile pour ce voyage :
lance la Console (appelée Terminal en anglais) et laisse-toi guider !

Si tu es sous Windows, utilise la console `git bash`
{: .alert-warning }

## Avant de voyager, visite ta propre maison !

Si tu viens juste d’ouvrir la console, tu devrais te trouver chez toi, dans ton dossier utilisateur.<br>
Pour être sûr de ça, tu peux exécuter la commande suivante :<br>

```bash
cd ~
```

- la commande `cd` signifie change directory
- le tilde `~` est un raccourci vers ton dossier utilisateur.

Cette commande est sensée accéder à un dossier, mais si tu l’exécutes avec le paramètre `~`,
elle te permet de te téléporter dans ta maison !<br><br>
Tu devrais observer une invite de commande qui ressemble plus ou moins à ça :<br>

```bash
wilder@wilder-ThinkPad-T430:~$
```

- Le premier élément avant le `@`, c’est toi ! (ton nom d’utilisateur).
- Le second élément après le `@` jusqu’aux deux points `:`, c’est le nom de ton
  ordinateur. - Après les `:`, se trouve ta position dans l’ordinateur (ici le tilde `~`).
- Après le `$` se trouveront les commandes que tu pourras tapper !

Attention, ton dossier utilisateur ne correspond pas à l’endroit le plus profond de ton ordinateur
(appelé la racine) !

Si tu veux connaître le chemin réel qui mène jusqu’à ton dossier utilisateur, tu peux utiliser la
commande suivante :

```bash
pwd
```

La commande `pwd` sert à afficher le chemin réel du dossier où tu te trouves.<br>
Ici tu es donc dans ton dossier utilisateur, représenté par le tilde `~`, le chemin qui
apparaît est probablement le suivant :

```bash
/home/wilder
```

- `/home/` contient tous les dossiers utilisateurs de cet ordinateur
- `wilder` (ou ton nom d’utilisateur) qui contient ton dossier utilisateur !

Sur Windows et OSX le chemin ne sera pas le même, mais tu observeras une assez grosse
ressemblance !
{: .alert-warning }

## Connaître ses racines

Maintenant que tu connais le chemin (appelé `path` en anglais) vers ton dossier utilisateur,
observons-le de nouveau.

Tu peux constater que le chemin commence par un slash `/` et chaque dossier est séparé par un
`/`.

Le premier slash `/` représente le chemin le plus profond de ton ordinateur : la racine
(`root` en anglais).
Va le visiter ! Pour cela, utilise la commande qui permet d’accéder à un dossier, en lui précisant le
chemin vers la racine :

```bash
cd /
```

Et comme il fait sombre là-dedans, utilisons la commande qui permet d’afficher la liste des fichiers et
dossiers :

```bash
ls
```

Oula, il y a un paquet de fichiers, tous affichés les uns à côté des autres ! Pas très pratique pour s’y
retrouver.<br>
Si tu veux afficher la liste des fichiers verticalement, avec en plus des détails, utilise la commande :<br>

```bash
ls -l
```

## Pause repas temporaire

Tu as vu précédemment l’ensemble des lieux qu’il t’est possible de visiter à partir de la racine.
Cependant, comme certains sont plus dangereux que d’autres, tu vas commencer par le plus le plus sûr de
ta machine : `/tmp` !<br>
Accède au dossier `/tmp` et affiche tout ce qu’il contient.

C’est le bordel là-dedans ! En fait, ce dossier contient des fichiers temporaires, qui sont parfois
utilisés lors de l’installation ou l'exécution de programmes sur ton ordinateur.

Tu peux supprimer ou créer ce que tu veux sans risque dans ce dossier.<br>
Tu vas donc créer un fichier afin de polluer un peu plus ton ordi !

```bash
echo "Je suis moisi" > vieuxtacos.txt
```

Observe en détail cette commande :

- la commande `echo` sert à afficher du texte dans la console.
- le signe `>` sert à stocker le résultat d’une commande précédente dans un fichier,
  spécifié ensuite. Tu peux l’utiliser avec tout ce que tu veux, pas uniquement `echo`.

En affichant la liste des fichiers, tu devrais voir ton nouveau `vieuxtacos.txt` !<br>
Si tu veux afficher le contenu du fichier, tu peux utiliser la commande suivante :

```bash
cat vieuxtacos.txt
```

Pas terrible d’avoir un vieux tacos moisi qui traine au fond de son ordinateur, tu vas pouvoir améliorer
ça.

```bash
echo "Je ne suis pas moisi" > vieuxtacos.txt
```

Si tu affiches le contenu du fichier, tu peux constater qu’il a été écrasé par le nouveau texte.<br>
C’est mieux, mais un vieux tacos, même s’il n’est pas moisi, ça reste un vieux tacos.<br>
Le mieux serait de renommer le fichier en autre chose, grâce à la commande suivante :

```bash
mv vieuxtacos.txt tacos.txt
```

La commande `mv` sert à déplacer un fichier d’un lieu à un autre, mais elle peut aussi être
utilisée pour renommer un fichier !

Ce tacos, n'étant plus moisi, était trop appétissant et tu l'as mangé. Supprime-le grâce à la commande
suivante :

```bash
rm tacos.txt
```

Si tu affiches le contenu du répertoire, le fichier ne s’y trouve plus, il a été supprimé
définitivement.

Il n’y a pas vraiment de “poubelle” dans le terminal, fais donc attention à ce que tu supprimes : il te serait
extrêmement difficile de le récupérer !
{: .alert-warning}

## Les gratte-ciels des logiciels

Le ventre plein, tu vas pouvoir continuer la visite.  
Va faire un tour à l’endroit où il t'est conseillé d’installer les logiciels sur ton ordinateur :

- `/opt` pour Linux
- `/usr/share` pour Windows
- `/usr/local` pour OSX

Pour le fun, tu vas essayer de créer un dossier ici, avec la commande :

```bash
mkdir tacosfolder
```

Tu devrais avoir la réponse suivante :

```bash
mkdir: cannot create directory tacosfolder: Permission denied
```

En effet, ce dossier (et plusieurs autres) est protégé, comme tu n’as pas précisé qui tu étais, Linux ne te laisse pas faire n’importe quoi ici.

Tu peux cependant, du moment que tu as assez de droits, forcer les choses avec la commande suivante :

```bash
sudo
```

Sous Windows la commande `sudo` n'existe pas. Mais pas de panique, tu peux l'installer !
Exécute la commande suivante : `curl -s https://raw.githubusercontent.com/imachug/win-sudo/master/install.sh | sh`
Puis redémarre ta console et tu auras accès à la commande !
{: .alert-warning}

Seule, la commande n’est pas utile, il faut la placer devant la commande que tu veux forcer : essaie de la combiner avec la commande précédente.

Plutôt que de retaper toute la commande, utilise la flèche haut de ton clavier. Le flèches haut/bas te permettent de te balader dans l’historique des commandes que tu as déjà tapé ! Utilise la flèche gauche pour revenir au début de la ligne et taper `sudo` (et un espace).

Tu peux aussi utiliser les raccourcis `Ctrl+A` et `Ctrl+E` pour aller automatiquement au début et à la fin de la ligne.

Tu devrais obtenir la ligne suivante :

```bash
sudo mkdir tacosfolder
```

La console devrait te demander le mot de passe de ta session pour vérifier tes privilèges :

```bash
[sudo] password for wilder:
```

Quand tu saisis un mot de passe dans la console, rien ne s'affiche à l'écran : c'est normal, mais rassure-toi, ce que tu tapes est bien pris en compte.

Allons faire un tour dans ce nouveau dossier :

```bash
cd tacosfolder
```

Maintenant, supprimons ce dossier vide.
Pour cela revient dans le dossier parent : plutôt que de devoir retaper le chemin à chaque fois, utilise le raccourci suivant :

```bash
cd ..
```

Cette commande permet de remonter d’un dossier dans l'arborescence.

Sous Linux, un seul point `.` signifie le dossier actuel et deux points `..` signifient le dossier parent.
Si tu écris la commande :

```bash
cd .
```

Bah en fait, tu accèdes au dossier actuel, donc ça ne fait rien !

Maintenant que tu es sûr d’être au bon endroit, supprime le dossier avec la commande suivante :

```bash
sudo rm -r tacosfolder
```

- la commande `sudo` sert à forcer la main, car tu es dans un dossier protégé
- la commande `rm` permet de supprimer un fichier
- le paramètre `-r` sert à préciser que tu veux supprimer un dossier et tout ce qu’il contient

## Les montagnes de documents

Pour la suite et fin de cet atelier, reviens dans ton dossier utilisateur, puis dans son sous-dossier `Documents`.

Plutôt que de devoir taper tout le chemin jusque là, sachant que le raccourci vers ton dossier utilisateur est le tilde `~`, tu peux écrire la commande :

```bash
cd ~/Documents
```

Profites-en pour utiliser la commande qui te permet de voir le chemin réel de l'endroit où tu te situes.  
Ici nous allons voir tous les droits pour s’amuser à bâtir un petit chalet pour les vacances !  
Commence par créer un dossier `chalet`.

Tout en restant dans `~/Documents`, crée un fichier vide `fauteuil1` avec la commande suivante :

```bash
touch fauteuil1
```

Déplace le fichier `fauteuil1` dans le dossier `chalet` avec la commande suivante :

```bash
mv fauteuil1 chalet
```

Crée les dossiers suivants dans le sous-dossier `~/Documents/chalet` :

- `armure`
- `armoires`
- `etageres`

Ensuite, accède au dossier `chalet` et commence à écrire la commande suivante (sans appuyer sur la touche `Entrée` à la fin) :

```bash
cd a
```

À la fin de la ligne, appui sur la touche `Tab` deux fois : la console devrait te présenter tous les dossiers commençant par `a`.

Complètes ta commande par :

```bash
cd armo
```

Puis appui sur la touche `Tab` : la console devrait te compléter la commande entière.  
On appelle ça l’autocomplétion !

Exécute la commande pour aller dans le dossier `armoires`, puis utilise la commande pour revenir dans le dossier précédent.

Enfin, nous allons ajouter des fauteuils à notre `chalet`, un seul n’est pas suffisant !  
Utilise la commande suivante pour copier un fichier :

```bash
cp fauteuil1 fauteuil2
```

Affiche le contenu du répertoire et tu trouveras bien deux fauteuils !

Enfin, toujours dans ton dossier `chalet`, crée un fichier `bibelots`.

Accède au dossier `armoires`. Déplace le fichier `bibelots` du répertoire précédent dans ton dossier actuel. Pour ce faire, utilise la commande suivante :

```bash
mv ../bibelots .
```

Comme vu précédemment, les deux points `..` représentent le dossier parent et le point `.` représente le dossier actuel.

Quand le fichier `bibelots` est présent dans ton `armoires`, sans bouger de là, copie ce fichier dans le dossier `etageres`, présent dans `chalet`.

Enfin, nous allons observer le contenu de ton `chalet`. Pour ce faire, reviens dans `~/Documents`.

Essaie la commande suivante :

```bash
find chalet
```

Si tu as bien travaillé, ton chalet ressemblera à ça :

```bash
chalet   chalet/fauteuil1   chalet/etageres   chalet/etageres/bibelots   chalet/armure   chalet/fauteuil2   chalet/armoires   chalet/armoires/bibelots
```

Félicitation ! Tu as le droit de continuer de t’amuser avec ton chalet. Pense à le supprimer plus tard (en ligne de commande) quand tu auras fini de jouer !
