# Tutoriel

N'oubliez pas de renseigner votre progression dans le tableau de bord (lien sur Moodle).





# Partie 5 : transfert de données

Le dernier aspect abordé dans ce tutoriel concerne le transfert de données, depuis votre machine locale vers un serveur distant (le serveur RStudio de l'IFB par exemple) et inversement.

Nous allons pour cela utiliser le logiciel [FileZilla](https://filezilla-project.org/), logiciel libre et gratuit, disponible pour Windows, Linux et Mac.

1. Lancez d'abord *FileZilla* avec la petite loupe dans la barre d'outils en bas ([aide](img/filezilla_lancement.png)).
1. Tout en haut, dans le champ *Hôte* indiquez l'adresse du serveur de l'IFB : 
    ```
    sftp://core.cluster.france-bioinformatique.fr
    ```
    (voir remarque plus bas concernant l'adresse du serveur).
1. Dans le champ *Nom d'utilisateur*, indiquez le nom d'utilisateur de votre compte sur le serveur de l'IFB.
1. Dans le champ *Mot de passe*, indiquez le mot de passe de votre compte sur le serveur de l'IFB.
1. Cliquez enfin sur le bouton *Connexion rapide*.

Lors de la première connexion : 

1. Acceptez d'enregistrer vos informations de connexion dans FileZilla.
2. Dans la fenêtre *Clef de l'hôte inconnue*, cochez « *Toujours faire confiance à cet hôte, ajoutez cette clef au cache* » et cliquez sur le bouton *OK*.

Une fois connecté, la fenêtre de FileZilla devrait ressembler à ceci (cliquez pour aggrandir) :

<a href="img/filezilla_connexion_ifb.png"><img src="img/filezilla_connexion_ifb.png" alt="Fenêtre de connexion FileZilla" width="800"></a>

- Cet [autre graphique](img/filezilla.png) décompose les différents panneaux de la fenêtre FileZilla.
- Sur le serveur distant, votre répertoire utilisateur est de la forme `/shared/ifbstore1/home/LOGIN` où `LOGIN` est votre nom d'utilisateur. Nous verrons lors de la prochaine session ce que signifie `/shared/ifbstore1/home/...`.

Ensuite :

1. Dans FileZilla, dans le panneau de gauche correspondant à vos répertoires et fichiers locaux, déplacez-vous dans le répertoire *Downloads* (ou *Téléchargements*).
1. Retrouvez le fichier correspondant au génome de *S. cerevisiae* **décompressé**
    (fichier `S288C_reference_sequence_R64-3-1_20210421.fsa`).
1. Double-cliquez sur ce fichier pour le transférer vers le serveur de l'IFB.
1. Quelques instants plus tard, il devrait apparaître dans le panneau de droite, correpondant à vos répertoires et fichiers distants (c'est-à-dire sur le serveur de l'IFB). Au besoin, utilisez l'ascenseur à droite de la fenêtre pour parcourir tous les fichiers du répertoire.
1. Faites le transfert inverse, en double-cliquant sur un fichier dans le panneau de droite. Vous tranférerez ainsi ce fichier depuis le serveur distant vers votre machine. Vérifie que ce fichier est bien présent sur votre machine (panneau de gauche).
1. Dans un navigateur web, connectez-vous au serveur RStudio de l'IFB : <https://rstudio.cluster.france-bioinformatique.fr/> Vérifiez que le fichier du génome de *S. cerevisiae* apparait bien en bas à droite dans l'explorateur de fichiers (déplacez-vous si besoin dans votre répertoire utilisateur qui est sous la forme `/shared/ifbstore1/home/LOGIN` où `LOGIN` est votre nom d'utilisateur).

**Remarque :** lors de la dernière session, vous avez utilisé l'adresse <https://rstudio.cluster.france-bioinformatique.fr/> comme adresse du serveur RStudio de l'IFB. Pour un transfert de fichiers par FileZilla (via le protocole SSH), il faut se connecter au serveur `sftp://core.cluster.france-bioinformatique.fr`. Vous verrez par contre que les mêmes répertoires sont visibles d'un serveur à l'autre.

# Partie 6 : pour terminer avec un peu d'humour

Commentez ce [dessin](https://xkcd.com/2298/) du blog XKCD :

![](https://imgs.xkcd.com/comics/coronavirus_genome.png)



## Licence

![](img/CC-BY-SA.png)

Ce contenu est mis à disposition selon les termes de la licence [Creative Commons Attribution - Partage dans les Mêmes Conditions 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/deed.fr) (CC BY-SA 4.0). Consultez le fichier [LICENSE](LICENSE) pour plus de détails.

This content is released under the [Creative Commons Attribution-ShareAlike 4.0 ](https://creativecommons.org/licenses/by-sa/4.0/deed.en) (CC BY-SA 4.0) license. See the bundled [LICENSE](LICENSE) file for details.
