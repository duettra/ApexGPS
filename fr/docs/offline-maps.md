# Cartes hors ligne

ApexGPS fonctionne sans signal si les tuiles de la zone sont déjà sur votre téléphone. Deux moyens : cache automatique et pré-téléchargement manuel.

## Cache automatique

Tout ce que vous avez regardé avec signal est sauvegardé dans le cache du téléphone. Revisiter la même zone hors ligne → les tuiles se chargent instantanément depuis le cache.

Le cache est **par source de tuiles** — OpenTopoMap et Satellite sont séparés. Regarder une zone en OpenTopoMap n\'aide pas si vous passez à Satellite hors ligne.

La taille du cache s\'affiche dans **Paramètres → Stockage** avec détail par source.

## Pré-téléchargement manuel (recommandé pour les sorties)

Avant d\'aller quelque part sans signal, téléchargez délibérément la région :

### Choisir la zone

1. Déplacez/zoomez la carte pour cadrer la zone voulue.
2. **Menu → Cartes** → appuyez sur **Télécharger une zone**.
3. Une petite carte d\'aperçu montre la zone actuelle. Réajustez si besoin.

### Définir la plage de zoom

Un **slider** définit les niveaux à mettre en cache. Plus de zoom = plus de détail mais exponentiellement plus de tuiles.

- **Week-end de randonnée** : 10–16 suffit généralement.
- **Expédition / une semaine** : 10–17 ou 10–18 pour un maximum.
- Zoom 19+ rarement utile en plein air — beaucoup de tuiles, peu d\'info supplémentaire.

L\'UI affiche le **nombre estimé de tuiles** et la **taille Mo** pendant que vous déplacez le slider. À comparer avec votre espace libre.

### Télécharger

Appuyez **Télécharger**. Une notification en avant-plan apparaît ; vous pouvez quitter l\'app, verrouiller le téléphone — le téléchargement continue. Progrès mis à jour en direct dans la notification et dans le hub Cartes.

Pour annuler pendant le téléchargement : hub Cartes → la carte de téléchargement a un bouton **Annuler**. (Retour arrière NE l\'annule pas — c\'est voulu pour que vous puissiez parcourir les traces pendant le téléchargement.)

### Source de tuiles active uniquement

Le téléchargement utilise la source active au démarrage. Pour cacher un autre style, changez d\'abord la source (FAB couches), puis lancez.

## Régions enregistrées (menu → Cartes → Cartes hors ligne enregistrées)

Chaque téléchargement terminé apparaît ici. Tap sur une région pour ouvrir sa fiche :

- **Nom** — modifiable. Défaut basé sur pays/région géocodée depuis le cadre englobant.
- **Source**, **plage de zoom**, **nombre de tuiles**, **taille disque**.
- **Afficher sur la carte** — ferme la fiche et zoome sur le cadre.
- **Supprimer** — libère le stockage. Avec confirmation.

Supprimer une région enregistrée supprime son bundle mais PAS le cache général. La zone peut rester cachée via navigation antérieure.

## Gestion du cache (menu → Paramètres → Stockage)

- **Taille totale du cache** toutes sources confondues.
- **Détail par source** — Mo occupés par chaque style.
- **Tout effacer** — vide le cache de navigation pour chaque source. NE supprime PAS vos régions enregistrées (fichiers séparés).
- **Effacer [source]** — cache d\'un seul style.

Les régions hors ligne se gèrent dans le hub Cartes, pas ici.

## Ce qui consomme du réseau en balade

Même avec tout en cache, quelques éléments peuvent encore tenter Internet :

- **Changement de style** si le nouveau style n\'est pas caché pour la zone — tuiles vides.
- **Thunderforest (Outdoors)** — tuiles via HTTPS avec votre clé API.
- Rien d\'autre. Traces, points et navigation sont 100 % locaux.

Sans signal, la pastille **Hors ligne** apparaît en haut. C\'est le signal au niveau appareil, pas un choix d\'app.

## Astuces

- **Pré-téléchargez toujours avant une sortie.** Ne comptez pas sur l\'auto-cache — il ne couvre que ce que vous avez regardé.
- **Deux styles** peut aider : OpenTopoMap pour les courbes + sentiers, Satellite pour le visuel. Téléchargez les deux pour les zones critiques.
- **Plus de zoom = plus de stockage, rendement décroissant.** Au-delà de 17 le détail supplémentaire aide rarement ; c\'est surtout forme des bâtiments et étiquettes de rue.
- **Vérifiez l\'espace libre avant un gros téléchargement.** Une grande région en zoom 18 peut dépasser 500 Mo.

---

**Voir aussi :** [L\'écran carte →](map.md) · [Paramètres →](settings.md) · [Sauvegarde & restauration →](backup.md)
