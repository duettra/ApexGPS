# Nouveautés

Changements visibles par l\'utilisateur, plus récents en premier. Pour les refactos internes / sauts de version pur, voir le repo privé.

---

## 1.28.0 — 24 avr. 2026

- **Arabe ajouté.** العربية rejoint l\'allemand, le français, l\'espagnol et le polonais aux côtés de l\'anglais. Six langues d\'interface dans **Paramètres → Apparence → Langue**.
- **Panneau des points maintenant traduit.** Un tap sur un point affichait auparavant « Elev 145 m · Dist 0,42 km » en anglais — quelle que soit la langue de l\'app. Désormais il suit la langue (ex. « Alt 145 m · Dist 0,42 km »).
- **Les chiffres restent occidentaux dans toutes les langues.** Coordonnées, distances, altitudes, caps — toujours `25.165`, `145`, `0.42`. Cohérent avec Google Maps / WhatsApp.

---

## 1.27.0 — 23 avr. 2026

- **Cinq langues d\'interface.** Allemand, français, espagnol, polonais et anglais. Choix dans **Paramètres → Apparence → Langue**, ou « Système par défaut » pour suivre le téléphone.
- **Guide hors ligne dans votre langue.** Les 11 chapitres du guide utilisateur (Paramètres → À propos → Guide utilisateur) sont traduits.
- **La langue survit à une restauration.** La langue choisie est incluse dans le ZIP.
- **Barre de stats aussi traduite.** VIT / ALT / DIST changent avec la langue.

---

## 1.26.2 — 22 avr. 2026

- **Clé API Thunderforest chiffrée au repos.** La clé collée dans **Paramètres → Avancé** est stockée dans un coffre-fort basé sur l\'Android Keystore, plus en clair. Les clés existantes migrent automatiquement au premier lancement. Les sauvegardes incluant les paramètres transportent la clé dans le ZIP (nécessaire pour la portabilité) — un nouvel avertissement rouge dans le dialogue de sauvegarde le rappelle.
- **Restauration plus sûre.** La restauration rejette désormais les ZIP avec traversal, limite à 100 000 entrées, 500 Mo par entrée et 2 Go total décompressé. Les sauvegardes malformées ne peuvent plus remplir votre stockage ni sortir du dossier de sauvegarde.
- **Bouton Annuler sur la sauvegarde.** Pendant une sauvegarde en cours, vous pouvez cliquer **Annuler** sous le bouton occupé pour interrompre sans attendre.
- **Progression de l\'import GPX.** Un snackbar « Import GPX… » s\'affiche pendant les gros imports — l\'app ne semble plus gelée.
- **Service de localisation plus fiable sur Android 14+.** Le service GPS démarre correctement sur Android 14 et 15 (auparavant parfois tué silencieusement). Périmètre du wake-lock réduit — devrait améliorer la batterie en suivi long.
- **Correction aperçu tuiles + hygiène en arrière-plan.** L\'aperçu de la fiche Carte hors ligne charge sans bloquer l\'UI. Interne : le service de téléchargement de tuiles ne peut plus ANR au shutdown. Les builds release n\'expulsent plus de logs de debug.
- **Supprimé :** le lien Buy-me-a-coffee dans Paramètres → À propos. ApexGPS reste gratuit sans pub, sans tracking, sans cloud.
- **Interne (pour les curieux) :** la base Room a désormais des migrations explicites (1→2→3) ; les upgrades préservent vos traces et points même si le schéma change. Le wipe au downgrade reste — sideloader une vieille APK par-dessus une neuve réinitialisera la base.

---

## 1.26.1 — 22 avr. 2026

- **Aperçu carte hors ligne — biseau corrigé.** L\'aperçu dans **Menu → Cartes hors ligne enregistrées → [tap une région]** débordait sur les stats et le bouton « Afficher sur la carte ». Il est désormais correctement coupé sur son rectangle 1,6:1.
- **Lien « Lire en ligne » in-app** dans Paramètres → À propos pointe vers `apexgps.duttra.de/docs/` (la doc rendue) au lieu de la vue brute GitHub.
- **Buy me a coffee.** Nouvelle section Support dans **Paramètres → À propos**. ApexGPS reste gratuit sans pub ni tracking — si vous aimez, un petit pourboire aide à financer les nouvelles fonctions.

---

## 1.26.0 — 21 avr. 2026

- **Guide utilisateur hors ligne.** Le guide complet de 10 chapitres est embarqué dans l\'app — ouvrez **Paramètres → À propos** et tap sur un chapitre pour le lire sans connexion. Les liens entre chapitres marchent in-app ; les liens externes ouvrent le navigateur.
- **Charger les données d\'exemple.** Nouveau bouton dans **Paramètres → Données** charge 3 points (Sommet / Point de vue / Départ de sentier) et 3 traces de longueurs et profils variés. Pour essayer l\'app sans GPX perso. Supprimables ensuite — ce sont des traces/points normaux après import.
- **Naviguer active le GPS automatiquement.** Tap sur Naviguer depuis une position partagée ou un point active la position en direct si elle était coupée. Plus de blocage « Acquisition GPS… » alors que vous vouliez démarrer la nav.
- **Pan de la carte re-déverrouille le suivi.** Régression des builds 1.2x : sous mises à jour GPS continues, la carte revenait à votre position chaque seconde même après un pan. Pan sur la carte → caméra déverrouillée (FAB en bleu moyen) comme avant ; le triangle continue de se mettre à jour.
- **Symboles qui plantaient.** Importer un GPX avec les symboles Point de vue / Col / Cascade / Pique-nique / Eau potable / Panneau / Ruines / Toilettes pouvait planter l\'app au rendu. Corrigé — les 32 symboles s\'affichent correctement.

---

## 1.25.x — 21 avr. 2026

- **Import GPX depuis la liste Traces** (icône dossier en haut à droite). Idem liste Points. Le FAB d\'import de la carte est supprimé — ce sont les écrans liste qui gèrent l\'import.
- **Ajouter un point par coordonnées** — « + » bleu dans la liste Points ouvre la boîte d\'édition avec Lat/Lon vides. Tapez ou collez une chaîne `lat, lon` dans Latitude (division automatique).
- **Modifier les coordonnées d\'un point.** Lat et Lon sont éditables avec validation inline (lat ∈ [-90, 90], lon ∈ [-180, 180]).
- **FAB Suivre-moi déplacé en bas** de la colonne de droite — au plus près du pouce. Couches au-dessus, Mesurer encore au-dessus.

---

## 1.24.x — 19 avr. 2026

- **Boussole de navigation plein écran.** En navigation, tap sur 🧭 dans la barre ouvre une grande boussole analogique : distance / ETA / vitesse / altitude en haut, cadran tournant avec aiguille bleue pointant le point, lat/lon/cap/précision en bas. Glisser vers le bas pour minimiser. Voir [Partager → La boussole](share-and-navigate.md#la-boussole-de-navigation-plein-écran).
- **Partager un point.** Panneau point avec un bouton Partager à côté de Naviguer et Modifier. Envoie le point via n\'importe quelle app de messagerie ; les destinataires avec ApexGPS l\'ouvrent directement comme position partagée, à enregistrer.
- **Barre de nav + barre stats plus propres.** La barre de nav affiche cap + ETA (cap en bleu — live), la distance est dans DIST de la barre stats. Plus de doublons.
- Aiguille de la boussole épurée au pivot central (polish visuel).

## 1.23.0 — 19 avr. 2026

- **Naviguer vers n\'importe quel point** directement depuis son panneau. Tap sur l\'icône personne marchant à côté de Modifier — même ligne bleu clair pointillée + distance/cap live + arrêt auto à 20 m que la nav de position partagée. Voir [Points → Naviguer vers un point](waypoints.md#naviguer-vers-un-point).

## 1.22.2 — 19 avr. 2026

- **Lien guide utilisateur** dans Paramètres → À propos. Ouvre cette doc dans le navigateur.

## 1.22.0 — 19 avr. 2026

- **Bouton panique** (opt-in). Pastille rouge ⚠ en haut à gauche. Tap → ouvre le panneau de partage et active le GPS si besoin. À activer dans **Paramètres → Apparence → Bouton panique**. Voir [Partager → Bouton panique](share-and-navigate.md#bouton-panique-optionnel).

## 1.21.0 — 19 avr. 2026

- **Suivre-moi : pannez librement.** Glisser la carte ne se bat plus avec le GPS — le triangle continue, mais la carte reste où vous l\'avez posée. Tap sur le bouton pour re-centrer. Appui long pour couper le GPS instantanément. Trois états visibles (off / verrouillé / déverrouillé).
- **Boussole vers nord animée** au lieu de sauter. Retour au nord plus doux.

## 1.20.0 — 19 avr. 2026

- **Naviguer vers une position partagée.** Quand quelqu\'un vous partage un lien `apexgps.duttra.de`, tap sur Naviguer dans la barre du bas pour dessiner une ligne bleu clair pointillée de votre position à la sienne avec distance et cap live. Arrêt auto à 20 m. Voir [Partager → Naviguer vers une position partagée](share-and-navigate.md#naviguer-vers-une-position-partagée).
- **Repère visuel des positions partagées.** Une cible rouge apparaît à l\'endroit partagé. [Enregistrer] comme point ou [Masquer] pour effacer.

## 1.19.0 — 19 avr. 2026

- **Liste Points : filtre + tri.** Filtre par couleur ou symbole, tri par date / nom / plus proche. Même chose que les Traces. Voir [Points → Liste des points](waypoints.md#liste-des-points-menu--points).
- **Format de message partagé plus propre** — URL étiquetées (`ApexGPS:` / `Google Maps:`) avec ligne vide au-dessus.

## 1.18.x — 19 avr. 2026

- **Partager votre position actuelle.** Tap sur le triangle bleu → panneau info avec altitude, précision, heure, batterie → Partager via WhatsApp, SMS, e-mail, etc. Détails dans [Partager & naviguer](share-and-navigate.md).
- **App Links.** Les positions partagées depuis ApexGPS ouvrent directement l\'app sur les appareils qui l\'ont, avec marqueur rouge.
- **Fallback web** — si le destinataire n\'a pas ApexGPS, le lien ouvre une page avec aperçu + bouton Google Maps.

## 1.17.6 — 18 avr. 2026

- **Hub Cartes** redessiné. Téléchargement nouvelle zone et cartes hors ligne enregistrées vivent sur un seul écran, en cartes dépliables. Voir [Cartes hors ligne](offline-maps.md).
- Correction coins noirs à la rotation (plus de triangles noirs sur les bords).

## 1.16.0 — 17 avr. 2026

- **Paramètres** réorganisés en sous-écrans (Apparence / Stockage / Données / Clés API / À propos) avec aide inline.
- **Taille des points** (Petit / Normal / Grand / XL) dans Apparence.
- **Verrouillage rotation au lancement** — pour ceux qui haïssent les rotations accidentelles.

## 1.15.0 et antérieures

- App noyau : import GPX, liste traces, points avec 32 symboles, téléchargement cartes hors ligne, boussole + rotation, mesure de distance, sauvegarde/restauration ZIP, optimisation de trace.

---

*Pour un niveau de détail bug-report ou contexte dev, voir le [repo privé](mailto:sandwalker.one@proton.me) — contacter le développeur pour l\'accès.*
