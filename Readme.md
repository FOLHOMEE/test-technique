# Test technique

## Exercices :

### Algo

Créer une fonction javascript permettant d'obtenir le chiffre le plus proche de zéro au sein d'un tableau de valeurs ex : `closeToZero( [ 10, 7, -3, 4.5, -1.3, 579 ] ) // retourne -1.3`

### MongoDB

Tu dispose de la collection "ads" suivante :

```
{ _id: 1, title: 'Appartement 40m2 dans Paris 15', price: 405000, type: 'apartment', assets:['last-floor']  },
{ _id: 2, title: 'Appartement 54m2 dans Paris 20', price: 399000, type: 'apartment', assets:[]  },
{ _id: 3, title: 'Maison de campagne', price: 232000, type: 'house', assets:['country-side', 'refresh']  },
{ _id: 4, title: 'Maison avec piscine', price: 321900, type: 'house', assets:['swimmingpool', 'refresh']  },
```

A l'aide de requêtes ou d'aggregats, tu dois obtenir les résultats suivants :

1. Obtenir la somme des prix des appartements (pas des maisons)
2. Obtenir un tableau contenant la liste des `assets` sans doublon
3. Obtenir la liste des annonces qui possèdent le mot "campagne" dans le titre (sans tenir compte de la casse)

### NodeJS

Tu hérite du code suivant. A l'aide de la librairie `express`, tu dois créer une nouvelle route en POST `/scrapping`. En appelant cette route, l'application doit récupérer le texte HTML de la page `https://www.folhomee.fr`. Avec l'aide d'une librairie de ton choix, tu dois aller chercher le `content` de la balise meta `google-site-verification` et finalement l'afficher en retour.

```
const express = require('express')
const request = require('request')
const app = express()

// Si aucune route ne match, on affiche un message
app.use((req, res) => res.send('Erreur...'))

// On lance le serveur
app.listen(3000)
```

### React

A l'aide du serveur node précédement réaliser, tu doit créer une petite application React qui va contenir un bouton. Lorsqu'on clique sur le bouton, ça doit appeler la route que tu as créé pour récupérer le contenu de la mete `google-site-verification` du site Folhomee.
