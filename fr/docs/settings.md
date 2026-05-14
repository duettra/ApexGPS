# Paramètres

**Menu → Paramètres** est organisé en cinq sous-écrans : Apparence, Stockage, Données, Clés API, Avancé. Chacun a un bouton ⓘ à côté des titres de section expliquant la fonction.

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
Crée un ZIP avec traces, points, régions enregistrées et paramètres. Des cases permettent d\'exclure des catégories. Les régions hors ligne enregistrées disposent d\'un **mode à trois choix** : **Ne pas inclure** (les ignorer) / **Recette** (petit — juste les instructions pour retélécharger chaque région, fonctionne entre Android et iOS) / **Tuiles complètes** (l\'ancien comportement — intègre les bundles de tuiles bruts, volumineux mais restaurable hors ligne, Android uniquement). Voir [Sauvegarde & restauration](backup.md).

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

**Sans clé, le style Outdoors est masqué** du sélecteur de style de carte (et du sélecteur de téléchargement de région hors ligne) pour que vous ne le choisissiez pas accidentellement et ne voyiez les tuiles de repli OpenTopoMap. Collez une clé → l\'entrée réapparaît dans les deux menus. Les cinq autres styles fonctionnent sans clé.

## Avancé

### Économie de batterie à grande vitesse
Quand vous vous déplacez plus vite que **36 km/h** (≈22 mph) — voiture, train, vélo électrique rapide — l\'app réduit sa cadence d\'échantillonnage GPS à un fix toutes les **10 secondes** au lieu d\'un par seconde. Les traces de forme routière s\'enregistrent toujours proprement ; la précision au niveau de la voie est réduite en voiture. Réduit d\'environ la moitié la consommation GPS sur le tronçon autoroutier d\'un road trip sans perte visible de la géométrie d\'itinéraire. Désactivez si vous avez besoin d\'un échantillonnage complet à grande vitesse (par ex. télémétrie rallye).

## À propos

**Paramètres → À propos** affiche la version, les attributions et l\'e-mail de contact — plus le **Guide utilisateur** : entrées cliquables pour chaque chapitre de cette documentation, embarquée avec l\'app pour une consultation hors ligne. Tap sur un chapitre → un lecteur s\'ouvre et rend le chapitre dans l\'app. Les liens croisés entre pages sont respectés ; la flèche de retour revient à la liste. Un lien **« Lire en ligne »** en bas ouvre la même doc sur [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) dans le navigateur. Pour aide : [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

Sous Guide utilisateur, une ligne **Politique de confidentialité** ouvre le même lecteur intégré sur le chapitre confidentialité — sans connexion nécessaire pour lire quelles données l\'app collecte (aucune au-delà de ce qui est sur votre téléphone) et comment elles sont utilisées. Le même contenu est miroir sur [apexgps.duttra.de/privacy.html](https://apexgps.duttra.de/privacy.html) pour quiconque veut le lire avant d\'installer.

---

**Voir aussi :** [FAQ →](faq.md) · [Sauvegarde & restauration →](backup.md)
