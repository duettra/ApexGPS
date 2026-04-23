# FAQ & dépannage

## « Mon triangle bleu ne s\'affiche pas »

Trois raisons possibles :

1. **GPS coupé.** Appuyez sur le bouton viseur dans la colonne de droite. Passe du gris au bleu. Voir [L\'écran carte → Suivre-moi](map.md#suivre-moi-viseur).
2. **Permission de localisation refusée.** Allez dans les Paramètres du téléphone → Apps → ApexGPS → Autorisations → Position → **Autoriser uniquement pendant l\'utilisation**, position **Précise**. Puis rouvrez ApexGPS.
3. **Pas de fix GPS.** En intérieur, près de grands bâtiments ou dans un canyon profond, la première acquisition peut prendre 30 s ou plus. Sortez si possible.

## « La carte revient à ma position toutes les quelques secondes »

C\'est le suivi verrouillé. Glissez la carte une fois — le bouton viseur passe en bleu plus clair et la carte reste où vous l\'avez mise. Le triangle continue ; seule la caméra arrête de vous suivre. Pour re-centrer : tap sur le viseur.

Voir [L\'écran carte → Suivre-moi](map.md#suivre-moi-viseur).

## « Comment couper complètement le GPS ? »

**Appui long** sur le viseur. GPS arrêté, triangle disparu, batterie économisée.

Le tap-to-toggle depuis l\'état verrouillé coupe aussi, mais l\'appui long saute l\'animation de re-centrage — utile si vous avez pané ailleurs et ne voulez pas que la carte saute avant de couper.

## « Quelqu\'un m\'a envoyé un lien de position — comment le voir ? »

Si le lien est du genre `https://apexgps.duttra.de/loc?lat=...&lon=...`, tap dessus depuis votre message. Avec ApexGPS installé, ça ouvre l\'app avec une cible rouge. Sans ApexGPS, ça ouvre une page web avec aperçu + lien d\'installation.

Les autres liens cartes (Google Maps, etc.) ouvrent votre app cartes habituelle — ils ne passent pas par ApexGPS.

Voir [Partager → Recevoir une position partagée](share-and-navigate.md#recevoir-une-position-partagée).

## « Puis-je enregistrer une trace pendant une rando ? »

Pas dans cette version. L\'enregistrement live est prévu pour une future version. Pour l\'instant les traces viennent de l\'import GPX (les vôtres depuis une autre app, ou celles d\'un autre).

## « Combien d\'espace l\'app prend-elle ? »

L\'app elle-même est petite (~10 Mo). Le stockage augmente avec :

- **Cache de navigation** — tuiles des zones regardées. Voir **Paramètres → Stockage**.
- **Régions hors ligne enregistrées** — tuiles pré-téléchargées via le hub Cartes. Peuvent être grosses (50-500 Mo par région selon les zooms).
- **Traces + points** — minuscules, généralement <1 Mo même avec des centaines d\'items.

Vider le cache via Paramètres → Stockage → Vider. Supprimer les régions via Cartes hub → tap sur une région → Supprimer.

## « La carte rame au zoom / pan »

Quelques pistes :

1. **Trop de traces chargées.** Liste Traces → filtre visibilité → masquer celles non utilisées aujourd\'hui. Ou supprimer en lot les vieux imports.
2. **Traces très détaillées.** **Paramètres → Données → Tout optimiser** — le nombre de points chute ~90 % sans changement visible.
3. **Zoom bas avec beaucoup de points.** Les points se regroupent automatiquement à zoom bas (un seul rond avec un compteur) — tap pour zoomer. Si le téléphone peine encore, le seuil cluster est fixe en code ; masquez plutôt des traces.
4. **Vieux téléphone.** ApexGPS vise Android moderne. Sur un modèle d\'avant 2020, des lenteurs sont inévitables avec 500+ traces à l\'écran.

## « Je ne vois pas la nouvelle version dans le Play Store »

Vous êtes testeur fermé et on vous a notifié d\'une maj. Si rien n\'apparaît :

1. Play Store → icône de profil (haut droite) → **Gérer les applis et l\'appareil** → **Mises à jour disponibles** → actualiser. Si ApexGPS apparaît, **Mettre à jour**.
2. Toujours rien ? Rouvrez le lien d\'invitation testeur original. Puis force-stop Play Store, rouvrir, rechercher ApexGPS.
3. Toujours rien ? **Paramètres → Apps → Google Play Store → Stockage → Vider le cache**. Rouvrir, rechercher à nouveau.
4. Le CDN Google prend 2–24 h après « auto-publication ». Si vous venez d\'être informé, attendez quelques heures.

## « Puis-je utiliser ApexGPS sans donner la permission de localisation ? »

Globalement oui. Vous pouvez importer des GPX, afficher des traces, planifier, mesurer, gérer des points et pré-télécharger des régions — tout sans position. Ce que vous perdez :

- Triangle de position live.
- Suivi / tri par plus proche.
- La fonction Partager la position (pas de position à partager).
- Navigation vers un point (pas de « vous » pour tracer une ligne).

## « L\'app envoie-t-elle ma position quelque part ? »

Non. ApexGPS ne fait aucune requête réseau avec votre position. La seule activité réseau sortante est la récupération de tuiles, indistincte de consulter une carte — les serveurs voient une IP + des coordonnées de tuile, rien sur vous. Voir la [politique de confidentialité](/privacy.html).

Le partage via le bouton Partager est entièrement à votre initiative — vous choisissez l\'app (WhatsApp, etc.) et le destinataire.

## « Le téléphone Android de mon ami ouvre le lien dans le navigateur, pas dans ApexGPS »

Le lien ne va direct dans ApexGPS que sur les appareils où la vérification App Links Google est passée. Une nouvelle installation a parfois besoin d\'un premier lancement avant que la vérification ne prenne. Demandez à votre ami :

1. Ouvrir ApexGPS une fois, accorder la position, fermer.
2. Re-tap sur votre lien partagé.

Ça devrait ouvrir directement dans l\'app. Sinon, Android propose peut-être un sélecteur — il peut choisir « Toujours ouvrir dans ApexGPS ».

## « Puis-je restaurer une sauvegarde ApexGPS sur iPhone ? »

Non. ApexGPS est uniquement Android. Le format de sauvegarde est spécifique à l\'app.

## « Où sont mes données physiquement ? »

Sur votre téléphone, dans le stockage privé d\'ApexGPS (`/data/data/com.apexgps.app/` avec accès root — sinon inaccessible). Traces + points dans une base SQLite ; paramètres dans un fichier prefs ; tuiles comme fichiers image.

Rien n\'est envoyé nulle part. Pour sauvegarder, utilisez [Sauvegarde & restauration](backup.md).

---

**Toujours bloqué ?** [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me) — rapports de bug bienvenus.
