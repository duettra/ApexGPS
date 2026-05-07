# Paramètres

**Menu → Paramètres** est organisé en quatre sous-écrans : Apparence, Stockage, Données, Clés API. Chacun a un bouton ⓘ à côté des titres de section expliquant la fonction.

## Apparence

### Thème
- **Système** (par défaut) — suit le paramètre clair/sombre du téléphone.
- **Clair** — toujours clair.
- **Sombre** — toujours sombre.

### Carte par défaut
Le style utilisé au lancement. Six options ; voir [L\'écran carte → Couches](map.md) pour les détails. Vous pouvez toujours changer en cours de session via le bouton couches.

### Largeur de trace
Slider, 4–24 dp. Des lignes plus épaisses sont plus visibles quand plusieurs traces se chevauchent ; plus fines c\'est plus net à zoom élevé. Défaut ~6 dp.

### Taille des points
Petit / Normal / Grand / XL. Multiplicateur sur la taille adaptative au zoom — les marqueurs rétrécissent à petit zoom et grossissent à fort zoom pour rester lisibles ; ce réglage décale toute la plage. Défaut Normal (1,0×).

### Rotation verrouillée au démarrage
- **Désactivé** (par défaut) — les gestes deux doigts marchent dès l\'ouverture.
- **Activé** — rotation verrouillée au lancement ; appui long sur la boussole pour débloquer. Utile si vous tournez souvent la carte par erreur.

## Stockage

### Usage du cache
Taille totale du cache de navigation + détail par source.

### Taille du cache des tuiles carto
Choisissez l\'espace disque alloué au cache automatique des tuiles : **250 Mo**, **500 Mo** (défaut), **1 Go**, **2 Go**. La nouvelle limite s\'applique immédiatement au prochain téléchargement de tuile — pas besoin de redémarrer. Les régions hors-ligne enregistrées sont stockées à part et ne comptent pas dans cette limite ; changer la taille du cache ne supprime jamais une région que vous avez délibérément téléchargée.

### Vider le cache
- **Tout vider** — supprime les tuiles cachées pour chaque style. NE supprime PAS les régions enregistrées.
- **Vider [source]** — par style. Utile quand un style prend beaucoup de place (imagerie satellite > carte courbes).

Le cache de navigation se reconstitue en regardant des zones avec signal. Vider n\'affecte pas les données explicitement enregistrées via le hub Cartes.

## Données

### Sauvegarde
Crée un ZIP avec traces, points, régions enregistrées et paramètres. Cases pour exclure des catégories (cartes souvent décochées pour des sauvegardes rapides « juste mes traces »). Voir [Sauvegarde & restauration](backup.md).

### Restauration
Ouvre un `apexgps-backup-*.zip`. Choisissez **Fusionner** (ajouter à l\'existant) ou **Remplacer** (écraser). Voir [Sauvegarde → Fusionner vs Remplacer](backup.md#fusionner-vs-remplacer).

### Optimiser toutes les traces
Lance Douglas-Peucker sur toutes les traces. Réduit les points sans altérer visiblement la forme. Utile si vous avez beaucoup de GPX très détaillés et si la carte rame sur un vieux téléphone. Le nombre total touché est indiqué.

Les traces individuelles peuvent aussi être optimisées depuis leur écran détail.

### Charger les données d\'exemple
Un enregistrement réel de la **traversée du Watzmann** (Berchtesgaden, Allemagne) : Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, boucle de ~22,6 km / +2250 m / environ 10–12 h de marche. Trois points de repère aux coordonnées réelles : départ Wimbachbrücke (628 m), refuge DAV Watzmannhaus (1930 m), Watzmann-Mittelspitze (le *Hauptgipfel*, 2713 m). Importée automatiquement à la première ouverture d\'une installation neuve ; ce bouton la réimporte à la demande si vous l\'avez supprimée et la voulez à nouveau. Après import, ce sont des traces/points normaux — supprimables à tout moment.

## Clés API

### Thunderforest
Requis pour le style **Outdoors (Thunderforest)**. Plan « Hobby » gratuit : 150 000 requêtes/mois, sans carte. Inscrivez-vous sur [thunderforest.com](https://www.thunderforest.com/), copiez votre clé, collez ici → **Enregistrer**.

Sans clé, Outdoors affiche un placeholder ; les cinq autres styles fonctionnent sans clé.

## À propos

**Paramètres → À propos** affiche la version, les attributions et l\'e-mail de contact — plus le **Guide utilisateur** : entrées cliquables pour chaque chapitre de cette documentation, embarquée avec l\'app pour une consultation hors ligne. Tap sur un chapitre → un lecteur s\'ouvre et rend le chapitre dans l\'app. Les liens croisés entre pages sont respectés ; la flèche de retour revient à la liste. Un lien **« Lire en ligne »** en bas ouvre la même doc sur [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) dans le navigateur. Pour aide : [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

---

**Voir aussi :** [FAQ →](faq.md) · [Sauvegarde & restauration →](backup.md)
