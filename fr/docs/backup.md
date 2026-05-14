# Sauvegarde & restauration

ApexGPS stocke tout **en local sur votre téléphone**. Aucune synchro cloud. En cas de réinitialisation, changement de téléphone ou désinstallation, **vos traces, points et régions hors ligne sont perdus** sauf si vous avez fait une sauvegarde.

La sauvegarde est manuelle mais simple. Faites-en une régulièrement si vous avez des données importantes.

## Ce qu\'une sauvegarde contient

- **Toutes les traces** (données GPX, nom, couleur, visibilité, étiquette d\'activité).
- **Tous les points** (nom, description, coords, altitude, couleur, symbole).
- **Toutes les régions de carte hors ligne enregistrées** — voir [Recette vs tuiles complètes](#recette-vs-tuiles-complètes) ci-dessous pour les deux façons de les sauvegarder.
- **Tous les paramètres** (thème, source par défaut, largeur de trace, taille des points, verrou rotation, économie de batterie, etc.).

Ce qu\'une sauvegarde **ne contient pas** :

- Le **cache de navigation** (tuiles auto-cachées lors de l\'usage général). Pas sauvegardé car facilement régénérable et potentiellement énorme.
- La **clé API Thunderforest** est sauvegardée avec les paramètres, donc pas besoin de la retaper.

## Créer une sauvegarde

1. **Menu → Paramètres → Données → Sauvegarder**.
2. Choisissez ce que vous voulez inclure — des cases pour traces / points / paramètres, plus un **sélecteur à trois choix pour les régions de carte hors ligne** (voir ci-dessous).
3. Appuyez **Créer la sauvegarde**.
4. Le ZIP est produit dans le stockage privé. Un dialogue de partage s\'ouvre — choisissez où :
   - **Google Drive / Dropbox / OneDrive** — garde en cloud.
   - **S\'envoyer à soi-même** par e-mail / chat.
   - **Enregistrer dans Téléchargements** via gestionnaire de fichiers.

Le ZIP s\'appelle par ex. `apexgps-backup-2026-05-14.zip`. La date est dans le nom.

### Recette vs tuiles complètes

Pour les régions de carte hors ligne enregistrées, vous choisissez **l\'un des trois modes** :

| Mode | Taille | Comportement | Multiplateforme ? |
|---|---|---|---|
| **Ne pas inclure** | minimale | Les lignes de régions ne sont pas sauvegardées du tout. | s.o. |
| **Recette** | ~80 Ko au total | Chaque région est sauvegardée comme une courte « fiche d\'instructions » — nom, cadre englobant, plage de zoom, source de tuiles. À la restauration, les régions apparaissent dans **Cartes → Cartes hors ligne enregistrées** marquées *« Pas encore téléchargée · X tuiles »*, avec un bouton **Télécharger** pour récupérer les tuiles réelles depuis le serveur de tuiles. | **Oui** — fonctionne entre Android et iOS. |
| **Tuiles complètes** | 50–500 Mo | Le bundle MBTiles réel de chaque région est intégré dans le ZIP. À la restauration, les régions sont immédiatement utilisables hors ligne ; pas besoin de retélécharger. | **Android uniquement.** iOS ne peut pas (encore) lire les bundles intégrés. |

**Choisissez Recette** pour les déplacements entre appareils (remplacement de téléphone, partage d\'une sauvegarde avec un ami sur iOS, ou sauvegarde « au cas où » à garder sur Drive pour toujours). Le retéléchargement est rapide en Wi-Fi et utilise vos tuiles les plus à jour.

**Choisissez Tuiles complètes** si vous voulez spécifiquement une sauvegarde restaurable hors ligne en une étape sur Android uniquement — utile avant un voyage où vous pourriez effacer votre téléphone et ne pas avoir de Wi-Fi à destination.

**Créer une sauvegarde Tuiles complètes peut prendre une à deux minutes** et produire un ZIP volumineux. L\'UI affiche la progression.

## Restaurer une sauvegarde

### La voie facile

Tap sur un fichier `apexgps-backup-*.zip` dans n\'importe quel gestionnaire / Google Drive / pièce jointe Gmail. Android propose les apps compatibles ; choisissez ApexGPS. L\'app s\'ouvre directement sur Paramètres → Données avec le dialogue de restauration.

### Via les paramètres

1. **Menu → Paramètres → Données → Restaurer**.
2. Choisissez le ZIP depuis le picker.
3. Choisissez un mode (voir ci-dessous).
4. Confirmez.

### Fusionner vs Remplacer

Les deux modes parcourent le ZIP catégorie par catégorie.

| Mode | Effet |
|---|---|
| **Fusionner** | Les nouveaux éléments sont AJOUTÉS à l\'existant. Les traces de même nom ne sont pas réunies — vous pouvez avoir des doublons ; utilisez **Paramètres → Données → Tout optimiser** ou suppression par trace pour nettoyer. |
| **Remplacer** | Chaque catégorie de la sauvegarde REMPLACE ce que vous avez. Si la sauvegarde contient des traces, toutes les vôtres sont d\'abord supprimées. Les catégories décochées à la création ne sont PAS touchées à la restauration. |

**Règle :**

- Nouveau téléphone → **Remplacer** (vous voulez l\'état exact de l\'ancien).
- Récupérer les points d\'un ami depuis sa sauvegarde → **Fusionner** (garde vos données, ajoute les siennes).

La restauration est en streaming — rapide même pour un ZIP de plusieurs centaines de Mo. En cas d\'échec à mi-chemin, certaines catégories peuvent avoir été appliquées ; relancez par sécurité.

### Restauration en mode recette — retélécharger les régions

Si la sauvegarde a utilisé le mode **Recette** pour les cartes hors ligne, la restauration est instantanée mais vous verrez les régions dans **Cartes → Cartes hors ligne enregistrées** marquées *« Pas encore téléchargée · X tuiles »* avec un bouton **Télécharger**. Appuyez pour récupérer les tuiles depuis le serveur de tuiles. Si la région utilise des tuiles Thunderforest et que vous n\'avez pas encore collé votre clé API, l\'app affiche un toast unique vous demandant de l\'ajouter d\'abord sous **Paramètres → Clés API** ; une fois la clé en place, appuyez à nouveau sur Télécharger.

### Restauration entre versions de l\'app

Une sauvegarde v2 (créée sur cette version ou plus récente) refuse de s\'ouvrir sur les versions plus anciennes de l\'app et affiche *« Le format de sauvegarde v2 est plus récent que ce que cette app supporte. Veuillez mettre à jour ApexGPS. »* — mettez à jour d\'abord, puis restaurez. Les anciennes sauvegardes v1 se restaurent toujours sur l\'app actuelle sans étape supplémentaire.

## Migrer vers un nouveau téléphone

1. **Sur l\'ancien :** créez une sauvegarde tout cochée. Envoyez-vous par e-mail / stockez sur Drive.
2. **Sur le nouveau :** installez ApexGPS, ouvrez, accordez les permissions, connectez-vous à votre e-mail / Drive.
3. **Téléchargez le ZIP** sur le nouveau téléphone, tap dessus → restaurer avec **Remplacer**.

Terminé. Traces, points, cartes, paramètres sont tous là.

## Protection réinitialisation / désinstallation

L\'auto-sauvegarde d\'Android restaure *une partie* de vos paramètres (thème, source par défaut, clé API, largeur de trace, taille des points, verrou rotation) depuis Google Drive à la réinstallation. Cela N\'inclut PAS traces, points ou régions — uniquement des préférences légères.

**Le seul moyen fiable de préserver vos données de randonnée à travers une réinstallation est une sauvegarde ZIP.** Faites-en une avant tout changement de téléphone ou maj majeure de l\'OS.

---

**Voir aussi :** [Paramètres →](settings.md) · [Traces →](tracks.md) · [Points →](waypoints.md)
