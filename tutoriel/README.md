# Tutoriel

# Exploration du génome de *Sacharomyces cerevisiae*

## Partie 1 : téléchargement des données

1. Téléchargez le génome de *S. cerevisiae* :
[*S288C_reference_sequence_R64-3-1_20210421.fsa.gz*](https://omics-school.github.io/formats-echanges-donnees-biologie/S288C_reference_sequence_R64-3-1_20210421.fsa.gz). Ce fichier provient de la [Saccharomyces Genome Database (SGD)](https://www.yeastgenome.org/)
2. Trouvez où ce fichier a été téléchargé sur votre ordinateur (a priori dans le répertoire *Téléchargements*) puis déterminez sa taille.
6. Essayez maintenant d'ouvrir le fichier téléchargé avec l'outil *Bloc-notes* de Windows. Pour ce faire :
    - Lancez d'abord *Bloc-notes* avec la petite loupe dans la barre d'outils en bas ([aide](img/bloc-notes_aide.png)).
    - Puis glisser-déposez le fichier sur l'application.
    - Que lisez-vous ?


> **Éléments de réponse :**
> > Le fichier se trouve a priori dans le répertoire *Téléchargements*. Le fichier a une taille d'environ 3,8 Mo.
> >
> > Quand on ouvre le fichier S288C_reference_sequence_R64-3-1_20210421.fsa.gz avec l'application *Bloc-notes*, on obtient :
> > ![](img/bloc-notes_O_tauri_gz.png)
> > Le fichier n'est pas très lisible. C'est normal car S288C_reference_genome_Current_Release.tgz n'est pas un fichier texte. C'est un fichier compressé donc binaire.
> > On ne peut pas ouvrir de fichier binaire avec un éditeur de texte. En fait, on peut techniquement (vous venez de le faire), mais cela n'a aucun intérêt.
{:.answer}


## Partie 2 : éditeurs de texte

### 2.1 Préparation

1. Installez le logiciel *Notepad++* sur votre machine. Vous trouverez une notice détaillée [ici](https://omics-school.github.io/formats-echanges-donnees-biologie/install-notepadpp/).
1. Vérifiez que le logiciel *7-zip* est bien installé. Si ce n'est pas le cas, installez-le sur votre machine. Vous trouverez une notice détaillée [ici](https://omics-school.github.io/formats-echanges-donnees-biologie/install-7zip/).

### 2.2 Visualisation du génome avec *Bloc-notes*

1. Décompressez le fichier *S288C_reference_sequence_R64-3-1_20210421.fsa.gz*.  
    Pour cela, cliquez droit sur le fichier puis sélectionnez *7-zip -> Extraire Ici*
1. Ouvrez le fichier *S288C_reference_sequence_R64-3-1_20210421.fsa* avec *Bloc-notes*.  
    Remarque : lancez d'abord *Bloc-notes* puis glisser-déposez le fichier sur l'application.
1. Quel est le nombre maximum de bases par ligne ?
1. Recherchez les chromosomes de *S. cerevisiae* en pressant les touches <kbd>Ctrl</kbd>+<kbd>F</kbd> puis en entrant le motif `>ref` puis en cliquant sur le bouton *Suivant* ([aide](img/bloc-notes_recherche.png)).  
    Combien de chromosomes trouvez-vous ?
1. Fermez le *Bloc-notes*.

> **Éléments de réponse :**
> > Quand on ouvre le fichier *S288C_reference_sequence_R64-3-1_20210421.fsa* avec *Bloc-notes* on obtient :
> > ![](img/bloc-notes.png)
> > 
> > Les lignes de séquences sont formatées avec un maximum de 60 bases par ligne.
> >
> > La fonction *Rechercher* (obtenue en pressant les touches <kbd>Ctrl</kbd>+<kbd>F</kbd>) permet de retrouver les chromosomes un par un
> > ![](img/bloc-notes_recherche.png)
> > En cliquant plusieurs fois sur le bouton *Suivant*, on trouve 16 chromosomes (+ une séquence pour la mitochondrie).
> >
{:.answer}


### 2.3 Visualisation du génome avec *Notepad++*

1. Ouvrez le même fichier avec l'éditeur de texte *Notepad++*.
1. Que signifie `LF` dans la barre en bas de la fenêtre ?
1. Avec votre souris, sélectionnez une ligne entière contenant un morceau de séquence puis regardez la barre en bas de la fenêtre.  
    Sur combien de caractères par ligne sont réparties les séquences des chromosomes de *S. cerevisiae* ?
1. Vérifiez que tous les chromosomes de *S. cerevisiae* sont bien là en pressant les touches <kbd>Ctrl</kbd>+<kbd>F</kbd> puis en entrant le motif `>ref` puis en cliquant sur le bouton *Suivant*.
1. Voyez-vous un moyen de compter très rapidement le nombres de chromosomes ?

Notepad++ est beaucoup plus puissant que Bloc-notes. Nous vous recommandons fortement son utilisation !

> **Éléments de réponse :**
> > Quand on ouvre le fichier *O.tauri_genome_V2.1.tfa* avec le *Notepad++* on obtient :
> > ![](img/notepad++_ouverture.png)
> > La mention `LF` dans la barre en bas de la fenêtre signifie que le fichier a été créé sous Unix pour lequel les fins de lignes sont `LF` (contre `CR+LF` pour un fichier créé sous Windows).
> >
> > En sélectionnant une ligne complète, la barre en bas indique le nombre de caractères. Ici 60.
> > ![](img/notepad++_taille_ligne.png)
> >
> > En utilisant la fonction *Rechercher* de *Notepad++*, on retrouve les 20 chromosomes.
> > ![](img/notepad++_rechercher.png)
> >
> > On peut même les compter très rapidement en cliquant sur le bouton *Compter* :
> > ![](img/notepad++_compter.png)
> >
> > On peut automatiser très simplement cette recherche de motif (`>ref`) et le comptage associé pour des dizaines voire des milliers de fichiers avec un outil comme Unix que nous aborderons prochainement.
{:.answer}


# Partie 3 : le jeu des différences

### 3.1 Préparation

Vérifiez que le logiciel *Meld* est bien installé. Si ce n'est pas le cas, installez-le sur votre machine. Vous trouverez une notice détaillée [ici](https://omics-school.github.io/formats-echanges-donnees-biologie/install-meld/).

Téléchargez les séquences protéiques, au format FASTA, de la déhydrogénase :
- de l'homme (P04406) - [UniProt](https://www.uniprot.org/uniprot/P04406) - [local](files/P04406.fasta)
- du gibbon à favoris blancs du Nord (G1QVR0) -  [UniProt](https://www.uniprot.org/uniprot/G1QVR0) - [local](files/G1QVR0.fasta)

### 3.2 Recherche des différences entre deux séquences de déhydrogénase

1. Lancez *Meld*, cliquez sur *File comparison*, cliquez sur *(None)* et sélectionnez les deux fichiers FASTA l'un après l'autre ([aide](img/meld_file_comp.png)). Enfin, cliquez sur *Compare*.
1. Identifiez la position et le type des acides aminés qui diffèrent entre les 2 séquences.

> **Éléments de réponse :**
> > ![](img/meld_dehydrogenase.png)
> > Les acides aminés différents entre l'homme et le gibbon sont :
> >
> > | Position | Homme | Gibbon |
> > |----------|-------|--------|
> > | 147      | Ile   | Val    |
> > | 329      | Ala   | Ser    |
> >
> > Le calcul de la position se fait en repérant le numéro (dans la barre en bas de la fenêtre) du caractère correspondant à la mutation puis en ajoutant le nombre de caractères des lignes d'avant (60 caractères par ligne).
> > Cette méthode est bien sur « artisanale ». Pour des séquences plus grandes ou plus nombreuses, il faudrait automatiser cette comparaison avec un programme écrit en Python ou en R par exemple 😇.
{:.answer}


# Partie 4 : contrôle d'intégrité

## 4.1 Préparation

Sur le site [Zenodo](https://zenodo.org/record/154453), vous trouverez les données d'une étude sur la malaria ayant pour titre
« *Plasmodium falciparum infection in febrile Congolese children: prevalence of clinical malaria ten years after introduction of Artemisinin-combination therapies* ».

En bas de la page, dans la rubrique *Files*, téléchargez les fichiers :

- `mng2015_children_malaria_codebook.txt`
- `mng2015_children_malaria_data.csv`

Si lors du téléchargement, Firefox vous demande quoi faire avec ces fichiers, choisissez *Enregistrer le fichier*.

Notez les empreintes MD5 fournies sous chaque fichiers :

![](img/malaria_md5.png)

Repérez où ont été téléchargés les fichiers (a priori dans le répertoire *Téléchargements*).

**Remarque :** Zenodo est un site très intéressant pour archiver certaines données scientifiques.


## 4.2 Calcul des empreintes

Depuis votre machine, lancez le logiciel *WinMD5* ([aide](img/winmd5_aide.png)).

En cliquant sur le bouton *Browse*, ouvrez le fichier `mng2015_children_malaria_codebook.txt`. 

![](img/winmd5_browse.png)

Comparez l'empreinte MD5 calculée (dans le champ texte *Current file MD5 checksum value*) avec l'empreinte fournie sur le site Zenodo où vous avez téléchargé les données.

Répétez l'opération avec le fichier `mng2015_children_malaria_data.csv`.

Ouvrez maintenant le fichier `mng2015_children_malaria_data.csv` avec Notepad++ et remplacez le 1er caractère de la 1ère ligne (`p`) par `P` (majuscule). Enregistrez le fichier modifié.

Calculez la nouvelle somme de contrôle du fichier `mng2015_children_malaria_data.csv` et comparez-la à la précédente.

> **Éléments de réponse :**
> > Si les deux fichiers ont été téléchargés correctement, les empreintes calculées doivent normalement correspondre à celles indiquées sur Zenodo.
> >
> > Une fois le premier caractère du fichier `mng2015_children_malaria_data.csv` modifié,
> > l'empreinte MD5 obtenue est totalement différente de la première.  
> > Il n'y a aucune relation entre deux sommes de contrôle mais s'il n'y a qu'un seul caractère
> > de différence entre les deux fichiers.
{:.answer}


## 4.3 Collision 😱

**Attention, cette cascade n'a pas été réalisée par un professionnel, essayez surtout de la reproduire chez vous.**

Téléchargez les deux images ci-dessous en cliquant droit sur chaque image puis en choisissant *Enregistrer l'image sous...*.

![](img/souvlaki_coll.jpg)

![](img/gyra_coll.jpg)

Toujours avec le logiciel *WinMD5*, calculez l'empreinte MD5 de ces deux photos (`souvlaki_coll.jpg` et `gyra_coll.jpg`, l'extension `.jpg` peut ne pas apparaitre dans l'explorateur de fichiers).

Notez bien l'empreinte à chaque fois. 

Comparez ensuite les deux empreintes. Si elles sont identiques, alors que les deux images sont portant bien différentes, vous venez d'assister à une collision de l'algorithme MD5. Bravo ! 🥳

Source : les images proviennent du blog [Emaragkos.gr](https://emaragkos.gr/infosec-adventures/create-your-own-md5-collisions/).

> **Éléments de réponse :**
> > Pour les deux images, l'empreinte MD5 est `59bbfd270bdf5817c5d77e739839a02a`.
> > La collision MD5 que vous avez pu observer n'est pas due au hasaard. Un algorithme particulier a été utilisé pour créer cette collision.
{:.answer}


## Licence

![](img/CC-BY-SA.png)

Ce contenu est mis à disposition selon les termes de la licence [Creative Commons Attribution - Partage dans les Mêmes Conditions 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/deed.fr) (CC BY-SA 4.0). Consultez le fichier [LICENSE](LICENSE) pour plus de détails.

This content is released under the [Creative Commons Attribution-ShareAlike 4.0 ](https://creativecommons.org/licenses/by-sa/4.0/deed.en) (CC BY-SA 4.0) license. See the bundled [LICENSE](LICENSE) file for details.
