# Xeler Devis Copieurs — guide de mise en ligne

## 1. Mettre l'application en ligne sur GitHub (comme l'outil robots)

Je n'ai pas pu créer le dépôt ni pousser le code moi-même depuis cette session (pas d'accès en écriture à ton compte GitHub ici) — voici la marche à suivre, identique à celle déjà utilisée pour l'outil robots (dépôt `xeler-devis`, mise en ligne du 2026-08-25) :

1. Aller sur **https://github.com/new**
2. Nom du dépôt : `xeler-devis-copieurs` (compte `burgatregis-cloud`, comme pour les robots)
3. Laisser "Public" (nécessaire pour GitHub Pages gratuit), ne rien cocher d'autre, cliquer "Create repository"
4. Sur la page du dépôt vide qui s'affiche, cliquer **"uploading an existing file"**
5. Glisser-déposer tout le contenu de ce dossier (`index.html`, `manifest.json`, `sw.js`, le dossier `assets/`, le dossier `icons/`) — **le dossier lui-même, pas un zip** : GitHub reconstitue l'arborescence automatiquement si tu glisses les dossiers `assets` et `icons` en entier
6. En bas de page, cliquer **"Commit changes"**
7. Aller dans **Settings → Pages** (menu de gauche du dépôt)
8. Sous "Build and deployment" → Source : choisir **"Deploy from a branch"**, branche **main**, dossier **/ (root)**, puis **Save**
9. Après 1 à 2 minutes, l'adresse apparaît en haut de cette même page : `https://burgatregis-cloud.github.io/xeler-devis-copieurs/`

C'est cette adresse qu'il faut partager avec ton équipe (comme `https://burgatregis-cloud.github.io/xeler-devis/` pour les robots).

**Si tu préfères, dis-le-moi** : dans une prochaine session je peux aussi pousser le code directement si l'accès en écriture à ce nouveau dépôt est ajouté aux sources autorisées de la session.

## 2. Installer l'application (identique à l'outil robots)

### Sur PC Windows
1. Ouvrir Edge ou Chrome sur l'adresse GitHub Pages ci-dessus
2. Cliquer sur l'icône d'installation dans la barre d'adresse (ou menu ⋮ → "Installer Xeler Devis Copieurs")
3. L'application s'ouvre dans sa propre fenêtre, épinglable à la barre des tâches

### Sur Android / tablette
1. Ouvrir Chrome sur la même adresse
2. Menu ⋮ → "Ajouter à l'écran d'accueil" / "Installer l'application"

## 3. Premiers réglages (une fois installée)

Aller dans **Administration → Copieurs** :

- **Tous les prix de vente sont à 10 000 € (placeholder)**, comme demandé — à corriger modèle par modèle avec les vrais tarifs RICOH. La mensualité (Grenke, 2,1 %, 60 mois) se recalcule automatiquement dès qu'un prix est changé.
- Chaque modèle a maintenant 4 champs supplémentaires visibles dans la fiche d'édition : **Famille** (codage couleur du catalogue), **Badge distinctif** (ex. "Avec fax"), **Modèle jumeau** (le modèle à l'extérieur identique) et **Alerte anti-confusion** (texte ⚠️ affiché dès qu'on sélectionne ce modèle) — modifiables si besoin.
- **Coordonnées Xeler Informatique, contrat CAP (coût à la page) et financement** sont préremplis — à vérifier dans les autres onglets d'Administration.
- Le **RIB** (IBAN/BIC) a été laissé vide volontairement (je n'invente jamais ces données) — à compléter dans Administration → Entreprise si le PDF de devis doit les afficher.

## 4. Le catalogue : 26 modèles, système anti-confusion

Les 4 brochures RICOH fournies (`Communication/Copieurs`) couvrent 26 références au total (3 A4 N&B, 2 A4 Couleur, 9 A3 N&B, 12 A3 Couleur). Comme demandé, chaque modèle qui a un "jumeau" à l'apparence identique (option fax, finisseur, scanner LED HP en option — le "(A)" des brochures) porte :

- un **badge court** sur sa carte ("Avec fax", "Scanner LED HP en option"...)
- une **alerte rouge** dès qu'il est sélectionné dans un devis, avec un lien direct vers la fiche du modèle jumeau pour comparer avant de valider

Un **filtre par famille** (pastilles de couleur) permet de trier rapidement le catalogue et l'écran de chiffrage.

## 5. Le reste (PDF, email, historique...) fonctionne comme l'outil robots

Même moteur, mêmes écrans : génération PDF du devis avec fusion automatique de la fiche technique RICOH, envoi par email pré-rempli (mailto), Historique, Administration, export/import JSON pour partager le catalogue avec l'équipe. Voir le `LISEZ-MOI.md` de l'outil robots pour le détail de ces fonctionnalités, identiques ici.
