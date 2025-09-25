# cryptotracker

Crypto Watch Tower — un petit projet React pour suivre les cryptomonnaies en temps réel en utilisant l'API CoinGecko.

## Aperçu

Cette application affiche :

- Données globales du marché (market cap, volume, etc.).
- Liste des principales cryptomonnaies (prix, variation, market cap).
- Graphiques de prix par crypto.

Technos utilisées : React, Webpack (create-react-app-like), JavaScript, SCSS.

## APIs utilisées

- Market data : `https://api.coingecko.com/api/v3/global`
- Données des coins : `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=250&page=1&sparkline=false&price_change_percentage=1h%2C24h%2C7d%2C14d%2C30d%2C200d%2C1y`
- Graphiques de prix : `https://api.coingecko.com/api/v3/coins/${coinId}/market_chart?vs_currency=usd&days=${duration}${duration > 32 ? "&interval=daily" : ""}`

> Remarque : CoinGecko propose une API publique gratuite avec des limites de rate. Pour un usage intensif, consulte la documentation CoinGecko.

## Installation (en local)

Ouvre un terminal dans le dossier du projet puis :

```powershell
npm install
```

## Lancer le serveur de développement

```powershell
npm start
```

Le projet démarre en mode développement. Le terminal te précisera l'URL locale (par défaut `http://localhost:3000` ou un autre port si 3000 est occupé).

## Scripts utiles

- `npm start` : démarre le serveur de développement.
- `npm run build` : crée une version optimisée pour la production dans `build/`.
- `npm test` : lance les tests (si configurés).

## Configuration et variables d'environnement

Si tu utilises des variables d'environnement (par exemple pour une clé API), crée un fichier `.env` à la racine et ajoute les variables nécessaires. Le projet ignore déjà les fichiers `.env` via `.gitignore`.

Exemple :

```
# .env
REACT_APP_API_URL=https://api.coingecko.com/api/v3
```

## Déploiement

Construis d'abord l'application :

```powershell
npm run build
```

Tu peux ensuite déployer le contenu du dossier `build/` sur n'importe quel hébergeur statique (Netlify, Vercel, GitHub Pages, etc.).
