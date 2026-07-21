# 🏮 Le Mandarin Rouge — Site Vitrine

Site vitrine pour un restaurant chinois fictif "Le Mandarin Rouge", créé comme **démonstration**.

## Fonctionnalités

- **Menu dynamique** chargé depuis l'API REST (fallback hardcodé si API indisponible)
- **Commande en ligne** avec panier interactif
- **Paiement simulé** avec animation 3D carte bleue + confettis
- **Design waouh** : thème sombre/rouge/or, animations scroll, particules flottantes

## Stack

- HTML/CSS/JS fichier unique
- Google Fonts (Playfair Display + Inter)
- Canvas-confetti (CDN)
- API : menu-qr.thedeusirae.workers.dev

## Dev

```bash
# Serveur local
python3 -m http.server 3000
```

## Build

Pas de build — c'est du HTML statique.

## Déploiement

Sur GitHub Pages via push sur le repo `hovihovi/mandarin-rouge`.
