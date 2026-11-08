# Invitation de mariage — Camille & Julien

Site d'invitation en une seule page, pensé d'abord pour le téléphone.
HTML + CSS + JavaScript pur, aucune dépendance à installer, aucune base de données.

## Contenu du dossier

```
.
├── index.html          ← tout le site (textes + photos à modifier en haut du fichier)
├── photos/             ← vos images (voir photos/lisez-moi.txt)
│   └── lisez-moi.txt
└── README.md
```

## Personnaliser en 5 minutes

1. **Ouvrez `index.html`** avec n'importe quel éditeur (VS Code, Bloc-notes, TextEdit…).
2. **Tout en haut du fichier**, le bloc `window.CONFIG` contient :
   - prénoms, monogramme du cachet de cire, initiales du pied de page ;
   - date du mariage (format `AAAA-MM-JJTHH:MM:SS`) → pilote le compte à rebours ;
   - salle, adresse, ville → génèrent automatiquement la carte Google Maps
     et le bouton « Ouvrir l'itinéraire » ;
   - date limite de réponse, e-mail, téléphone, WhatsApp ;
   - hashtag ;
   - le chemin de chaque photo.
3. **Les textes** (histoire, programme, dress code…) sont dans le `<body>`,
   chacun précédé d'un commentaire `✎ MODIFIER`.
4. **Les photos** : déposez vos fichiers dans `photos/` avec les noms indiqués
   dans `photos/lisez-moi.txt`. Des images d'exemple s'affichent tant qu'elles
   ne sont pas là.

## Formulaire de réponse (RSVP)

- Par défaut (`mode: "formulaire"`), le bouton ouvre un formulaire élégant
  intégré à la page ; la réponse part par **e-mail** (ou par **WhatsApp** si
  vous renseignez `rsvp.whatsapp`).
- Si vous préférez Google Forms / Typeform : mettez `mode: "lien"` et collez
  votre adresse dans `rsvp.url`.

## Prévisualiser sur son téléphone

Ouvrez simplement `index.html` dans un navigateur.
Pour tester avec les vraies photos et le bon comportement mobile :

```bash
# dans le dossier du site (Python 3)
python3 -m http.server 8000
```
Puis ouvrez `http://localhost:8000` (ou l'IP de votre ordinateur depuis
le téléphone, sur le même réseau Wi-Fi).

## Accessibilité & performances

- Animations désactivées automatiquement si le téléphone demande
  « moins de mouvement » (`prefers-reduced-motion`).
- Images chargées en différé (`loading="lazy"`), polices avec `display=swap`.
- Aucune librairie JavaScript : la page pèse quelques dizaines de kilo-octets.

## Mise en ligne

Voir les instructions détaillées de déploiement (GitHub + Vercel ou Netlify)
dans le fil de discussion, ou les classiques :

- **Netlify Drop** : glissez-déposez le dossier sur https://app.netlify.com/drop
- **Vercel** : `vercel` en ligne de commande, ou import du dépôt GitHub.
