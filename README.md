[README.md](https://github.com/user-attachments/files/34910693/README.md)
# Prixjuste – comparateur de prix

Site statique (un seul fichier `index.html`, sans dépendance) pour comparer les prix.
Le site choisit les magasins selon la recherche :

| Recherche | Magasins proposés |
|---|---|
| diesel, essence, SP98, E85… | Prix-carburants.gouv.fr (officiel), Leclerc, Intermarché, Carrefour, Auchan, Système U, TotalEnergies, Esso, BP, Shell, Avia |
| lait, pain, café… | Leclerc, Intermarché, Carrefour, Auchan, Lidl (+ artisans si pertinent) |
| boulangerie, charcuterie, boucherie… | Google Maps, PagesJaunes + vos propres artisans |
| perceuse, canapé, aspirateur… | IKEA, Castorama, Conforama, Leclerc, Carrefour, Auchan, Darty, Boulanger… |
| vélo, tente, ballon… | Decathlon, Leclerc, Amazon, Cdiscount, eBay |
| jean, robe, veste… | Zalando, Amazon, Cdiscount, eBay (+ Vinted en occasion) |
| parfum, mascara… | Sephora, Amazon |
| livre, manga, lego… | Cultura, Fnac, Amazon, Leclerc |
| casque, téléphone, PC, télé… | Fnac, Darty, Boulanger, Cdiscount, Amazon, Back Market, Leclerc… |
| autre | Amazon, Cdiscount, eBay, Fnac, Leclerc, Intermarché, Carrefour, Auchan |

## Fonctionnement

- Le site **ouvre la recherche chez chaque marchand** ; il ne récupère aucun prix automatiquement.
- Vous relevez le prix vu et le site trace la courbe dans le temps.
- Vous pouvez coller le **lien direct de l'article** (même domaine que le marchand) pour que le bouton l'ouvre directement.
- Pour les artisans, ajoutez vos commerces locaux et notez le prix vu en boutique.
- Tout est stocké dans le `localStorage` du navigateur (rien n'est envoyé nulle part).

## Mise en ligne avec GitHub Pages

1. Créez un dépôt GitHub et déposez `index.html`, `README.md` et `.nojekyll` à la racine.
2. `Settings` → `Pages` → `Build and deployment` → `Deploy from a branch` → branche `main`, dossier `/ (root)` → `Save`.
3. Le site est disponible après une minute sur `https://<utilisateur>.github.io/<depot>/`.

En local : ouvrez simplement `index.html` dans un navigateur.

## Ajouter un marchand

Dans `index.html`, ajoutez une ligne au tableau `M` :

```js
{n:"Nom",c:"tech maison",u:q=>`https://exemple.fr/recherche?q=${q}`},
```

`c` liste les catégories : `tech`, `cour`, `maison`, `sport`, `mode`, `beaute`, `culture`, `carb`, `gen`.

## À vérifier

Certains liens de recherche (Leclerc, Intermarché, Lidl, Conforama, PagesJaunes…) n'ont pas été testés en direct : corrigez l'adresse dans `M` si l'un d'eux ne marche pas.
