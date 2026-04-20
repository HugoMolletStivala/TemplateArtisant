# 🔧 Template Site Vitrine – Artisan Local
**Version 1.0 – Prêt à l'emploi, 100% statique**

---

## 📁 Fichiers inclus

```
/
├── index.html       ← Site complet (tout-en-un)
├── config.json      ← Configuration à personnaliser
└── README.md        ← Ce fichier
```

---

## ⚡ Démarrage rapide

### 1. Personnalisez `config.json`
C'est le seul fichier à modifier pour adapter le template à votre activité.

```json
{
  "business": {
    "name": "VotreEntreprise",         ← Nom affiché partout
    "service": "Électricien",          ← Votre métier (singulier)
    "servicePluriel": "Services d'électricité",
    "ville": "Marseille",
    "departement": "Bouches-du-Rhône",
    "codePostal": "13001",
    "adresse": "15 Rue Paradis",
    "telephone": "04 91 00 00 00",     ← IMPORTANT : format "XX XX XX XX XX"
    "telephoneFormate": "04 91 00 00 00",
    "email": "contact@votre-site.fr",
    "siteWeb": "https://www.votre-site.fr",
    "horaires": "Disponible 24h/24, 7j/7",
    "anneesExperience": "10",
    "nombreInterventions": "1 800",
    "noteGoogle": "4.8",
    "nombreAvis": "187"
  }
}
```

### 2. Adaptez vos services
Modifiez le tableau `services` pour lister vos prestations :

```json
"services": [
  { "icon": "⚡", "titre": "Dépannage électrique", "description": "Votre description ici." },
  { "icon": "🔌", "titre": "Tableau électrique", "description": "..." }
]
```

### 3. Ajoutez vos zones d'intervention
```json
"zones": ["Marseille 1er", "Marseille 2e", "Aix-en-Provence", "Aubagne"]
```

### 4. Intégrez vos vrais avis clients
Remplacez les exemples dans `temoignages` par vos avis réels (copiez depuis Google Maps).

### 5. Mettez en ligne
Déposez les deux fichiers (`index.html` + `config.json`) sur votre hébergeur.

---

## 🎨 Personnaliser les couleurs

Dans `config.json`, section `couleurs` :

```json
"couleurs": {
  "primaire": "#1a3a5c",    ← Couleur principale (bleu foncé par défaut)
  "accent":   "#e8420a",    ← Couleur CTA / boutons (orange par défaut)
  "fond":     "#f7f5f0",    ← Couleur de fond
  "texte":    "#1a1a1a"     ← Couleur du texte
}
```

**Suggestions par métier :**
| Métier        | Primaire  | Accent    |
|---------------|-----------|-----------|
| Plombier      | `#1a3a5c` | `#e8420a` |
| Électricien   | `#1a2a4c` | `#f5a623` |
| Serrurier     | `#2c2c2c` | `#c0392b` |
| Chauffagiste  | `#8b2020` | `#e67e22` |
| Peintre       | `#2d5a27` | `#3498db` |

---

## 🔍 SEO Local – Liste de contrôle

### Avant la mise en ligne :
- [ ] Vérifier que le **numéro de téléphone** est identique sur :
  - Le site (topbar, header, hero, contact, footer)
  - Votre fiche Google Business Profile
  - Les annuaires (PagesJaunes, etc.)
- [ ] Renseigner `config.json → seo.titreOnglet` avec votre mot-clé principal
- [ ] Rédiger une `metaDescription` naturelle contenant `[service] à [ville]`
- [ ] Lister toutes vos zones d'intervention dans `zones`
- [ ] Mettre à jour le **schéma JSON-LD** automatiquement généré ✅ (fait par le JS)

### Google Business Profile :
1. Créez/revendiquez votre fiche sur [business.google.com](https://business.google.com)
2. Utilisez **exactement** le même nom, adresse et téléphone que dans `config.json`
3. Ajoutez des photos de vos interventions
4. Répondez à tous les avis
5. Postez régulièrement des actualités

---

## 📱 Fonctionnalités d'appel

| Fonctionnalité | Description |
|---|---|
| **Bouton sticky mobile** | Affiché en permanence sur mobile en bas d'écran |
| **Numéro partout** | Topbar, header, hero, contact, footer, tous cliquables |
| **Appel direct** | Tous les numéros utilisent `tel:` pour appel direct |

---

## 🛠 Adaptation par métier

| Métier | service | servicePluriel | icon suggestions |
|--------|---------|---------------|-----------------|
| Plombier | "Plombier" | "Services de plomberie" | 💧🚿🔧🏠⚡🔩 |
| Électricien | "Électricien" | "Services d'électricité" | ⚡🔌💡🔧🛡️🏗️ |
| Serrurier | "Serrurier" | "Services de serrurerie" | 🔑🚪🔒🛡️⚡🔧 |
| Chauffagiste | "Chauffagiste" | "Services de chauffage" | 🔥🌡️🔧⚙️♨️🏠 |
| Maçon | "Maçon" | "Services de maçonnerie" | 🧱🏗️🔨⚒️🏠✅ |

---

## ⚙️ Architecture technique

- **100% statique** – Aucun serveur, aucun backend
- **Chargement** : `config.json` chargé via `fetch()` au démarrage
- **Fallback** : Si `config.json` absent, les données par défaut sont utilisées
- **Performance** : CSS Variables, animations CSS uniquement, pas de framework JS
- **SEO** : JSON-LD mis à jour automatiquement depuis la config
- **Accessibilité** : Balises ARIA, roles, navigation clavier

---

## 📋 FAQ du template

**Q : Le site fonctionne-t-il sans serveur ?**
R : Oui, en double-cliquant sur `index.html`. Pour que `config.json` se charge, un serveur local ou hébergement est recommandé.

**Q : Puis-je l'héberger gratuitement ?**
R : Oui – GitHub Pages, Netlify, Vercel, OVH hébergement mutualisé, etc.

**Q : Comment ajouter Google Analytics ?**
R : Ajoutez le script GA4 juste avant `</head>` dans `index.html`.

**Q : Comment intégrer Google Maps ?**
R : Dans la section `#contact`, ajoutez une `<iframe>` Google Maps avec votre adresse.

**Q : Puis-je modifier les textes directement dans le HTML ?**
R : Oui, tous les éléments ont des `id` explicites et peuvent être modifiés directement.

---

## 📞 Support

Pour toute question sur la personnalisation, référez-vous à ce README ou consultez la documentation des technologies utilisées (HTML5, CSS3 Variables, JavaScript ES2020+).

---

*Template conçu pour maximiser les appels téléphoniques et le référencement local en France.*
