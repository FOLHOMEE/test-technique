# Test technique Folhomee

## Contexte

Le buts de ce test technique sont les suivants :

- Nous permettre de voir votre niveau technique
- Essayer de déterminer vos capacités concernant la résolution de problèmes
- Voir si vous pourriez vous intégrer au sein de notre équipe technique

Au cours de ce test technique, vous allez réaliser une application de réduction d'URL à l'image de [bitly](https://bitly.com/)

Il est important de respecter les consignes suivantes :

- Ne sautez pas un exercice, il faut respecter l'ordre
- Vous n'avez pas besoin d'utiliser un service extérieur pour les exercices
- Il est très facile de trouver des résolutions/solutions de ce test en ligne, aussi vous serez jugé sur votre capacité de structurater votre code

## Livrables

Les livrables minimum sont les suivants :

- Un repo github privé auquel vous aurez donné accès au CTO de Folhomee (username github : [milanito](https://github.com/milanito))
- Un ensemble de dossiers/fichiers selon une nomenclature claires
- Pour chacun des exercices, le temps que vous avez mis à le réaliser au travers d'un README que vous essayerez de détailler (le markdown est recommandé), de préférences individuellement pour chaque partie

Nous vous demanderons en plus de respecter les contraintes technique suivantes :

- Le code devra être écrit en javascript et tourner sur node LTS (v12 au moment de l'écriture de ce test)
- Le code devra respecter la coding style de l'entreprise, à savoir [standardjs](https://standardjs.com/)

Pour le reste, vous êtes libre de vos choix technique (base de donnée, etc ...) quand il n'est pas explicitement dit dans l'exercice le choix à faire

## Exercices

Lors de ce tests, nous vous demandons de créer deux dossiers à la racine de votre repo :

- Un dossier `back` qui regroupera les fichiers source de votre application serveur :
  - Le serveur est une application node, n'oubliez pas de l'initialiser avec `npm init` ou `yarn init`, vous êtes libre du choix du gestionnaire de paquet
  - Les sources devront se trouver dans un sous dossier `src`
  - Vous êtes libre d'utiliser, ou non, un module bundler ou un compiler javascript
- Un dossier `front` qui regroupera les fichiers sources de votre application front
  - Nous vous conseillons de le créer uniquement au moment ou vous commencerez l'application front

### Fonction de reduction/identification

Dans le dossier `back/src`, après avoir créé un sous dossier `services`, créer deux fonctions (vous êtes libre sur le nombre de fichiers ou les modules externes à utiliser) :

- Pour obtenir une hash, en entrée votre fonction doit prendre un entier et renvoyer une chaine de caractères
- Pour obtenir une ID à partir d'un hash, en entrée votre fonction doit prendre une chaine de caractère et renvoyer un entier

Il faut imaginer que la première fonction prend en entrée une ID de base de donnée (SQL, pour mongodb la réprésentation est différente) et renvoie un hash unique, par exemple :

```
f(34) = df3f
```

> Attention, la fonction doit être déterministe : À savoir pour une valeur donnée, il va toujours renvoyer la même valeur

Tandis que la seconde doit pouvoir à partir d'un hash renvoyer l'id correspondante, par exemple :

```
g(df3f) = 34
```

N'oubliez pas dans votre README (à la racine du projet ou dans le dossier `back`) de détailler vos choix d'algorithme

#### Bonus

Les bonus pour cet exercice sont les suivants :

- Implémentation de test
  - Au sein de l'entreprise nous utilisons jest, mais vous êtes libre sur le choix à faire

### Serveur

Dans le dossier `back`, vous allez créer une application [expressjs](https://expressjs.com/fr/) qui devra comporter deux routes :

- Une route qui permet de réduire une URL :
  - L'URL attend comme paramétre une URL à réduire
- Une route qui permet, à partir d'un hash, de rediriger l'URL correspondante

Vous devez utiliser pour cet exercice les fonctions que vous avez précédemment créé (attention donc si vous avez fait le choix d'une base de donnée avec des ID non incrémentales, type mongoDB)

Vous êtes libre sur vos choix(verbes HTTP, middlewares, etc ...), dans cet exercice nous vous jugerons sur votre capacité à bien structurer votre code

#### Bonus

Les bonus pour cet exercice sont les suivants :

- Implémentation de test
- Pour une URL déjà existante, renvoyer le même hash
- Avoir une validation de l'URL en entrée

### Application Front

Vous allez créer dans le dossier `front` une application React qui consistera en une seule page, sur laquelle vous devrez (à partir de l'application express précédemment créée) :

- Permettre à l'utilisateur de rentrer une URL pour la réduire
- Lister les dernières URLs qui ont été réduite, avec un lien réduit qui doit ouvrir, dans un nouvel onglet, votre URL

Vous êtes libre dans les choix d'implémentation, de représentation et de fonctionnement, sachant dans cet exercice nous vous jugerons sur votre capacité à proposer une expérience utilisateur intéressante

#### Bonus

Les bonus pour cet exercice sont les suivants :

- Implémentation de test

## Bonus

Une fois l'intégralité des exercices précédents réalisés, vous pouvez réaliser les tâches suivantes en bonus :

- Pouvoir lancer la stack applicative (back/front/base de donnée) au travers de docker, et docker compose
- Proposer un hébergement en ligne pour les applications
- Trouver un algorithme pour éviter le déterminisme dans notre algorithme
- Nous impressionner avec n'importe quoi que vous trouverez pertinent
