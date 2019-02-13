# Tutoriel

# Exploration du génome d'Ostreococcus tauri

## Partie 1

1. Allez sur le site <http://bioinformatics.psb.ugent.be/orcae/>
1. Puis sur **Ostreococcus tauri (V2)**
    ![](img/tauri_V2.png)
    Attention de bien prendre la **V2** !
1. Combien *O. tauri* possède de chromosomes ?
    > **Réponse :**
    > > Il y a 20 chromosomes
    {:.answer}

1. Cliquez ensuite sur **Download** puis **assembly_data** puis **O.tauri_genome_V2.1.tfa.gz**
1. Repérez où ce fichier a été téléchargé sur votre ordinateur et déterminez sa taille.
1. Essayez maintenant d'ouvrir le fichier téléchargé avec l'outil *Bloc-notes* de Windows. Pour ce faire :
    - Lancez d'abord le *Bloc-notes* ([aide](img/bloc-notes.png))
    - Puis glisser-déposez le fichier sur l'application.
    - Que lisez-vous ?


## Partie 2

### Préparation

1. Installez le logiciel *7-zip* sur votre machine. Vous trouverez une notice détaillée [ici].
1. Installez le logiciel *Notepad++* sur votre machine. Vous trouverez une notice détaillée [ici].


### Visualisation du génome avec le *Bloc-notes*

1. Décompressez le fichier *O.tauri_genome_V2.1.tfa.gz*. Cliquez droit sur le fichier puis sélectionnez *7-zip -> Extraire ici*
1. Ouvrez le fichier *O.tauri_genome_V2.1.tfa* avec le *Bloc-notes*
    Remarque : lancez d'abord le *Bloc-notes* puis glisser-déposez le fichier sur l'application.
1. Recherchez les chromosomes de *O. tauri* en pressant les touches <kbd>Ctrl</kbd>+<kbd>F</kbd> puis en entrant le motif `>chrom` puis en cliquant sur le bouton *Suivant* ([aide](img/recherche_bloc-notes.png)).
    Retrouvez-vous le bon nombre de chromosomes ?
1. Observez-vous un truc *curieux* par rapport à vos connaissances du format FASTA ?
1. Fermez le *Bloc-notes*.


### Visualisation du génome avec le *Notepad++*

1. Ouvrez le même fichier avec l'éditeur de texte *Notepad++*.
1. La lisibilité du fichier est-elle améliorée ?
1. Comment expliquez-vous cette différence de comportement entre le *Bloc-notes* et *Notepad++* ?
1. Avec votre souris, sélectionnez une ligne entière contenant un morceau de séquence puis regardez la barre en bas de la fenêtre.
    Sur combien de caractères par ligne sont réparties les séquences des chromosomes de *O. tauri* ?
1. Vérifiez que tous les chromosomes de *O. tauri* sont bien là en pressant les touches <kbd>Ctrl</kbd>+<kbd>F</kbd> puis en entrant le motif `>chrom` puis en cliquant sur le bouton *Suivant*


# Le jeu des différences

### Préparation

1. Installez le logiciel *Meld* sur votre machine. Vous trouverez une notice détaillée [ici].

### Recherche des différences entre deux séquences de déhydrogénase

1. Téléchargez les séquences protéiques, au format FASTA, de la déhydrogénase :
    - de l'homme (P04406) - [UniProt](https://www.uniprot.org/uniprot/P04406) - [local](files/P04406.fasta)
    - du gibbon à favoris blancs du Nord (G1QVR0) -  [UniProt](https://www.uniprot.org/uniprot/G1QVR0) - [local](files/G1QVR0.fasta)
1. Lancez *Meld*, cliquez sur *File comparison*, indiquez le chemin des deux fichiers FASTA puis cliquez sur *Compare*.
1. Identifiez quels acides aminés diffèrent entre les 2 séquences

Réponse :
![](img/meld_dehydrogenase.png)
Ile (homme) | Valine (gibbon)
Ala (homme) | Ser (gibbon)
