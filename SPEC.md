# Le Mandarin Rouge — Site Vitrine

## Restaurant (fictif)

- **Nom :** Le Mandarin Rouge
- **Adresse :** 42 Rue de la Lanterne, 75002 Paris
- **Téléphone :** 01 42 86 53 72
- **Horaires :** Mar-Dim 12h-14h30 / 19h-22h30
- **Description courte :** Cuisine chinoise authentique au cœur de Paris, entre tradition et modernité

## API

- **Base URL :** `https://menu-qr.thedeusirae.workers.dev/api/v1`
- **Auth :** `Authorization: Bearer 994b0dd8a6e2f949ddb0434490fffd911c28deb5eeee6a09bb1a6da208f9ecc9`
- **GET /menu?lang=fr** → menu complet groupé par catégorie
- **POST /orders** → créer une commande
  - Body: `{ customer_name, customer_phone, notes, items: [{ menu_item_id, quantity }] }`
  - Response: `{ order: { id, status, total_price, ... } }`

## Stack

- **Fichier unique** `index.html` (HTML + CSS + JS embarqué)
- Zéro dépendance externe (sauf Google Fonts et confetti lib)
- Font: "Playfair Display" + "Inter" (Google Fonts)
- JS library: canvas-confetti (CDN) pour l'effet waouh

## Design & WOW Effect

- **Thème :** Sombre (#0a0a0f bg), rouge (#dc2626 / #ef4444), or (#f59e0b / #d4a853), blanc cassé (#f8f5f0)
- **Hero :** Full-screen avec vidéo/particules animées (CSS keyframes + canvas de lanternes flottantes)
- **Animations :** Scroll reveal avec Intersection Observer (fade-up, slide-in)
- **Menu :** Cards glassmorphism (backdrop-blur, border gradient) avec hover 3D tilt effect
- **Commande :** Panier slide-out avec animations fluides, notification toast
- **Paiement :** Modal avec animation de carte de crédit 3D flip, barre de progression simulée
- **Confettis :** canvas-confetti.js sur le succès de commande
- **Navigation :** Fixed navbar avec blur, links smooth scroll
- **Parallax :** Section parallax avec overlay rouge
- **Compteurs :** Animated counters (plats servis, années d'expérience, etc.)

## Sections

1. **Nav** — Logo + liens (Menu, Commande, Contact) + bouton panier avec badge
2. **Hero** — Background gradient animé + cercles flottants, titre "Le Mandarin Rouge", tagline, CTA "Découvrir le menu"
3. **À propos** — Parallax divider "Depuis 1985" + texte + 3 cartes stats (compteurs animés)
4. **Menu** — Tabs par catégorie, cards avec image/prix/description/niveau épicé, bouton "Ajouter"
5. **Commander** — Récapitulatif du panier + formulaire (nom, téléphone, notes) + bouton "Commander"
6. **Contact** — Google Maps embed + infos + horaires
7. **Footer** — Copyright + liens

## Interactions

### Panier
- Bouton "Ajouter" sur chaque plat → ajoute au panier (stockage JS, pas localStorage)
- Bouton panier dans nav → slide-out drawer du panier
- Dans le drawer : items avec quantité +/- et suppression, total
- Bouton "Passer la commande" → scroll vers section Commander

### Commande
- Formulaire : nom (required), téléphone (required), notes (optionnel)
- Bouton "Payer 💳" → modal de paiement
- Modal : animation 3D carte bancaire + spinner loading 2s → succès
- Succès : confettis + message "Commande #XXX confirmée !" + résumé
- Appel API POST /orders avec les données

### Menu dynamique
- fetch au chargement avec loading skeleton
- Affichage par catégories (tabs)
- Gestion erreur API → fallback menu statique hardcodé

## Responsive

- Mobile-first
- Navigation burger en mobile
- Menu en grille 1 col mobile, 2 col tablette, 3 col desktop

## Fichier

`projects/site-web/mandarin-rouge/` (déjà créé)
- `index.html` — le site complet
- `README.md` — infos projet
