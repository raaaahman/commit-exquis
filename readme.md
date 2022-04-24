# Le commit exquis

Ce jeu est un dérivé du jeu littéraire _Le cadavre exquis_, mais en utilisant des dépôts _Git_ partagés (sur GitHub).

## Règles du jeu

1. Un premier joueur est désigné, il doit créer un fork de ce dépôt. ![Il faut cliquer sur le bouton "fork" en haut à droite.](images/rules-01.png)
2. Une fois le dépôt "forké", il crée une copie locale de son fork avec la commande `git clone https://github.com/<username*>/commit-exquis` (où `<username*>` est remplacé par son nom d'utilisateur GitHub).
4. Depuis la copie locale du dépôt, il inspecte le dernier commit avec la commande `git log -n 1`, ce qui va lui révéler un morceau de phrase, par exemple: 
	```
	commit ba058f76a58a328d3bf6c171107fdc1aebbbcfc9 (HEAD -> master, origin/master)
	Author: raaaahman <sylvain@devindetails.com>
	Date:   Sun Apr 24 19:07:56 2022 +0200
	
   	 Un jour, alors que je me promenais, ...
    ```
3. Il doit alors finir la phrase précédemment commencée, **sans ouvrir le fichier texte**. Cela peut être fait grâce à la commande `echo je découvris une cabane. >> histoire.md`
4. Il commence ensuite une nouvelle phrase, et l'ajout au fichier, toujours sans ouvrir d'éditeur, par exemple: `echo Alors que j'en poussais la porte, >> histoire.md`
5. Il enregistre les modifications avec la commande et réécris le dernier morceau de phrase dans le message du commit, afin que le prochain joueur puisse le lire, par exemple `git commit -am "Alors que j'en poussais la porte, ..."`
6. Il pousse ensuite les modifications enregistrées sur son dépôt, par exemple: `git push origin master`.
7. Sur GitHub, il peut enfin faire une Pull Request vers le dépôt du joueur précédent, qu'il a forké. ![Dans l'onglet "Pull Request", cliquer sur le bouton "New Pull Request".](images/rules-02.png). GitHub devrait automatiquement proposer le dépôt d'origine et le dépôt actuel (en 1), ainsi que les branches `master` de chacun de ces dépôts (en 2). ![Sélection des dépôts et des branches à comparer](images/rules-03.png)
8. Puis il donne l'URL de son dépôt Git au prochain joueur, qui recommence à l'étape 1, ajoute ses deux morceaux de phrases, et passe au joueur d'après, et ainsi de suite.
9. Lorsque tous les joueurs ont ajouté leurs phrases, ont peut lire le texte complet à tout le monde.