# **Integration Testing**

La collection bruno etant versionnable avec git, elle permet aussi d'intégrer directement les tests d'intégrations à chacunes des requetes et donc à l'ensemble de la bibliothèque.
l'api doit être lancée en local ou distant (adapter l'env de bru selon)   
pour le local    
`make api && bin/api`    
Pour lancer les tests    
`cd Mangi_bruno`    
`bru run --env local --tests-only`    
Voir la documentation bruno pour plus d'informations
(documentation bruno)[https://docs.usebruno.com/testing/introduction]   

ps : (need)[https://docs.usebruno.com/bru-cli/overview]

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
`git add <fichier>`   
`git commit -m "KAN-n°ticket_description-efficace-du-sujet"`   
d'où l'importance de bien choisir le nom de ticket/branche.    
`git push`   

### Depot complémentaire

Vous avez déjà un commit mais vous avez des changements à ajouter.     
`git add <fichier>`    
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
`git push --force-with-lease`    

### **Merge vers main**

nous faisons des MR via gitlab et donc il suffit de créer / valider la MR sur l'interface gitlab.     
Normalement Gitlab fermera automatiquement la branche.     
Cela permet de garder une trace de l'arborescence des branches ainsi que la fermeture des branches après merge.      
Ensuite pensez a remettre a jour votre main avec un     
`git pull`

#### Author

Caroll Klacar