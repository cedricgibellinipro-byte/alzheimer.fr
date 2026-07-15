[README.md](https://github.com/user-attachments/files/30053485/README.md)
# alzheimer.fr — Landing page premium

Landing page single-page, sobre et haut de gamme, présentant **alzheimer.fr**
comme un actif numérique rare disponible à l'acquisition — destinée à une
organisation sérieuse (fondation, institut de recherche, plateforme
d'information, startup MedTech, application d'accompagnement...).

Design inspiré de la sobriété de v8.fr, Apple, Linear et Stripe : fond noir
profond, typographie XXL, beaucoup d'espace vide, animations discrètes.

## Aperçu

- Fond `#090909`, blanc cassé, rouge `#E53935` en accent unique
- Une seule page, aucun menu
- Illustration abstraite d'un complexe de neurones (SVG pur, aucune photo)
- Formulaire de contact intégré, révélé au clic sur « Faire une offre »
- 100% HTML / CSS / JavaScript vanilla — aucune dépendance, aucun build

## Structure du projet

```
.
├── index.html   # page complète (HTML + CSS + JS dans un seul fichier)
└── README.md    # ce document
```

## Utiliser le projet

Aucune installation n'est nécessaire.

1. Téléchargez `index.html`
2. Ouvrez-le directement dans un navigateur, ou déployez-le tel quel

## Déploiement sur GitHub Pages

1. Créez un nouveau dépôt GitHub et importez `index.html` à la racine
2. Dans **Settings → Pages**, sélectionnez la branche `main` et le dossier `/root`
3. La page est publiée à l'adresse `https://<votre-utilisateur>.github.io/<votre-dépôt>/`

Pour utiliser un nom de domaine personnalisé (ex. `alzheimer.fr`), ajoutez un
fichier `CNAME` à la racine contenant le domaine, puis configurez les DNS
chez votre registrar (enregistrement `A` vers les IP GitHub Pages ou `CNAME`
vers `<votre-utilisateur>.github.io`).

## Personnalisation

Toutes les valeurs de design sont centralisées en haut du fichier, dans
`:root` (variables CSS) :

```css
:root{
  --black:#090909;
  --white:#f5f5f3;
  --red:#e53935;
  --font-a:'Inter', sans-serif;       /* voix principale */
  --font-m:'JetBrains Mono', monospace; /* labels, chiffres, méta */
}
```

- **Couleurs** : modifier `--black`, `--white`, `--red`
- **Typographies** : remplacer les imports Google Fonts dans `<head>` et les
  variables `--font-a` / `--font-m`
- **Textes** : chaque section est commentée dans le HTML (`SECTION 1 — HERO`,
  `SECTION 2 — CE QUE ALZHEIMER.FR PEUT DEVENIR`, etc.)
- **Illustration neuronale** : SVG inline dans le hero, avec des dégradés
  radiaux (`glowWhite`, `glowRed`) réutilisables pour d'autres noeuds

## Formulaire de contact

Le formulaire final est géré en JavaScript (`contactForm` dans le `<script>`
en fin de fichier) et simule actuellement l'envoi côté client. Pour le
connecter à un vrai service :

- **Formspree / Getform** : changez l'attribut `action` du `<form>` et
  laissez la soumission native du navigateur s'exécuter
- **API interne** : remplacez le contenu du gestionnaire `submit` par un
  appel `fetch()` vers votre endpoint

## Performance & accessibilité

- Aucune image raster : tout est en SVG et CSS, donc léger et net à toute résolution
- `prefers-reduced-motion` respecté : toutes les animations sont désactivées
  pour les utilisateurs qui le demandent
- Focus clavier visible sur les éléments interactifs
- Balises sémantiques (`header`, `main`, `section`, `footer`) et un seul `<h1>`

## Licence

Projet fourni tel quel pour un usage propre à la présentation et à la
commercialisation du nom de domaine alzheimer.fr.
