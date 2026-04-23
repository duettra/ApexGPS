# Traces

Une **trace** est un chemin enregistré — une série de points GPS reliés comme une ligne sur la carte. Les traces viennent de l\'import de fichiers GPX (depuis GaiaGPS, Strava, Garmin Connect, wikiloc.com ou tout autre export GPX).

**Remarque :** ApexGPS n\'enregistre pas de nouvelles traces dans cette version. L\'enregistrement live est prévu pour une future version.

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
