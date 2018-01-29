# RUBY ON RAILS

## Modèle MVC
### ***Architecture***

![Image Archi](/images/schema_MVC.png)

Le **MVC**, ou *Model* / *View* / *Controller* est un
type d'architecture logiciel permettant une communication entre un utilisateur et une base de donnée.
Contrairement à un site statique, un site dynamique contient du code qui s’exécute via un serveur.

*Comment fonctionne une requête lors d'une navigation sur un site dynamique?*

1. Un utilisateur accède au site.
1. Le site accède au routeur.
1. Le routeur envoie une requête au controller via une *méthode*.

Le **controller** est l'entité centrale du modèle. Il fait le lien entre le routeur et le modèle, entre le modèle et la view et entre la view et l'utilisateur !

Le **modèle**, gère la base de donnée.

La **view**, gère la construction de la page HTML, et l'envoi de cette page.


## Comment ca marche ??

### La gestion des routes.

Dans un premier temps nous allons analyser ce que sont les *routes* dans le modèle MVC.

Le fichier routes.rb se situe dans le dossier **config**, généré lors de la création de l'app Rails.
> Il est vide...

Et oui ! C'est à nous de compléter ce beau fichier routes.rb !
Nous allons le compléter avec des *méthodes*.

Il y a différentes actions possibles, mais les 4 les plus utilisées sont les suivantes :
* GET : qui fait comme un return de la ressource suivant le path demandé. Elle va la chercher et en fait ce que tu lui demandes.
* POST : crée une nouvelle ressource
* PUT : met à jour une ressource existante
* DELETE : supprimer une ressource existante


  *ex : get 'welcome', to 'welcome#index'*
  --> Quand un utilisateur se rend sur URL/welcome, on execute la méthode index.

### La création d'un modèle

> Il faut avoir réfléchi préalablement à la structure de la base de donnée que nous voulons constituer.  

Pour créer la base de donnée, rien de plus simple :
Dans un terminal
```
rails g model Article
```
--> A pour effet de créer des fichiers
1. Fichier de migration
La migration sert grossièrement à une chose : créer/modifier une table avec les données souhaitées.
  1. Le fichier de migration créé possède une classe. Il faut ajouter des fonctions, des méthodes à cette classe, pour pouvoir agir sur la base de donnée.
1. Fichier de modèle, qui défini comment notre modèle interagit.
 
