# POPCORN 🍿

_Popcorn_ est une plateforme open source et (vraiment) sans frais ni commission qui aide les développeur-e-s freelance de {{MA_LOCALITE}} à trouver des projets : [Voir le site](https://popcorn-nantes.github.io/)

## Les objectifs de _Popcorn_ pour les développeurs freelances :

- 📈 Etre un canal pour trouver des affaires à {{MA_LOCALITE}} sans commission ni intermédiaire
- 📗 Maitriser les fonctionnalités de la plateforme en contribuant à [la machine à Popcorn](https://github.com/popcorn-nantes/popcorn-machine).
- 💬 Faire circuler les tuyaux boulot entre freelances via le tchat.
- 💪 Offrir une alternative locale aux _market places_ de freelances centralisées

## Quelle est la différence avec des plateformes comme Malt ou Comet ?

- _Popcorn_ est une [association à but non-lucratif](https://opencollective.com/popcorn) et ne prélève pas de commission.
- _Popcorn_ est réservé aux **développeur·e·s de {{MA_LOCALITE}}**.
- _Popcorn_ est développé et maintenu par les développeur(e)s freelances eux-mêmes.
- _Popcorn_ n'est **pas** un intermédiaire ou une entreprise: les clients entrent directement en contact avec les freelances. _Popcorn_ ne joue aucun rôle dans les échanges qui suivent ensuite entre les deux parties.

## Les fonctionnalités

- Gestion des profils de freelance et de pages statiques
- Recherche instantanée sur les compétences et mot-clefs du profils
- SEO-friendly avec la prégénération du html et les tags pour les réseaux sociaux (Facebook, Twitter, Linkedin)
- Support Gravatar pour les photos du profil
- Un formulaire de contact qui envoie le message sur le channel #general d'un Slack
- Une page qui affichent tous les autres popcorns francophones

## La philosophie : 0 maintenance, 0 frais, simple et efficace

Le mot _Popcorn_ a été notamment choisi pour évoquer une grande légèreté. Son mantra technique pourrait être:

> Dis moi ce dont tu as besoin, je te dirai comment t'en passer.

L'idée expérimentée par _Popcorn_ est d'avoir un site aussi léger techniquement que possible, sans serveur et base de données **afin qu'il ne requiert quasiment aucune maintenance et intervention de notre part ni aucun frais, parce que :**

- On est déjà tous "sous l'eau", ce site ne doit pas être une charge de travail supplémentaire.
- On ne veut pas que le site reste 48 heures en rade parce qu'il ya un truc qui déconne et que tout le monde est trop occupé pour intervenir dessus.
- On ne veut pas qu'au fil du temps une personne devienne "responsable" du site, qu'elle soit la seule à piger comment tout fonctionne et qu'elle parte à Barcelone ou quitte _Popcorn_ en laissant aux autres un truc compliqué qu'ils et elles ne maitrisent pas
- On veut bien être hébergé pour 0 euros chez Github ^^
- On veut bien un site qui soit capable de supporter un fort pic de charge sans broncher : évitons le cas du site qui tombe pile au moment où un article de presse le mentionne 😅
- On veut bien un moteur de recherche super-rapide et un site qui s'affiche super vite
- On veut bien que des gens puissent tout simplement forker ce dépôt pour créer leur propre annuaire 💚

## La technique

`popcorn-machine` est une application [Nuxt.js](https://github.com/nuxt/nuxt.js) qui permet de générer un site statique en _html_ à partir de fichiers markdowns pour créer les profils et contenus du sites.

Les fichiers markdowns sont convertis en fichier JSON via le module Nuxt [Gustave](https://github.com/yann-yinn/nuxt-gustave). Ce sont ces fichiers JSON qui sont ensuite consommés par les composants Vue.js.

Le tout est ensuite exportable en _html_ et hébergeable sur [github pages](https://pages.github.com/).

### Comment créer sons propre _Popcorn_

- Télécharge le popcorn-starter
- Renomme le fichier .env.example, renomme le en .env avec les valeurs qui correspondent à ton Popcorn.
- Installe puis démarre le Popcorn avec `npm install` puis `npm run dev`
- Recherche toutes les occurences de `{{MON_POPCORN}}` et `{{MA_LOCALITE}}` pour les remplacer par les valeurs de ton Popcorn.
- Si tu veux déployer ton site avec Travis sur Github, il faudra connecter l'application Travis à Github et renseigner la variable GITHUB_TOKEN.
- _N'oublie pas de renseigner sur Travis ou autre toutes les variables présentes dans le fichier .env.example_
- N'hésite pas à nous contacter si tu as besoin d'aide, en ouvrant une issue sur ce dépôt.

- tu pourra sensuite ajouter ton popcorn a l'annuaire et ajouter des profil a ton procorn

### Tests

Cypress est utilisé pour tester le site. Pour lancer les tests, il faut d'abord démarrer le projet de test qui sera lancé sur le port `44000`

```sh
# démarrer le projet de test sur le port 44000
cd test/e2e/project
npm run dev
# revenir à la racine du projet
cd -
# Lancer la suite de tests dans le terminal
npm run e2e
# Lancer la suite de tests en ouvrant un chrome (recommandé pour le debug)
npm run e2e:open
```
