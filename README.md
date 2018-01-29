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
* **GET** : qui fait comme un return de la ressource suivant le path demandé. Elle va la chercher et en fait ce que tu lui demandes.
* **POST** : crée une nouvelle ressource
* **PUT** : met à jour une ressource existante
* **DELETE** : supprimer une ressource existante


  *ex : get 'welcome', to 'welcome#index'*
  --> Quand un utilisateur se rend sur URL/welcome, on execute la méthode index.

### La création d'un modèle

> Il faut avoir réfléchi préalablement à la structure de la base de donnée que nous voulons constituer.  

Pour créer la base de donnée, rien de plus simple :
Dans un terminal
```
$ rails g model Article
```
--> A pour effet de créer des fichiers
1. Fichier de migration
La migration sert grossièrement à une chose : créer/modifier une table avec les données souhaitées.
  * Le fichier de migration créé possède une classe. Il faut ajouter des fonctions, des méthodes à cette classe, pour pouvoir agir sur la base de donnée.
1. Fichier de modèle, qui défini comment notre modèle interagit.
1. Fichier de tests.

Pour créer la base de donnée, il faut faire dans un terminal :
```
$ rails db:migrate
```

> Fichier très pratique à consulter : schema.rb qui permet de voir l'état de la base de donnée.

Le modèle étant maintenant créé, il va falloir commencer à manipuler tout ça !

### Le modèle CRUD

Le **CRUD**, ou **C**reate **R**ead **U**pdate **D** estroy
est un  modèle permettant d'interagir avec notre base de donnée, et par l'interface du front-end.

#### Commençons par les routes

Rails nous permet de générer directement les routes du CRUD
Dans le fichier routes.rb,
```
ressources :modèle
```

On peut consulter  *"l'annuaire"* de ces routes avec la commande
```
rails routes
```
Pour chacune des méthodes, il faut maintenant créer la page !

#### Création du controller
Dans le terminal
```
rails g controller Controller_name
```
Créé un fichier **controller** et un fichier **view**

Le fichier controller est composé d'une classe, vide.
Le principe est de codé les méthodes qui composent le CRUD pour pouvoir faire appel à ces méthodes dans le but de manipuler la DB.

A chaque fois qu'une méthode est créée dans le controller, il ne faut pas perdre de vue que l'on recherche à afficher une page pour un utilisateur.
Il faut donc penser à éditer également un fichier view.html.erb
Ce fichier est à créer dans le dossier **view** et dans le sous-dossier créer automatiquement par le controller (du même nom).
Ce fichier est à écrire en HTML.
La spécificité de ce type de fichier réside dans la possibilité d'intégrer du code Ruby directement dans le corps du HTML, grâce à la balise erb
``` eRuby
<% ...... %>
<%= ..... %>
```
