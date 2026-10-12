# epruva. — Espace candidat (prototype autonome)

## Démarrage

Ouvrez **index.html** directement dans Chrome, Firefox, Edge ou Safari. Aucune installation, aucun serveur, aucun `npm install` et aucune connexion Internet ne sont nécessaires.

Sur la page de connexion, entrez **n'importe quel identifiant et mot de passe fictifs** pour entrer dans le prototype. **Ne saisissez pas vos véritables identifiants.**

## Écrans inclus

- Connexion IAM commune contextualisée sur epruva (démo, sans Keycloak réel)
- Mot de passe oublié (simulation)
- Accueil candidat
- Mes examens : filtres, recherche, tri, statuts
- Détail d'un examen
- Passation : questions, navigation, marquage, chronomètre et soumission simulée
- Résultats détaillés : publication de note et autorisation distincte de correction
- Entraînement : 10 matières, recherche, choix du thème, mode et nombre de questions
- Révision : correction immédiate, explications et bilan
- Défi : chronomètre, correction en fin de session et bilan
- Pages 403, 404, 500, hors ligne, session expirée
- Footer standard et footer compact
- Responsive desktop/tablette/mobile avec navigation mobile inférieure

## Pages de démonstration supplémentaires

Après connexion, ouvrez dans la barre d'adresse (après `index.html`) :

- `#/403`
- `#/404`
- `#/500`
- `#/offline`
- `#/expired`

Dans la console du navigateur : `epruvaDemo.offline()` simule la perte de connexion pendant une session et `epruvaDemo.online()` la reconnexion. `epruvaDemo.reset()` réinitialise les données de démo.

## Important

C'est un **prototype UX/UI fonctionnel**, pas une application d'examen de production :

- Les examens, questions, résultats, statistiques et comptes sont fictifs.
- Aucune authentification réelle : **Keycloak n'est pas connecté**.
- Aucune API FastAPI, base de données, correction officielle ni soumission serveur.
- Le navigateur conserve l'état de la démonstration dans `localStorage`. Il peut être effacé à tout moment.
- Les règles de chronométrage et de soumission sont simulées : le navigateur ne fait pas autorité.
- Le mode Défi est une extension de démonstration, non encore validée en détail.
- Le catalogue de 10 matières n'a qu'un petit jeu de questions d'algèbre linéaire pour illustrer les interactions.
- Les liens légaux et d'aide sont des placeholders.

## Organisation

```
epruva-candidat/
├── index.html
├── assets/
│   ├── style.css
│   └── app.js
└── README.md
```

Stack : HTML5 + CSS3 + JavaScript natif. Aucun framework, bundler, CDN ni dépendance externe.

Pour une version réelle, la suite logique est de porter ces composants vers Angular et d'intégrer Keycloak (OIDC Authorization Code + PKCE), l'API FastAPI et une sauvegarde robuste des réponses.
