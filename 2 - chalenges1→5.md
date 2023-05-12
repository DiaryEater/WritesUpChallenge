# FTP Authentification
Pour ce premier chalenge, ce sera toute simple. Vous avez eu accès au site ? Bravo ! Commençons !<br>
Normalement on verra un Boutton `Démarrer le chalenge` qui nous enverrai vers un lien de téléchargement, pour se faire, d'abord click droite sur ce Boutton, ensuite `copier l'adresse du lien`.
Ouvrons maintenant un nouvel onglet, on colle le lien, ce dernier nous mènera vers un téléchargement automatique du fichier ".pcap"; une fois télécharger, on click dessus et il nous ouvrira Wireshark.
<br>

```sh
On voit maintenant plusieurs ligne affichées, choisissez une ligne, peu importe laquelle vous choisirez, click droite → suivre → Flux TCP : 
	ça va afficher des informations privé d'où le mot de passe, il se trouve en dessus de "331 Password", le MDP se trouve auprès de `PASS`. Fini. Vous copiez, revenez vers le site du chalenge,
	et vous collez dans "Entrez le mot de passe".
```
Félicitations ! Premier chalenge réussi.

<br>

# TELNET Authentification
Pour commencer, on procède tel le commencement du Premier chalenge sur le Boutton `Démarrer le chalenge`. 
```sh
Pour la suite aussi, ce sera pareillement, choisissez une ligne, peu importe laquelle vous choisirez, click droite → suivre → Flux TCP :
	mais cette fois, ce qui sera affiché serait plus épais, mais on ne cherche qu'une chose, le MDP, où ? simple, nous verrons `Password: ...`
	et pareil encore, Vous copiez, revenez vers le site du chalenge, et vous collez dans "Entrez le mot de passe".
```
Félicitations ! Deuxième chalenge réussi.

<br>

# ETHERNET Trame
Cette fois ce sera un peu différent que d'habitude.
```sh
Une fois `Démarrer le chalenge` clické, on vous enverra vers un tout autre site qui montrera une langage informatique qu'il faudra décoder :
00 05 73 a0 00 00 e0 69 95 d8 5a 13 86 dd 60 00
00 00 00 9b 06 40 26 07 53 00 00 60 2a bc 00 00
00 00 ba de c0 de 20 01 41 d0 00 02 42 33 00 00
00 00 00 00 00 04 96 74 00 50 bc ea 7d b8 00 c1
d7 03 80 18 00 e1 cf a0 00 00 01 01 08 0a 09 3e
69 b9 17 a1 7e d3 47 45 54 20 2f 20 48 54 54 50
2f 31 2e 31 0d 0a 41 75 74 68 6f 72 69 7a 61 74
69 6f 6e 3a 20 42 61 73 69 63 20 59 32 39 75 5a
6d 6b 36 5a 47 56 75 64 47 6c 68 62 41 3d 3d 0d
0a 55 73 65 72 2d 41 67 65 6e 74 3a 20 49 6e 73
61 6e 65 42 72 6f 77 73 65 72 0d 0a 48 6f 73 74
3a 20 77 77 77 2e 6d 79 69 70 76 36 2e 6f 72 67
0d 0a 41 63 63 65 70 74 3a 20 2a 2f 2a 0d 0a 0d
0a
Comment ?

On copie le langage, on se dirige vers : https://www.rapidtables.com/convert/number/hex-to-ascii.html , sur la page on colle ce texte informatique dans la cage de `Coller des nombres hexadécimaux ou déposer un fichier`;
click sur le Boutton 'Convertir', et, ça donnera ensuite ceci :
s àiØZÝ`@&S`*¼ºÞÀÞ AÐB3tP¼ê}¸Á×áÏ 
	>i¹¡~ÓGET / HTTP/1.1
Authorization: Basic Y29uZmk6ZGVudGlhbA==
User-Agent: InsaneBrowser
Host: www.myipv6.org
Accept: */*

Notez qu'on aura nul besoin de tout ça. On prendra uniquement cette ligne : Y29uZmk6ZGVudGlhbA== qu'on va copier, ensuite voyageons vers un autre page, qui sera celui-ci : https://www.base64encode.org/ .
Dedans, en haut de la page, il y aura 2 options, "Decode" et "Encode", on click "Decode". On colle ensuite " Y29uZmk6ZGVudGlhbA== " dans la cage de ``Decode from Base64 format``, on scroll un peu et on click le boutton en vert `Decode`.
Finalement, on obtient le MDP qui sera dans la cage en dessous.
```
Félicitations ! Troisième chalenge réussi.

<br>

# Authentification Twitter
On revient à la méthode traditionelle, celui des 2 premiers chalenge, mais cette fois mélangée avec la troisième.
```sh
- Click droite `Démarrer le chalenge`, nouvel onglet, coller, et télécharrgement. Enfin, Wireshark.
- Ensuite, tel qu'habituellement (certes, il n'y aura qu'une seulle ligne) : click droite sur cette ligne → suivre → Flux TCP/HTTP (l'un ou l'autre ça ira).
- On aura ensuite une nouvelle fenêtre comme avant, on va s'intérésser à la ligne : " Authorization: Basic dXNlcnRlc3Q6cGFzc3dvcmQ= ".
- On prend maintenant " dXNlcnRlc3Q6cGFzc3dvcmQ= ", on le copie. C'est là qu'entre en scène le Troisième challenge.
- Mais cette fois, on ira seulement qu'au 2ème site ( https://www.base64encode.org/ ), dedans on applique pareillement le même procédé qu'en Troisième chalenge.
- Tadannn ... MDP obtenu
```
Félicitations ! Quatrième chalenge réussi.

<br>

# BLUETOOTH - Fichier inconnu
Pour le BLUETOOTH, ça va être plus complexe. Après le téléchargement, vous aurez un fichier ISO, qui sera nommé `ch18`, et ce n'est pas grave du tout. Mais, notez que vous ne pourrez l'ouvrir direct dans Wireshark
à partir de son emplacement principal dans votre P.C, par conséquent il faudra l'ouvrir autrement. <br>
Ceci dit, rien de difficile, on va procéder donc inversement, c'est à dire on va l'ouvrir à partir de Wireshark : <br>
    Commment ?
```sh
- Tout en haut, en dessous du nom du fichier ouvert, on a 11 choix de navigation, dont `Fichier`, on click dessus et on aura de multiples options, on click sur la première, soit `Ouvrir`, et finalement on séléctionne le "Fichier ISO ch18", et `Ouvrir`.
- Normalement ça ne va encore rien ouvrir, si c'est le cas, pas de panique, il faudra juste clicker le 'X rouge' tout à droite de la barre de recherche qui va se colorer e Vert. Résultat : le fichier est enfin ouvert dans Wireshark.
- Mais ce n'est pas fini évidement, nous venons juste d'ouvrir le fichier.
```

<br>

Une fois dans Wireshark, on peut enfin travailler normalement comme de petit(s) Hacker(s). <br>
Etape 1 :
```sh
- Revoyons les choix de navigation ! ... Vous voyez le `Wireless` ? oui ! on click dessus, on aurra 4 options aux choix, bien, nous on ne voudra qu'une seulle et ce sera `Equipement Bluetooth`.
- On aurra droit à un petit tableau, double click sur n'importe quel valeur dans le tableau, ensuite on copicolle la valeur de 'BD_ADDR' et 'Nom' (seulement) dans un Bloc Notes par exemple.
- On change en majuscule les lettres de la valeur du 'BD_ADDR' (notez que ce dernier représente enfait une adresse MAC).
- On met les deux valeurs sur une même ligne sans aucune espace; normalement on aura comme ceci : ``0C:B3:19:B9:4f:C6GT-S7390G``.

N.B : Pour copier les valeurs du tableau, click droite sur la valeur → copier la cellule.
```

<br>

Etape 2 :
```sh
- Après avoir copier ce dernier, on visite : https://www.dcode.fr/hash-sha1 pour le décoder afin de parvenir au MDP final.
- On colle ce dernier dans la seconde cage la plus grande que nous verrons, puis le boutton ``Chiffrer``.
- Si les choses se passent bien pour nous, au côté gauche de la page, on verra un test vérifiant si on est un Robot ou Non. On le fait sans  hésiter car ce n'est pas du tout un problème, juste comme un procédé à suivre. Une fois le test términé, il vous donne le MDP tant recherché.
```
Félicitations ! Cinquième chalenge réussi.
