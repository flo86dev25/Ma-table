# 🍽 Ma Table — Planificateur de repas familial

> Application web progressive (PWA) de planification des repas en famille.

![Version](https://img.shields.io/badge/version-1.0.2-terracotta?style=flat-square)
![Firebase](https://img.shields.io/badge/Firebase-Firestore-orange?style=flat-square&logo=firebase)
![PWA](https://img.shields.io/badge/PWA-installable-green?style=flat-square)
![Android](https://img.shields.io/badge/Android-APK-brightgreen?style=flat-square&logo=android)
![Licence](https://img.shields.io/badge/licence-privée-red?style=flat-square)

**Ma Table** permet de gérer un calendrier de menus partagé, une liste de courses intelligente et un carnet de recettes, le tout synchronisé en temps réel entre plusieurs membres d'un même foyer.

---

## ⚠️ Information importante — Compatibilité email

La **vérification de compte** et la **réinitialisation de mot de passe** par email peuvent ne pas fonctionner avec certains opérateurs français (Orange, SFR, Bouygues, Free…). Ces emails sont bloqués par leurs filtres anti-spam.

✅ Ces fonctionnalités fonctionnent normalement avec une adresse **@gmail.com**.

Vous pouvez quand même **utiliser l'application et toutes ses fonctionnalités normalement**.

Pour tout problème : [flo86dev25@gmail.com](mailto:flo86dev25@gmail.com) ou le formulaire de contact dans l'application.

---

## 📲 Installer l'application

### 🤖 Android — APK natif

Téléchargez et installez l'APK directement :

👉 **[Télécharger Ma Table pour Android](https://github.com/flo86dev25/Ma-table/releases/latest/download/ma-table.apk)**

> ⚠️ Android peut afficher un avertissement « Application inconnue ». Appuyez sur **Installer quand même** — l'app est sûre, elle n'est pas distribuée via le Play Store.
> Le lien pointe toujours vers la **dernière version** disponible.

### 💻 PC (Chrome ou Edge) — PWA

1. Ouvrez **[ma-table-69581.web.app](https://ma-table-69581.web.app/)** dans Chrome ou Edge
2. Inscription à l'application
3. Cliquez sur **« Installer »** (icône bleue)
4. L'app apparaît sur votre bureau ✅

### 🍎 iPhone (Safari) — PWA

1. Ouvrez **[ma-table-69581.web.app](https://ma-table-69581.web.app)** dans Safari
2. Appuyez sur le bouton **Partager 📤** (en bas de l'écran)
3. Choisissez **« Sur l'écran d'accueil »**
4. Appuyez sur **« Ajouter »** ✅

---

## ✨ Fonctionnalités

### 1. Authentification & Gestion du compte

| Fonctionnalité | Description |
|---|---|
| Inscription | Création de compte avec e-mail, mot de passe (min. 6 car.) et prénom affiché. |
| Connexion | Identification par e-mail / mot de passe avec affichage de l'e-mail dans la barre de navigation. |
| Mot de passe oublié | Envoi d'un e-mail de réinitialisation via Firebase Auth. *(Peut ne pas fonctionner avec certains opérateurs — voir alerte ci-dessus.)* |
| Vérification e-mail | Après inscription, un e-mail de vérification est envoyé. Un bandeau d'information s'affiche si l'email n'est pas vérifié — l'utilisateur peut le fermer et utiliser l'application normalement sans restriction. *(Peut ne pas fonctionner avec certains opérateurs — voir alerte ci-dessus.)* |
| Déconnexion | Bouton « Déco. » dans la barre de navigation, avec confirmation. |
| Suppression de compte | Suppression totale des données personnelles. Si le foyer est partagé, seule la participation est retirée ; si l'utilisateur est seul, le foyer entier est supprimé. Confirmation par saisie de « SUPPRIMER ». |
| Popover « Mon compte » | Accès rapide à l'e-mail, statut de vérification, partage du foyer, rejoindre un foyer, formulaire de contact et suppression de compte. |

---

### 2. Foyers partagés & Synchronisation

| Fonctionnalité | Description |
|---|---|
| Création automatique de foyer | À la première connexion, un foyer unique est créé et un code de partage de type « LUNA-X7K2 » est généré. |
| Code de partage | Code lisible et copiable depuis le modal « Partager mon foyer » ou le popover Mon compte. |
| Rejoindre un foyer | Saisie d'un code de partage pour rejoindre le foyer d'un autre membre. |
| Synchronisation temps réel | Les modifications sont synchronisées instantanément entre tous les membres via Firestore onSnapshot. |
| Badge de synchronisation | Icône dans la barre de navigation indiquant l'état de la dernière sauvegarde. |
| Bannière de conflit | Notification visuelle quand un autre membre modifie un repas : affiche son prénom, l'heure et un lien vers la semaine modifiée. |
| Mode hors-ligne | Données sauvegardées en localStorage. À la reconnexion, la file d'attente est envoyée à Firestore. |
| Purge automatique | Les repas de plus de 180 jours sont supprimés automatiquement au démarrage. |

---

### 3. Calendrier des repas

| Fonctionnalité | Description |
|---|---|
| Vue semaine / quinzaine | Affichage de 7 ou 14 jours consécutifs avec navigation par semaine (flèches). |
| 4 moments par jour | Petit déjeuner, Déjeuner, Goûter, Dîner. Petit déjeuner et Goûter sont rétractables. |
| Détail du repas | Modal de saisie (Apéritif, Entrée, Plat, Accompagnement, Dessert) avec labels personnalisables. |
| Suggestions de recettes | Suggestions des recettes du carnet classées par nombre d'utilisations passées. |
| Planification depuis une recette | Mode « Planifier » activable depuis la fiche recette : clic sur une cellule pour y placer la recette. |
| Ajout d'ingrédients aux courses | Lors de la planification, proposition d'ajouter les ingrédients directement à la liste de courses. |
| Qui cuisine ? | Sélecteur par jour pour attribuer un cuisinier parmi les convives ; affiché en doré et dans le PDF. |
| Échange de repas (Swap) | Mode d'échange permettant de déplacer un repas d'une cellule à une autre en deux clics. |
| Export PDF du menu | Génération d'un PDF A4 du menu sur 1 à 4 semaines, avec tableau jours × repas et cuisiniers. |
| Vue œil recette | Icône sur chaque repas lié à une recette pour ouvrir la fiche directement depuis le calendrier. |

---

### 4. Liste de courses

| Fonctionnalité | Description |
|---|---|
| Ajout d'article | Saisie avec nom, quantité et catégorie (Fruits & Légumes, Viandes, Épicerie, Surgelés, Maison, Animaux…). |
| Autocomplétion | Suggestions en temps réel issues des favoris et d'une base ~500 articles précatégorisés. Navigation clavier. |
| Cochage des articles | Clic pour marquer comme acheté (barré + grisé). Tri automatique : non cochés en tête, cochés en bas. |
| Regroupement par catégorie | Affichage groupé avec en-têtes de catégorie et compteurs. |
| Produits favoris | Sauvegarde d'un article comme favori pour le réutiliser rapidement. Filtrage par catégorie. |
| Données saisonnières | Onglet « Saison » : fruits, légumes et poissons du mois courant. Badge pour la pleine saison. |
| Export PDF / texte | Téléchargement de la liste en PDF ou copie en texte brut. |
| Import / Export JSON | Importation et exportation de la liste en fichier JSON. |

---

### 5. Carnet de recettes

| Fonctionnalité | Description |
|---|---|
| Création / édition | Formulaire complet : emoji, nom, temps, difficulté, personnes, ingrédients (nom + quantité + catégorie), instructions, catégories multiples, favoris. |
| Sélecteur d'emoji | Grille d'emojis intégrée pour choisir l'icône de la recette. |
| Recettes prédéfinies | Bibliothèque de recettes intégrées versionnées, réinitialisée à chaque mise à jour. |
| Catégories & filtres | Filtre par catégorie (Apéritif, Dessert, Végétarien, Viande, Pasta, Soupes…). Ajout, renommage et suppression de catégories personnalisées. |
| Favoris | Marquage ★ ; filtre « Mes recettes préférées » dans la barre de catégories. |
| Fiche recette | Vue détaillée : métadonnées, ingrédients avec catégorie, instructions. |
| Planifier une recette | Bouton « Planifier » depuis la fiche : bascule en mode planification du calendrier. |
| Export PDF d'une recette | PDF A4 mise en page soignée : en-tête coloré, bloc Ingrédients, bloc Instructions. |
| Import / Export JSON | Import/export de toutes les recettes ou d'une seule en fichier JSON. |

---

### 6. Convives, Notifications & Rappels

| Fonctionnalité | Description |
|---|---|
| Gestion des convives | Modal « Gérer les personnes » : ajout et suppression de noms de convives partagés dans le foyer. |
| Attribution du cuisinier | Sélecteur par jour dans l'en-tête du calendrier pour désigner le cuisinier. |
| Activation notifications | Bouton dans la barre (desktop) ou menu drawer (mobile) pour activer/désactiver. |
| Configuration des rappels | Modal de paramétrage : heure de rappel pour chaque repas (midi / soir), bascule on/off par type. |
| Contenu du rappel | La notification affiche le menu du jour et le cuisinier désigné. |
| Service Worker (web) | Alarmes persistées dans IndexedDB du SW, déclenchées même app fermée (vérification toutes les 60 s). |
| Notifications natives Android | Sur l'app Android (Capacitor), utilisation des LocalNotifications système. |

---

### 7. PWA, Interface & Personnalisation

| Fonctionnalité | Description |
|---|---|
| Installation PWA | Bouton « Installer » dans la barre (desktop) et le drawer (mobile). Instructions affichées pour iOS/Safari. |
| Partage multiplateforme | Modal « Partager l'application » avec instructions séparées : Android (APK via QR code), PC (PWA via Chrome/Edge) et iPhone (Safari + écran d'accueil). Inclut une alerte sur la compatibilité email avec certains opérateurs. |
| Icône PWA personnalisée | Icône « Ma Table » affichée lors de l'installation sur bureau PC, écran d'accueil iPhone ou Android (PWA). |
| Mode hors-ligne | Service Worker cache-first : l'app fonctionne sans connexion, modifications mises en file d'attente. |
| Application Android native | Version Capacitor (APK) : mode immersif, notifications locales, partage natif de PDF. |
| Détection de mise à jour APK | Au démarrage de l'app Android, vérification automatique d'une nouvelle version sur GitHub Releases. Un bandeau s'affiche avec lien de téléchargement direct si une version plus récente est disponible. |
| Thème clair / sombre | Bascule dans la barre. Préférence mémorisée en localStorage. |
| Navigation responsive | 3 onglets (Calendrier, Courses, Recettes). Drawer mobile (hamburger) sur petit écran. |
| Onboarding | Écran de bienvenue 7 slides (swipe, clavier) présenté à la première connexion. Accessible à tout moment via le bouton « Présentation » dans le menu. |
| Formulaire de contact | Formulaire intégré (Formspree) prérempli avec les données du compte connecté. |
| Sécurité des données | Stockage Firestore + localStorage taggé UID. Débounce 600 ms des sauvegardes. Flag notify pour bannières collaboratives. |

---

## 🛠 Stack technique

- **Frontend** : HTML / CSS / JavaScript vanilla (single file)
- **Backend** : Firebase (Firestore, Authentication, Hosting)
- **Android** : Capacitor (APK natif)
- **PDF** : jsPDF
- **Notifications** : Service Worker + IndexedDB (web) / LocalNotifications (Android)

---

## 📄 Licence

Projet personnel — tous droits réservés © 2026 flo86dev25.

---

*Documentation mise à jour pour la version 1.0.2*
