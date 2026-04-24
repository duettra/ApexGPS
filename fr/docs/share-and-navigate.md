# Partager votre position & naviguer vers un point

## Partager votre position actuelle

### La version rapide

1. Vérifiez que le GPS est activé (bouton viseur → triangle bleu).
2. Appuyez sur le **triangle bleu** sur la carte.
3. Un panneau monte avec vos infos. Appuyez **Partager**.
4. Choisissez WhatsApp, SMS, e-mail. Envoyez.

### Ce que le panneau affiche

```
Altitude 145 m · ±5 m · 19:42
Batterie 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=25.165183&lon=55.409717
Google Maps: https://maps.google.com/?q=25.165183,55.409717
```

- **Altitude** — mètres au-dessus du niveau de la mer selon le GPS (absente si indéterminable).
- **±précision** — confiance du GPS en mètres. Arbres, bâtiments, canyons l\'augmentent.
- **Heure** — quand ce fix a été pris.
- **Batterie** — pour que le destinataire sache si vous êtes à plat.
- Deux **URL** — la première ouvre ApexGPS (si installé), la seconde n\'importe quelle app de cartes.

### Ce que voit le destinataire

Le message ajoute un petit bonjour avant les détails :

```
Bonjour, voici ma position actuelle.

Altitude 145 m · ±5 m · 19:42
Batterie 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=...
Google Maps: https://maps.google.com/?q=...
```

Dans WhatsApp et apps similaires, les deux URL sont cliquables. En SMS c\'est du texte copiable.

### S\'il n\'y a pas encore de fix GPS

Le panneau s\'ouvre mais affiche « Acquisition GPS… » et le bouton Partager est désactivé. Dès que le premier fix arrive, le panneau se met à jour et Partager s\'active — pas besoin de fermer et rouvrir.

## Recevoir une position partagée

Quelqu\'un vous envoie un lien `apexgps.duttra.de/loc?...`.

### Si vous avez ApexGPS

Tap sur le lien → **ApexGPS s\'ouvre directement**, la carte se centre sur la position et une cible rouge apparaît. Une barre monte avec trois boutons :

- **Naviguer** — démarre le mode go-to (voir plus bas).
- **Enregistrer** — ajoute l\'endroit comme point (nom, couleur, symbole).
- **Masquer** — retire le marqueur, sans rien faire.

### Si vous n\'avez pas ApexGPS

Tap sur le lien → une page web simple avec un aperçu carte plus :

- Bouton **Ouvrir dans ApexGPS** (Android uniquement ; propose d\'installer si absent).
- Bouton **Ouvrir dans Google Maps**.

## Naviguer vers une position partagée

Après avoir tapé un lien partagé, appuyez **Naviguer** dans la barre du bas :

- Une **ligne bleu clair pointillée** se dessine de votre position vers la cible.
- La barre devient : *« Navigation · 0,42 km · 045° NE · [Arrêter] »*.
  - Distance mise à jour à chaque fix, en **bleu** = auto.
  - **Cap** en degrés + une des huit cardinales (N, NE, E, SE, S, SO, O, NO) — marchez dans cette direction.
  - La même distance apparaît aussi dans **DIST** de la barre stats, en bleu, pendant la navigation.
- À **20 mètres** du point, arrêt automatique avec « Arrivé ».
- **Arrêter** met fin manuellement. La cible reste ; vous pouvez **Naviguer** à nouveau ou **Enregistrer** comme point.

Cap à vol d\'oiseau — pas virage-par-virage. En randonnée hors piste c\'est ce qu\'il faut ; en ville, ouvrez plutôt le lien Google Maps pour un itinéraire routier.

### Fonctionne aussi pour vos propres points

Le même mode go-to démarre aussi depuis n\'importe quel point sur la carte. Tap sur un point → icône **Naviguer** (bonhomme marche) → le panneau se ferme et la barre de navigation prend le relais. Détails dans [Points → Naviguer vers un point](waypoints.md#naviguer-vers-un-point).

## La boussole de navigation (plein écran)

En navigation, une petite **icône boussole** 🧭 apparaît sur la barre de nav, à gauche d\'Arrêter. Tap pour ouvrir une vue plein écran. Glissez vers le bas pour minimiser.

### Mise en page

Ligne du haut : **Distance** (bleu) · **ETA** · **Vitesse** · **Altitude**.

Cadran analogique central :
- Couronne extérieure avec graduations tous les 15° (majeures tous les 30°).
- Libellés **N / E / S / O** sur la carte.
- Petit **triangle rouge** marquant le nord vrai.
- **Aiguille bleue** (triangle) pointant vers la cible dans le monde réel.
- **Pastille centrale** affichant le cap actuel du téléphone (`245°`), ou la lettre **S** avec la légende *« Cap simulé »* quand le capteur boussole est peu fiable (métal, aimant, calibration en forme de 8 requise).

Ligne du bas : **Lat · Lon · Cap° + cardinal · ±Précision**.

En bas : **Arrêter la navigation** (toute la largeur, termine la nav).

### Utilisation

Le cadran **tourne avec l\'orientation du téléphone**, donc le triangle rouge pointe toujours vers le nord réel. Pointez le haut du téléphone vers l\'aiguille bleue pour faire face au point.

Capteur fiable = pastille en degrés ; sinon « S » stylisé + *Cap simulé* — un rappel que la direction peut dériver.

### Ce qui se passe pour la barre stats

Quand la boussole est ouverte, la barre stats habituelle en bas de la carte est **masquée** — la boussole affiche déjà ces valeurs en plus grand, la duplication serait bruyante. La barre réapparaît dès que vous glissez la boussole vers le bas.

### Ce que la barre de nav affiche quand la boussole est fermée

Boussole minimisée, la barre de nav affiche :

> *Navigation · **045° NE** · ETA 12 min · 🧭 · Arrêter*

Le cap et la cardinale sont en **bleu** parce qu\'ils se mettent à jour à chaque fix. ETA est une estimation basée sur votre vitesse actuelle — `--` à l\'arrêt. La distance n\'est plus dans la barre ; elle est dans **DIST** de la barre stats (également bleu en nav).

---

**Voir aussi :** [L\'écran carte →](map.md) · [Paramètres →](settings.md) · [FAQ →](faq.md)
