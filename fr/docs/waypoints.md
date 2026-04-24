# Points

Un **point** est un endroit nommé sur la carte — départ de sentier, sommet, joli spot photo, cabane, emplacement du véhicule. Chacun a un nom, une couleur et un des 32 symboles.

## Ajouter un point

### À un endroit précis (appui long sur la carte)

Appui long sur la carte à l\'endroit voulu. Un sheet s\'ouvre avec :

- **Nom** — optionnel. « Point » par défaut si vide.
- **Notes** — description optionnelle.
- **Latitude / Longitude** — pré-remplies depuis le point tapé ; **modifiables** si besoin.
- **Altitude (m)** — optionnelle. Laissez vide si inconnue ; remplissez quand vous voulez que le point porte une altitude précise (ex. une hauteur de sommet que vous avez cherchée).
- **Symbole** — choix parmi 32 icônes.
- **Couleur** — palette de 16 couleurs.
- **Enregistrer** / **Annuler**.

### En saisissant des coordonnées

Ouvrez **menu → Points** → FAB **+** bleu en bas à droite. Même sheet, mais les champs Lat / Lon sont vides. Tapez des coordonnées (ou collez une chaîne `lat, lon` dans le champ Latitude — l\'app sépare automatiquement).

### En important un GPX

Ouvrez **menu → Points** → FAB **dossier bleu** en bas à droite. Choisissez un ou plusieurs `.gpx`. Tous les points dans les fichiers sont importés. Les doublons (même nom, à moins de ~11 m) sont ignorés automatiquement.

### À votre position actuelle

Activez le GPS (tap sur le viseur si le triangle n\'est pas affiché), appui long sur le triangle lui-même (ou très près), et la boîte s\'ouvre pré-positionnée sur votre fix.

### Depuis un GPX reçu (partage / ouvrir avec)

Les GPX ouverts depuis une autre app (pièce jointe WhatsApp, Gmail, gestionnaire de fichiers) importent aussi leurs points automatiquement. Si un point n\'a pas de nom (certains exports mettent les coordonnées dans le champ nom), ApexGPS le détecte et affiche « Point » à la place.

## Afficher un point

Tap sur un point. Un panneau monte depuis le bas avec :

- Icône + nom.
- Coordonnées (lat/lon à 6 décimales).
- Altitude (si définie).
- Distance depuis votre position GPS (en bleu — live).
- Description (si saisie).
- Bouton **Naviguer** (bonhomme qui marche, bleu) — démarre la navigation à vol d\'oiseau vers ce point. Voir plus bas.
- Bouton **Partager** — envoie le point via WhatsApp / SMS / e-mail. Le destinataire reçoit un texte avec nom, coords, altitude et deux liens (ApexGPS App Link + Google Maps). S\'il a ApexGPS, tap sur le lien ouvre l\'app directement avec une cible rouge à l\'endroit — il peut l\'enregistrer comme son propre point.
- Bouton **Modifier**.

Fermer en glissant vers le bas.

## Naviguer vers un point

Tap sur l\'icône **Naviguer** (bonhomme marche, teintée primaire) dans le panneau. Le panneau se ferme et :

- Une **ligne bleu clair pointillée** se dessine de votre GPS vers le point.
- La barre du bas devient : *« Navigation · 0,42 km · 045° NE · [Arrêter] »* — distance live (bleu quand auto), cap en degrés + cardinal (N, NE, E, SE, S, SO, O, NO).
- Le champ **DIST** de la barre stats affiche aussi cette distance en bleu.
- Arrêt automatique à **20 mètres** du point (message « Arrivé »).
- **Arrêter** met fin à tout moment. Le point reste — tap pour réouvrir le panneau.

C\'est le même mode go-to que pour les positions partagées. Cap à vol d\'oiseau, pas de guidage virage-par-virage — en hors piste c\'est généralement ce qu\'on veut.

Tap à nouveau sur le point pendant la navigation pour réouvrir le panneau (la navigation continue en arrière-plan).

## Modifier un point

Tap sur le point → **Modifier** dans le panneau, ou ouvrez **menu → Points** et tap sur une ligne.

Même sheet qu\'à l\'ajout. Nom, Notes, **Latitude**, **Longitude**, Symbole, Couleur sont modifiables. À l\'enregistrement, l\'app valide les coordonnées (lat ∈ [−90, 90], lon ∈ [−180, 180], doivent être des nombres) et affiche une erreur rouge si hors plage.

## Déplacer un point

**Appui long + glisser** sur le point. Glissez-le à la nouvelle position. Au relâchement, une barre apparaît en bas :

- **Déplacer** — valide la nouvelle position.
- **Annuler** — le remet où il était.

Rien n\'est enregistré tant que vous n\'appuyez pas sur Déplacer. Utile si le glisser était accidentel.

## Les 32 symboles

Groupés par usage pour faciliter le choix :

| Groupe | Symboles |
|---|---|
| **Navigation / générique** | Drapeau · Lieu · Étoile · Favori |
| **Extérieur / randonnée** | Sommet · Col · Point de vue · Photo · Forêt · Source · Cascade · Eau potable · Camp · Abri · Pique-nique · Panneau · Ruines |
| **Informatif** | Info · Avertissement |
| **Services** | Parking · Carburant · Restaurant · Hôtel · Hôpital · Toilettes |
| **Transport** | Voiture · Vélo · Marche · Train · Bateau · Avion · Gaz |

Tous les 32 sont sélectionnables à l\'ajout ou modification. Le symbole est stocké avec le point et survit à l\'export → réimport.

## Liste des points (menu → Points)

Tous les points, compte dans le titre.

### Filtrer

**Icône filtre** → deux sections :

- **Couleur** — tap sur une couleur pour ne voir que celle-ci. **Toutes** pour effacer.
- **Symbole** — liste scrollable des 32 symboles. Tap pour filtrer sur ce symbole.

Filtres actifs = icône bleue.

### Trier

**Icône tri** :

- **Plus récents** — par date d\'import / création (par défaut).
- **Par nom** — alphabétique.
- **Plus proches** — le plus proche de votre GPS. « (pas de GPS) » si le téléphone n\'a pas de fix en cache.

### Rechercher

Tapez dans le champ pour filtrer les points dont le nom OU la description contient votre texte.

### Sélection multiple

Appui long dans la liste → mode sélection. Cochez plusieurs, puis suppression groupée. Pas de changement groupé de couleur/symbole pour les points (pour l\'instant) — utilisez Modifier par point.

### Supprimer les doublons

Si vous avez réimporté plusieurs fois le même GPX, vous pouvez avoir des doublons empilés (même nom aux mêmes coords). Tap sur **⋮** → **Supprimer les doublons**. Conserve le plus ancien et supprime le reste ; indique combien ont été retirés.

## Suppression

Unitaire : glissez / corbeille sur une ligne, ou bouton Supprimer dans la boîte de modification.

Groupée : mode sélection + suppression groupée.

Pas d\'annulation. Faites une [sauvegarde](backup.md) si vous hésitez.

## Afficher un point sur la carte

Depuis la liste, tap sur un point → l\'app revient à la carte et fait un pan vers le point. Le suivi est pausé pour ne pas être écrasé par le prochain fix GPS.

---

**Voir aussi :** [Traces →](tracks.md) · [Sauvegarde & restauration →](backup.md) · [L\'écran carte →](map.md)
