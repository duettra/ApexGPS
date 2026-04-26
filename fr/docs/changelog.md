# Nouveautés

Changements visibles par l\'utilisateur, plus récents en premier. Pour les refactos internes / sauts de version pur, voir le repo privé.

---

## 1.32.2 — 26 avr. 2026 — Météo activée par défaut + traductions complètes + bouton retour des Cartes

- **La météo est désormais activée d'origine.** La pastille de prévision et la ligne « Météo ici » sur les waypoints sont visibles sans devoir basculer un réglage. Vous pouvez toujours désactiver la météo dans **Paramètres → Météo** si vous préférez aucun appel réseau — les installations existantes conservent votre réglage précédent.
- **Traductions complètes pour la fonction météo.** Tous les textes météo — la pastille, la feuille (panneau actuel, bandeau 24 heures, tendances humidité / pression, bandeau 7 jours, étiquettes coucher / UV / pression / point de rosée), les rangées dans Paramètres et le titre du chapitre du guide — sont maintenant traduits en allemand, français, espagnol, polonais et arabe. Les libellés de conditions météo (« Pluie légère », « Orage + grêle », « Partiellement nuageux », …) suivent le vocabulaire météorologique standard de chaque langue.
- **Menu Cartes : le bouton retour referme désormais une carte ouverte avant de quitter.** Quand **Télécharger une nouvelle zone** ou **Cartes hors ligne enregistrées** était dépliée, retour ignorait le menu Cartes et vous renvoyait directement à la carte principale. Désormais retour referme d'abord la carte ouverte ; un appui de plus vous ramène à la carte principale. Cela correspond au comportement ailleurs (sous-écrans Paramètres, sélection multiple dans les listes de traces / waypoints).

---

## 1.32.1 — 25 avr. 2026 — Météo : petites corrections

- **Icônes soleil / lune correctes au passage de minuit.** Le bandeau météo sur 24 heures affichait des glyphes lune sur les heures d\'après-midi du *lendemain* (11h00, 14h00, 17h00) lorsqu\'on ouvrait la feuille tard le soir. Chaque heure choisit désormais son propre lever / coucher de soleil, donc les heures de jour montrent toujours les icônes côté soleil.
- **La prévision waypoint utilise vraiment l\'altitude du waypoint.** Quand un waypoint sommet se trouvait pratiquement aux mêmes coordonnées que votre position GPS actuelle, la prévision en cache pour la position courante était parfois renvoyée pour le waypoint au lieu d\'une requête fraîche tenant compte de l\'altitude. Sur un sommet à 1480 m la prévision était ~9 °C trop chaude. Le cache utilise maintenant l\'altitude comme clé, donc l\'altitude stockée du waypoint est toujours respectée.

---

## 1.32.0 — 25 avr. 2026 — Météo : finition par-point, plus d\'overlays carte

Après 1.31.0, les overlays météo en grille n\'ont pas passé le test visuel sur les niveaux de zoom de randonnée — ils apparaissaient comme des carrés colorés sans alignement réel avec le terrain, et la rangée du bas (curseur d\'overlay + pastille + barre vitesse / altitude / distance) prenait trop d\'écran. Cette version dépouille la carte et mise sur la feuille par-point, là où les détails utiles vivent.

- **Overlays carte retirés.** Plus de radar de précipitations ni de couvert nuageux sur le fond de carte, plus de curseur temporel. L\'écran **Paramètres → Météo** se réduit à un seul interrupteur principal.
- **Feuille par-point plus riche.** La feuille météo (toucher la pastille ou la ligne « Météo ici » d\'un waypoint) montre maintenant : panneau actuel avec emoji météo, température, « ressenti » ; lignes pour vent / humidité / point de rosée / pression / UV / coucher ; bandeau 24 heures avec icônes météo horaires + température ; tendance d\'humidité (bleu clair) et tendance de pression (vert) ; et bandeau 7 jours avec maxi / mini + icône. Conçu pour tenir sur un écran de téléphone classique.
- **L\'altitude par-waypoint est envoyée à la prévision.** Les waypoints avec un champ altitude stocké la transmettent au modèle, donc les prévisions de sommet utilisent la vraie hauteur au lieu de l\'altitude moyennée grossière. Idem pour la prévision de la pastille — elle utilise votre altitude GPS.
- **La pastille s\'aligne avec la carte du waypoint.** Le texte de la pastille de la barre de stats correspond désormais à ce que vous voyez en touchant un waypoint : emoji + temp + vent. Un fin séparateur a été ajouté entre la pastille et la rangée vitesse / altitude / distance pour qu\'elles se lisent comme un seul panneau.

---

## 1.31.0 — 25 avr. 2026 — Météo

ApexGPS affiche maintenant des informations météo de niveau randonnée depuis des APIs publiques gratuites, entièrement opt-in.

- **Pastille de prévision dans la barre de stats.** Une fois la météo activée dans **Paramètres → Météo**, une petite pastille au-dessus de la barre vitesse / altitude / distance affiche les conditions actuelles à votre position GPS : température, vent, humidité. La pastille se met à jour toutes les 15 minutes en ligne et indique quand les données sont périmées ou que vous êtes hors-ligne (grise et ajoute une horloge).
- **Feuille déroulante.** Touchez la pastille (ou la nouvelle ligne « Météo ici » d\'un panneau de waypoint) pour le détail complet — relevés actuels, prochaines 24 heures sous forme de courbe de température + barres de précipitations, et bandeau 7 jours avec maxi/mini et icônes.
- **Rafraîchissement manuel.** Un bouton ↻ dans l\'en-tête force une requête fraîche après reconnexion.
- **Overlays animés sur la carte.** Une nouvelle section **Overlays** dans le hub Cartes ajoute deux interrupteurs indépendants : radar de précipitations (pluie animée code couleur, 2 dernières heures + nowcast 30 min) et satellite nuageux (sommets nuageux IR géostationnaires). Ils n\'envoient pas votre position — ce sont juste des tuiles, indépendantes de la pastille météo.
- **Vie privée d\'abord.** Tout est désactivé par défaut. Les prévisions viennent d\'Open-Meteo, le radar de RainViewer ; deux APIs publiques gratuites sans compte ni clé. Votre position n\'est envoyée que si vous activez explicitement la pastille.

Lisez le chapitre complet sous **Paramètres → Guide d\'utilisation → Météo**.

---

## 1.30.2 — 25 avr. 2026

- **Tap sur la boussole respecte le verrouillage de rotation.** Appui long sur la boussole pour verrouiller la rotation de la carte ; une fois verrouillée, un simple tap sur la boussole ne ramène plus la carte au nord. (Il faudrait d\'abord rappuyer long pour déverrouiller, puis tapoter.) Cela rétablit l\'intention du verrou — figer l\'angle contre les entrées involontaires, y compris un tap parasite sur la boussole.
- **Notifications plus brèves, moins intrusives.** Les messages « Supprimé … » / « Déplacé … » / « Arrivé » / suivi-verrouillé / auto-pause-localisation s\'affichent maintenant comme un bref Toast Android (~2 s, overlay système) au lieu d\'un snackbar de 4 s qui bloquait le bas de la carte. Vous pouvez toucher un autre waypoint juste après en avoir supprimé un, sans attendre.

---

## 1.30.0 / 1.30.1 — 25 avr. 2026 — Qualité d\'enregistrement

La première randonnée après 1.29 (4 h 10 min, 9,98 km) a révélé que l\'enregistrement live de trace stockait beaucoup plus de points que nécessaire et avait absorbé une fausse chute d\'altitude due à une lecture d\'altitude bloquée. Les deux corrigés :

- **Enregistrements plus légers, plus lisses.** Un nouveau filtre ne garde un fix que si vous avez bougé d\'au moins 5 m, 15 secondes se sont écoulées ou l\'altitude a changé de 3 m+. Les fixes très imprécis (>25 m) sont écartés. Sur la randonnée test : ~4600 → ~1500 points stockés, aucun changement visible de la trace, distance inchangée. Moins de stockage, exports GPX plus petits, même trace.
- **Plus de fausses chutes d\'altitude.** Le fused location provider de certains Android se bloque et renvoie la même altitude en cache (par ex. `139 m` en randonnée à 1200 m) pendant des minutes. L\'enregistrement traite désormais ces lectures comme « pas de valeur » plutôt que de persister le mauvais chiffre. Le profil d\'altitude montre une coupure propre sur la fenêtre fautive au lieu d\'un creux à zéro, et les stats montée / descente ne reflètent que les vraies variations.
- **Altitude MSL sur Android 14+.** Quand disponible, l\'enregistrement utilise l\'altitude moyenne au-dessus du niveau de la mer plus honnête que le fallback WGS84, sujet au bug ci-dessus.

Si vous avez un enregistrement antérieur à 1.30.0 avec une mauvaise altitude, vous pouvez le refaire — l\'affichage dans la trace utilise les points persistés. Pas d\'étape de migration.

---

## 1.29.0 — 24 avr. 2026

- **Enregistrement live de trace.** Appuyez sur la pastille rouge en haut à gauche de la carte pour démarrer l\'enregistrement de votre sortie. Un chrono live `HH:MM:SS` remplace la pastille ; tap pour **Pause / Terminer / Supprimer**. Votre parcours se dessine comme une ligne rouge au fil de vos déplacements. Sur **Terminer** l\'enregistrement est sauvegardé comme nouvelle Trace et le panneau s\'ouvre automatiquement pour consulter distance, dénivelé et profil d\'altitude tout de suite.
- **Rogner la trace.** Sur l\'écran détail, **Rogner la trace** ouvre une boîte avec une mini-carte en aperçu et deux poignées glissables sur le graphique d\'altitude. Coupez un mauvais début (pas encore de fix GPS) ou une fin parasite (oublié d\'appuyer sur Terminer) sans perdre le reste de la trace. Destructif — une étape de confirmation dit exactement combien de points vous allez perdre.
- **Tag d\'activité par trace.** L\'écran Détail de trace a un nouveau menu **Activité** : Randonnée · Marche · Course · Vélo · Tout-terrain · Parapente. Les enregistrements démarrent par défaut en Randonnée ; les traces importées sans tag.
- **Altitude de point.** Le sheet d\'édition de point a un nouveau champ optionnel **Altitude (m)** — remplissez-le quand vous voulez porter une altitude pour un sommet / col connu / etc. Vide = aucune altitude stockée (comme pour les points importés sans donnée d\'altitude aujourd\'hui).
- **Détail de trace + édition de point rafraîchis.** Cartes groupées, libellés de section, icônes sur chaque ligne, icône spécifique à l\'activité sur la puce Activité, **Supprimer** encadré rouge pour coller à l\'action destructive, nouvelle stat **Points** sur l\'écran trace. L\'édition de point est plus serrée — le formulaire entier tient désormais au-dessus de la barre de navigation système sur la plupart des téléphones sans défilement.
- **Récupération après mort du processus.** Si Android tue l\'app en pleine sortie (mémoire faible, arrêt forcé), la ligne est préservée. Rouvrez l\'app et l\'enregistrement revient en pause — reprendre, terminer ou jeter.
- **Économie de batterie : cadence GPS adaptative.** Pendant l\'enregistrement écran éteint, la cadence des fixes passe de 2 s à 10 s pour économiser la batterie. Dès que vous déverrouillez le téléphone elle revient à 2 s pour la fluidité. Entièrement automatique.
- **Protection localisation système.** Appuyer sur enregistrer alors que l\'interrupteur de localisation système Android est désactivé affiche désormais un message avec un raccourci **Paramètres** au lieu de démarrer silencieusement un enregistrement mort.
- **Indice no-fix.** Si vous appuyez sur enregistrer avant que le GPS ait acquis un fix, un court message *« Acquisition GPS… »* vous explique pourquoi la ligne n\'a pas démarré. L\'enregistrement commence dès que le premier fix arrive.
- **Supprimé :** le bouton panique optionnel. La zone en haut à gauche appartient maintenant à la pastille d\'enregistrement.

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
