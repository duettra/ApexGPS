# Sauvegarde & restauration

ApexGPS stocke tout **en local sur votre téléphone**. Aucune synchro cloud. En cas de réinitialisation, changement de téléphone ou désinstallation, **vos traces, points et régions hors ligne sont perdus** sauf si vous avez fait une sauvegarde.

La sauvegarde est manuelle mais simple. Faites-en une régulièrement si vous avez des données importantes.

## Ce qu\'une sauvegarde contient

- **Toutes les traces** (données GPX, nom, couleur, visibilité).
- **Tous les points** (nom, description, coords, altitude, couleur, symbole).
- **Toutes les régions de carte hors ligne enregistrées** (les bundles de tuiles — peuvent être gros).
- **Tous les paramètres** (thème, source par défaut, largeur de trace, taille des points, verrou rotation).

Ce qu\'une sauvegarde **ne contient pas** :

- Le **cache de navigation** (tuiles auto-cachées lors de l\'usage général). Pas sauvegardé car facilement régénérable et potentiellement énorme. Les régions enregistrées le sont ; le cache non.
- La **clé API Thunderforest** est sauvegardée avec les paramètres, donc pas besoin de la retaper.

## Créer une sauvegarde

1. **Menu → Paramètres → Données → Sauvegarder**.
2. Optionnel : décochez les catégories non voulues (les cartes enregistrées sont les plus grosses — laissez-les de côté si vous ne sauvegardez que traces/points).
3. Appuyez **Créer la sauvegarde**.
4. Le ZIP est produit dans le stockage privé. Un dialogue de partage s\'ouvre — choisissez où :
   - **Google Drive / Dropbox / OneDrive** — garde en cloud.
   - **S\'envoyer à soi-même** par e-mail / chat.
   - **Enregistrer dans Téléchargements** via gestionnaire de fichiers.

Le ZIP s\'appelle par ex. `apexgps-backup-2026-04-19.zip`. La date est dans le nom.

**Une sauvegarde avec régions hors ligne peut prendre une à deux minutes** et produire un ZIP volumineux (50-500 Mo selon le nombre de régions). L\'UI affiche la progression.

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
