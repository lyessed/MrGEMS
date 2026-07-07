# MRS GEMS — Site vitrine

Site monopage (HTML + Tailwind CDN + JS vanilla). Prêt à pousser sur Git / Vercel.

## Arborescence
```
mrs-gems/
├─ index.html
└─ assets/
   ├─ mrs-gems-logo.png   (logo)
   ├─ header-atelier.jpg  (image de fond hero, optimisée 278 Ko)
   └─ hero-video.mp4      (⚠️ PREVIEW iStock AVEC FILIGRANE — à remplacer)
```

## Déploiement Vercel
Aucun build. Push le dossier sur GitHub → Import dans Vercel → deploy. C'est du statique.

## ⚠️ À REMPLACER avant mise en ligne (cherche "REMPLACER" dans index.html)
1. **Téléphone** : `01 23 45 67 89` / `tel:+33123456789` (7 occurrences)
2. **Email** : `contact@mrs-gems.fr`
3. **Lien Google Business** : dans le footer + le JSON-LD
4. **Domaine** : balises `canonical` et `og:*` (`https://www.mrs-gems.fr/`)
5. **Vidéo hero** : `assets/hero-video.mp4` est un preview iStock filigrané → mettre une version licenciée (même nom de fichier, rien d'autre à changer)

## Brancher le formulaire sur n8n
Dans `index.html`, cherche `WEBHOOK_URL` (section SCRIPTS) :
```js
const WEBHOOK_URL = ""; // -> "https://n8n.zerotache.pro/webhook/mrs-gems-devis"
```
Renseigne l'URL du webhook n8n. Le formulaire enverra un POST JSON avec :
`nom, tel, email, cp, ville, appareil, marque, panne`.
Un honeypot (`website`) filtre déjà les bots côté front.

## SEO déjà en place
- Balises meta + Open Graph + Twitter
- JSON-LD `HomeAndConstructionBusiness` (zone IDF, horaires, tél)
- Structure sémantique (header/main/section/footer, h1→h3)
- Favicon, canonical
- **À ajouter côté repo** : `sitemap.xml` + `robots.txt` (comme pour BHA)
