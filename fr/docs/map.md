# L\'écran carte

Tout tourne autour de cette vue. Voici à quoi sert chaque contrôle.

## Gestes

| Geste | Effet |
|---|---|
| Glisser (un doigt) | Déplacer la carte. |
| Pincer | Zoomer / dézoomer. |
| Rotation à deux doigts | Tourner la carte. |
| Tap sur une trace | Ouvrir le panneau de trace (profil, scrubber). |
| Tap sur un point | Ouvrir le panneau de point (nom, description, modifier). |
| Tap sur le triangle bleu (votre position) | Ouvrir le panneau **Partager la position**. |
| Appui long sur la carte vide | Ajouter un point à cet endroit. |

## En haut à droite : la boussole

Une pastille ronde avec une aiguille rouge. Toujours visible. L\'aiguille indique toujours le nord vrai, quel que soit l\'orientation de la carte — elle sert aussi de repère permanent.

- **Tap** — oriente doucement la carte vers le nord.
- **Appui long** — bascule le verrou de rotation. Pastille **bleue** = rotation gelée ; les gestes deux doigts sont ignorés. Appui long à nouveau pour déverrouiller.

Option « verrouillage au lancement » dans **Paramètres → Apparence → Rotation verrouillée au démarrage** pour ceux qui ne veulent jamais tourner la carte.

## Colonne de droite : les boutons d\'action

De haut en bas :

### Mesurer la distance
**Icône règle**. Appuyez pour entrer en mode mesure ; tap sur la carte pour poser des épingles ; une ligne les relie et la barre stats en bas affiche la distance totale. Glissez la première épingle sur votre position GPS pour mesurer « depuis moi ». Appuyez de nouveau sur l\'icône pour sortir.

### Couches de carte
**Icône couches**. Six styles : OpenTopoMap (par défaut, randonnée), OSM Standard (vue générale épurée), ESRI Topo, ESRI relief ombré, Satellite, Outdoors (Thunderforest — nécessite une clé API gratuite depuis Paramètres → Clés API).

Le style choisi est conservé d\'une session à l\'autre.

### Suivre-moi (viseur)
Trois états — la couleur du bouton vous dit lequel :

| État | Couleur | Comportement |
|---|---|---|
| **Désactivé** | Gris | GPS coupé, aucun triangle sur la carte. |
| **Activé, verrouillé** | Bleu plein | GPS actif, triangle visible, la carte vous re-centre toutes les quelques secondes. |
| **Activé, déverrouillé** | Bleu pâle | GPS actif, triangle à jour, la carte reste où vous avez glissé. |

- Tap depuis **Désactivé** → active le GPS + verrouille la caméra sur vous.
- Tap depuis **Verrouillé** → coupe le GPS.
- **Glisser la carte** en mode verrouillé → bascule automatiquement en déverrouillé. Le triangle continue ; la carte ne bouge plus.
- Tap depuis **Déverrouillé** → re-centre + re-verrouille.
- **Appui long** sur n\'importe quel état actif → coupe le GPS instantanément (saute l\'animation de re-centrage).

### Où est passé le bouton d\'import (+) ?

Depuis la **v1.25.2**, la carte n\'a plus de FAB d\'import dédié — l\'import GPX se fait désormais depuis les écrans liste Traces et Points. Voir [Traces](tracks.md#importer) ou [Points](waypoints.md#ajouter-un-point).

## En haut à gauche

- **☰ menu** — tiroir de navigation (Traces, Points, Cartes, Paramètres).
- **Bouton panique** — pastille rouge ⚠, visible seulement si activé dans **Paramètres → Apparence → Bouton panique**. Tap ouvre le panneau de partage de position (lance le GPS automatiquement s\'il était coupé).

## Barre stats en bas

Trois valeurs :

- **VIT** — km/h actuels du GPS.
- **ALT** — altitude actuelle en mètres.
- **DIST** — contextuel :
  - En **mode mesure** : longueur totale de la ligne.
  - Pendant une **navigation vers une position partagée** : distance live au point cible (en bleu quand auto-mise à jour).
  - Sinon : vide.

## Indicateur hors ligne

Si votre appareil n\'a pas de réseau, une petite pastille rouge **« Hors ligne »** apparaît en haut. Les tuiles en cache s\'affichent ; les tuiles jamais vues ne se chargent pas tant que vous n\'êtes pas en ligne. Voir [Cartes hors ligne](offline-maps.md) pour pré-télécharger des régions.

---

**Voir aussi :** [Traces →](tracks.md) · [Points →](waypoints.md) · [Partager votre position →](share-and-navigate.md)
