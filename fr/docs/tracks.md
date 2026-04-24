# Traces

Une **trace** est un chemin enregistré — une série de points GPS reliés comme une ligne sur la carte. Vous obtenez des traces soit en les **enregistrant** en direct dans ApexGPS, soit en **important** des fichiers GPX (depuis GaiaGPS, Strava, Garmin Connect, wikiloc.com ou tout autre export GPX).

## Enregistrement

Appuyez sur la **pastille d\'enregistrement** rouge en haut à gauche de la carte. La pastille se déploie en un chip de temps écoulé live (`00:12:43`) et une ligne rouge de miettes commence à dessiner votre sortie sur la carte au fur et à mesure que de nouveaux fixes GPS arrivent.

### Pendant l\'enregistrement

- **Tap sur le chip chrono** pour un menu :
  - **Pause** — gèle le chrono ; les nouveaux fixes ne sont plus ajoutés à la ligne tant que vous n\'appuyez pas sur **Reprendre**.
  - **Terminer** — sauvegarde la sortie comme nouvelle Trace, ouvre le panneau de trace pour que vous puissiez consulter stats + profil d\'altitude immédiatement.
  - **Supprimer** — jette l\'enregistrement en cours sans sauvegarder.
- Le service GPS de premier plan démarre pour vous dès que vous commencez un enregistrement — vous n\'avez pas besoin d\'activer le suivi au préalable.
- **Écran éteint ?** L\'app relâche la cadence des fixes GPS pour économiser la batterie (≈10 s entre fixes écran éteint vs 2 s écran allumé). Aucune action requise — c\'est automatique.

### Si la localisation système est désactivée

Appuyer sur enregistrer alors que l\'interrupteur de localisation système Android est désactivé affiche un message rapide *« Localisation système désactivée — activez-la pour enregistrer »* avec un raccourci **Paramètres**. L\'enregistrement ne démarre pas.

### Si l\'app est tuée en pleine sortie

Si Android tue l\'app pendant un enregistrement actif (récupération mémoire, arrêt forcé, redémarrage), la ligne collectée jusqu\'à ce point est **préservée**. Rouvrez l\'app et le chip revient en affichant le temps écoulé en pause — tap sur **Reprendre** pour continuer, ou **Terminer** pour sauvegarder ce que vous avez.

### Type d\'activité

Chaque trace enregistrée démarre étiquetée **Randonnée**. Ouvrez l\'écran de détail de la trace (Traces → tap sur la ligne) et utilisez le menu déroulant **Activité** pour la passer en Marche / Course / Vélo / Tout-terrain / Parapente. Les traces importées n\'ont aucune étiquette d\'activité par défaut ; vous pouvez en assigner une de la même manière.

### Rogner un enregistrement

Du bruit de préchauffage GPS au début de votre trace ? Oublié de taper **Terminer** et la trace traîne à moitié jusqu\'à votre voiture ? Ouvrez l\'écran de détail et tap sur **Rogner la trace** :

- Une boîte de dialogue s\'ouvre avec une mini-carte en aperçu de la trace complète et son profil d\'altitude en dessous.
- Glissez les deux poignées sur le graphique d\'altitude pour définir le début et la fin de la plage à conserver. La mini-carte se met à jour en live — le segment conservé reste dans la couleur de la trace, les parties abandonnées passent en gris.
- L\'indicateur **Conservé** affiche la distance et le nombre de points résultants.
- Tap sur **Rogner** pour valider. Une confirmation précise combien de points tomberont de chaque extrémité. **Impossible à annuler** — gardez un export GPX si vous doutez.

Le rognage recalcule aussi la distance, la bounding box et le profil d\'altitude de la trace, pour que les stats en haut d\'écran reflètent immédiatement la trace raccourcie.

## Importer

### Depuis un fichier

Ouvrez **menu → Traces** → appuyez sur le **FAB dossier bleu** en bas à droite. Choisissez un ou plusieurs fichiers `.gpx` depuis le stockage (sélection multiple autorisée). L\'app revient à la carte et zoome automatiquement sur les traces importées.

### Depuis un partage (WhatsApp, e-mail, une autre app)

Quelqu\'un vous envoie un `.gpx` ? Appuyez dessus dans le chat / l\'e-mail / le gestionnaire de fichiers → le système propose de l\'ouvrir avec ApexGPS → l\'app l\'importe automatiquement et vous amène sur la carte.

### Ce qui est importé

- Les lignes de trace (avec altitude si le GPX en a).
- Les points inclus dans le GPX (chacun avec son nom, sa description, son symbole mappé sur le plus proche équivalent ApexGPS).

**Protection contre les doublons :** si vous réimportez le même GPX, les points déjà présents aux mêmes coordonnées ne sont pas ajoutés. Les lignes de trace SONT réimportées (même nom, vous pouvez supprimer manuellement).

## Afficher une trace sur la carte

Tap sur une ligne de trace sur la carte. Un panneau glisse depuis le bas avec :

- Nom + distance.
- **Profil d\'altitude** — un petit graphique. Glissez le doigt dessus pour scruber le long de la trace ; un viseur indique le point correspondant sur la carte.
- **Dénivelé +/-** totaux.
- Bouton **Modifier** → ouvre la fiche détail.
- Bouton **Partager** → exporte la trace en `.gpx` à envoyer à qui vous voulez.
- Bouton **Masquer** → réduit le panneau à une barre fine en bas (pour garder la sélection sans cacher la carte).
- **Fermer** (glisser vers le bas) → ferme le panneau.

## Liste des traces (menu → Traces)

Liste complète de toutes les traces importées. Compte dans le titre.

### Filtrer

Appuyez sur l\'**icône filtre**. Deux options :

- **Visibilité** — Toutes / Visibles uniquement / Masquées uniquement. Les traces que vous avez masquées via le bouton de visibilité restent dans la liste mais ne sont plus dessinées.
- **Couleur** — palette de 16 couleurs. Tap sur une couleur pour n\'afficher que les traces de cette couleur.

Filtre actif = icône bleue. Tap sur **Toutes** dans chaque section pour effacer.

### Trier

Appuyez sur l\'**icône tri** :

- **Plus récentes** — par date d\'import (par défaut).
- **Par nom** — alphabétique.
- **Plus proches** — point central le plus proche de votre position. Utilise la dernière position connue du téléphone, donc fonctionne même si le GPS d\'ApexGPS n\'a pas encore été activé cette session. Affiche « (pas de GPS) » si la permission est refusée ou sans fix en cache.
- **Par points** — traces avec le plus de points en premier (utile pour repérer les traces ultra-détaillées).

### Rechercher

Tapez dans le champ pour filtrer sur les traces dont le nom contient votre texte.

### Sélection multiple

Appui long sur une trace → mode sélection. Cochez celles que vous voulez, puis :

- **Changement de couleur groupé** (icône palette) — couleur unique pour la sélection.
- **Afficher / masquer groupé** (icônes œil) — visibilité rapide.
- **Suppression groupée** (corbeille rouge) — avec confirmation.
- **Tout sélectionner** — coche toutes les traces de la vue filtrée.

## Actions par trace

Tap sur une trace dans la liste → ouvre l\'écran **détail**.

- **Nom** — modifiable.
- **Couleur** — tap pour ouvrir le sélecteur.
- **Visibilité** — afficher / masquer sur la carte.
- **Profil d\'altitude** — même graphique que dans le panneau carte, mais en taille réelle.
- **Dénivelé +/-** totaux.
- **Nombre de points** — combien de points GPS composent la trace.
- **Afficher sur la carte** — ferme le détail et zoome sur la trace.
- **Optimiser** — simplifie en supprimant les points redondants. Utile pour les imports massifs. Non destructif au niveau du fichier source ; vous pouvez réimporter pour récupérer l\'original.
- **Partager en GPX** — équivalent du bouton de partage du panneau.
- **Supprimer** — avec confirmation.

## Optimisation en lot (bibliothèques volumineuses)

Si vous avez importé beaucoup de traces très denses, la carte peut sembler lente sur un vieux téléphone. **Paramètres → Données → Tout optimiser** lance la même simplification sur toutes les traces d\'un coup. L\'interface affiche combien seront touchées.

## Suppression

Unitaire : glissez / tap sur l\'icône corbeille dans la ligne, ou bouton Supprimer de l\'écran détail.

Groupée : mode sélection + suppression groupée.

Pas d\'annulation possible. Faites une [sauvegarde](backup.md) si vous hésitez.

---

**Voir aussi :** [Points →](waypoints.md) · [L\'écran carte →](map.md) · [Sauvegarde & restauration →](backup.md)
