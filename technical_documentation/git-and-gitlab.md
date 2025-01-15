# **Git**

Je propose le process suivant :
Nous travaillons à partir de la branche main (ou dev : nous verrons avec Valentine selon le type de déploiement continu), nous créons des branches selon les tickets de taches que nous devrons faire. Puis une fois la tache faite, nous mergeons vers la branche de départ.

Je conseille très fortement par conséquent que les tickets découpes les taches dans le plus petit dénominateur possible. Cela permettra non seulement de sentir l'avancement du projet mais aussi de pouvoir avancer avec des petits morceaux de code:

- plus facile de rollback en cas de besoin.
- plus facile de controler le code.
- moins lourd pour celui qui doit s'occuper de la tache.

## **Création de Branche**

Depuis la branche main afin d'être à jour :
`git pull`
`git checkout -b <nom_branche>`
Dans une soucis d'uniformité de travail, voici les process.
Nommage de branche:
`KAN-n°ticket_description-efficace-du-sujet`

Exemple de nom de commande:
`git checkout -b MG-2501_add-database-connexion`

## **Commit sur branche de travail**

### Depot standard

Afin de garder de la lisibilité, nous n'allons faire qu'un commit par branche.
Vous avez du travail à push ...
`git add <fichier>` ou `git add -u`
`git commit -m "KAN-n°ticket_description-efficace-du-sujet"`
d'où l'importance de bien choisir le nom de ticket/branche.
`git push`

### Depot complémentaire

Vous avez déjà un commit mais vous avez des changements à ajouter.
`git add <fichier>` ou `git add -u`
`git commit --amend`
la console qui va s'ouvrir va vous permettre de changer le nom de commit si besoin.
sinon vous sortez de la console avec `:wq`
`git push --force-with-lease`

## **Rebase avant de merge vers main**

Nous arrivons au moment de merge vers le main. Il va falloir en amont vous mettre à jour avec main.
`git checkout main`
`git pull`
Puis mettre à jour votre branche.
`git checkout <branche>`
`git rebase main`
Résoudre les conflits si besoin.
`git commit --amend`
`git push --force-with-lease`

### **Merge vers main**

nous faisons des MR via gitlab et donc il suffit de créer / valider la MR sur l'interface gitlab.
Normalement Gitlab fermera automatiquement la branche.
Cela permet de garder une trace de l'arborescence des branches ainsi que la fermeture des branches après merge.
Ensuite pensez a remettre a jour votre main avec un
`git pull`

#### Author

Caroll Klacar
