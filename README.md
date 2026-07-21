# 🏮 Le Mandarin Rouge — Site Vitrine

Site vitrine pour un restaurant chinois fictif "Le Mandarin Rouge", créé comme **démonstration**.

## Fonctionnalités

- **Menu dynamique** chargé depuis l'API REST avec cache localStorage (1h)
- **Commande en ligne** avec panier interactif
- **Paiement simulé** avec animation 3D carte bleue + confettis
- **Design waouh** : thème sombre/rouge/or, GSAP, canvas lanternes, particules

## Stack

- HTML/CSS/JS fichier unique
- Google Fonts (Playfair Display + Inter + Noto Sans SC)
- GSAP + Canvas-confetti (CDN)
- API : menu-qr.thedeusirae.workers.dev

## Dev

```bash
python3 -m http.server 3000
```

## Déploiement

Automatique via GitHub Actions (`.github/workflows/deploy.yml`).

### Pour que l'API fonctionne en prod :

1. Va dans **Settings → Secrets and variables → Actions** du repo
2. Ajoute un secret `API_TOKEN` avec la valeur de ta clé API
3. Le workflow injecte la clé automatiquement au déploiement

## URLs

- **Production** : https://hovihovi.github.io/site-demo/
- **Dev local** : http://100.76.238.93:3000
