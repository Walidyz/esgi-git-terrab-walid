# esgi-git-terrab-walid

Notre projet consiste à mettre en place un jeu simple similaire à Mario. Ce jeu comportera plusieurs map, pourra être joué avec plusieurs personnages et possèdera plusieurs niveaux.
Afin de mener à bien notre projet et d'être le plus efficace possible, il nous faut choisir un workflow.
Un workflow c'est la méthode que l'on va choisir pour réaliser nos tâches dans un projet. Cela permet d'accomplir les tâches de façon cohérente et productive. 


  
                Choix du Workflow:

- Workflow de branche par fonctionnalité (GitHub Flow)

Son principe : Ici, chaque fonctionnalité est développée dans une branche prévue à cet effet, avec un nom très descriptif.
Tout ce qui se trouve dans la branche principale (Main) est déployable et donc sans aucune erreur.
Ceci permet à plusieurs développeurs de travailler aisément et de facon plus lisible sur une fonctionnalité sans toute fois modifier le code de base.
Ces différentes branches doivent être pushées sur le dépot centralisé, pour que, justement, les développeurs puissent  travailler sur ces mêmes fonctionnalités.
Dès que l'on pense qu'une branche, donc une fonctionnalité est terminée, on effectue un "pull request", afin que notre/nos collègues puissent examiner la branche avant que celle-ci soit (ou non) déployée. Ceci rajoute une sécurité, car on le rappelle, tout ce qui est sur la branche principale ne doit pas contenir de bug.


               Justification du choix de ce Workflow

- Avantages
   - Pas de code bugué dans la branche main
   - Possibilité de signer une fonctionnalité avant son integration dans le projet
   - Bonne Communication en equipe sur le travail à effectuer
   - Livraison continue du travail
   
              Nos différentes branches :
- liste-carte (paris, londres, berlin)
- liste-personnages (toto, loic, tom)
- différent-menu (menu-pause, ecran-accueil, ecran-fin)
- différent-niveau (1,2,3)
Dans notre <<.gitignore>> nous avons décider de mettre un nouveau niveau   


             Démarche suivie:

On va crée une branche par fonctionnalité. Ainsi, dans chaque branche, nous aurons un répertoire avec les différents éléments de cette fonctionnalité.

Fride:
  - On commence par les cartes
  - On crée un repertoire pour les cartes, qu'on a appellé liste-carte et dedans on met 3 villes. Ce répertoire est crée dans la branche spécialement dédié aux cartes qui est elle aussi appelé liste-carte.
  - Ensuite on creé les fichiers des différentes cartes (paris, londres, berlin...)
  - Pour finir, on fait "git add liste-carte", pour ajouter le répertoire sélectionné au prochain commit. Après cela on fait un "git commit -m "première version des cartes"", et enfin "git push --set-upstream origin liste-carte"
Sur GitHub, cette branche est dorénavant disponible.

Walid:
  - Je récupère la branche sur github et pour l'avoir en local et travailler dessus je fais "git pull", ainsi je récupère sur mon ordinateur en local la nouvelle branche qui est liste-carte.
  - Maintenant, je peux faire "git checkout liste-carte" pour y accéder et travailler sur le répertoire liste-carte qui contient toutes les cartes. Je modifie le travail, et j'effectue un pull request avant de merge.
  - Avec le pull request, on a le choix de discuter, sur cette fonctionnalité avec qu'on la merge. On peut ainsi approuver ou non le contenu avant qu'il merge. Dans ce cas là, Fride a décider de re-modifier encore un fichier avant qu'il merge.


En plus : On a voulu volontairement faire un conflit en modifiant le même fichier sur la même branche. De ce fait, Fride ne pouvait plus se placer sur la branche main. Et elle était bloquer sur la branche liste-carte/merging.

Deux solutions:
- 1ère solution : résoudre cela en ligne de commande, en modifiant le fichier texte qui pose problème, et dans vim, il faut choisir le contenu qui nous intéresse.
Ensuite on refait un "git add paris.txt", un "git merge --continue" et "git push"
Là, le conflit est résolu.
Dorénavant, la fonctionnalité liste-carte est disponible sur la branche principale.
- 2ème solution: résoudre le conflit sur l'interface de github. En faisant un pull request, nous remarquons qu'il ya une erreur sur la branche crée alors une icone juste à coté appelé <<Resolve conflicts ?>> nous indique qu'il faut resoudre cela et en cliquant dessus nous pouvons modifier le fichier qui pose le conflit et apres cela on "commit" les changements et on fait de nouveau un "pull request" et le voila réglé.


Après la création d'une branche donc une fonctionnalité, la création des autres branches c'est globalement le même processus qui est réutilisé ("globalement" car il y a toujours des petits imprévus qui arrivent :( )
