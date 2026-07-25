# Ventes du jour — O'minüs (Qweekle)

Tableau de bord mobile, en un seul fichier (`index.html`), pour suivre en un
coup d'œil **les ventes du jour** et **les 7 derniers jours** de la plaine de
jeux, à partir de l'API Qweekle.

## Ce qu'il affiche

- **Ventes du jour** : net encaissé, **brut**, remboursements, nombre de
  tickets, ticket moyen, montant hors TVA et répartition par canal (caisse,
  accueil/web…).
- **7 derniers jours** : mini-graphique en barres + détail jour par jour
  (net, brut, HT, nombre de tickets).
- Rafraîchissement automatique (toutes les 5 min et au retour sur l'onglet),
  bouton de rafraîchissement manuel, et cache local si le réseau coupe.

## Sécurité du token

Le **token API n'est pas** dans le code. À la première ouverture, la page le
demande et le conserve **uniquement dans le navigateur de l'appareil**
(`localStorage`). Le fichier peut donc être hébergé publiquement sans risque :
sans token, la page n'affiche rien. Un bouton permet d'effacer le token.

## Mettre en ligne (GitHub Pages)

1. Dépôt **Settings → Pages**.
2. **Source** : « Deploy from a branch ».
3. **Branch** : `claude/qweekle-api-data-inventory-nnkkxc`, dossier `/ (root)`,
   puis **Save**.
4. Au bout d'une minute, l'URL apparaît (type
   `https://corthouts.github.io/Qweekle/`).
5. Ouvrir l'URL sur mobile, coller le token une fois, puis « Ajouter à
   l'écran d'accueil » pour un accès en un tap.

> Pour une URL plus propre à la racine du domaine, on peut plus tard fusionner
> cette branche dans `main` et servir Pages depuis `main`.

## Journée / fuseau

« Aujourd'hui » = la journée en cours à l'heure de Bruxelles
(`Europe/Brussels`), pour coller aux dates renvoyées par Qweekle.
