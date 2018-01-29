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
> Il est vide
