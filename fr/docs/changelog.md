# Nouveautés

Changements visibles par l\'utilisateur, plus récents en premier. Pour les refactos internes / sauts de version pur, voir le repo privé.

---

## 1.40.2 — 6 juin 2026 — Correction de l’altitude enregistrée

- Correction d’un bug sur les téléphones sans baromètre où les vibrations (p. ex. en VTT) pouvaient entraîner l’altitude enregistrée vers des valeurs impossibles — l’altitude reste désormais ancrée aux vraies mesures GPS.
- Les altitudes physiquement impossibles (sous −500 m ou au-dessus de 9000 m) ne peuvent plus être enregistrées, quelle que soit leur source.

---

## 1.40.1 — 5 juin 2026 — Corrections de la carte de statistiques d\'enregistrement

- La carte de statistiques d\'enregistrement en direct garde maintenant son horloge à jour même quand un enregistrement est en pause.
- Performances plus fluides sur les longs enregistrements — les statistiques en direct ne se recalculent désormais que lorsque la carte est ouverte.

---

## 1.40.0 — 4 juin 2026 — Carte de statistiques d\'enregistrement en direct

- **Tapez sur le chrono d\'enregistrement pour ouvrir une carte de statistiques en direct** — durée, distance, altitude actuelle (avec sa source), montée totale et horloge, le tout se mettant à jour au fil de votre progression.
- Pause, Terminer et Supprimer sont désormais des boutons à icône clairs, chacun avec une confirmation.
- Le menu d\'enregistrement et les autres menus de la carte se ressemblent maintenant : arrondis, translucides, et ils suivent votre réglage Taille du texte dans l\'app.

---

## 1.39.1 — 4 juin 2026 — Corrections du retour à la carte et du Guide d\'utilisation

- Correction d\'une **carte noire** occasionnelle au retour à la carte depuis un menu — elle se redessine maintenant immédiatement au lieu de rester vide jusqu\'à ce que vous panniez.
- Le texte du **Guide d\'utilisation** hors ligne s\'adapte désormais au réglage **Taille du texte** de l\'app, comme le reste de l\'application.

---

## 1.38.0 — 3 juin 2026 — Tailles de texte et de contrôles ajustables

- Nouveau curseur **Taille du texte** dans Paramètres → Apparence (50–150 %) qui met à l\'échelle tout le texte de l\'app par-dessus votre réglage de police Android.
- Nouveau curseur **Taille des contrôles de carte** — redimensionnez les boutons sur la carte, la boussole et la pastille d\'enregistrement ; rétrécissez-les pour récupérer de la surface de carte sur un petit téléphone.
- Le réglage de la taille des waypoints est lui aussi désormais un curseur fluide.

---

## 1.37.15 — 2 juin 2026 — L\'altitude des waypoints fonctionne hors ligne

- Ajouter un waypoint sur la carte **pré-remplit maintenant son altitude depuis votre altitude GPS actuelle**, donc cela fonctionne en mode avion ou sans signal. Vous pouvez toujours la modifier, ou récupérer la valeur précise plus tard une fois en ligne.

---

## 1.37.14 — 2 juin 2026 — Les nouveaux enregistrements démarrent sans activité

- Un nouvel enregistrement ne démarre plus par défaut sur « Randonnée » — il démarre sans activité sélectionnée (affiché comme « Aucune »), afin que vous choisissiez vous-même la bonne. Les traces existantes ne changent pas.

---

## 1.37.13 — 1 juin 2026 — Optimize affiche un aperçu du tracé

- La boîte de dialogue Optimize affiche maintenant un **aperçu avant/après du tracé** (original en pâle, résultat optimisé en gras par-dessus) afin que vous puissiez voir le lissage avant d\'enregistrer.

---

## 1.37.12 — 1 juin 2026 — Optimize nettoie le bruit GPS des canyons

- Optimize **nettoie maintenant la trace avant de la simplifier** — il lisse l\'altitude bruitée et redresse le « gribouillis » GPS qu\'on obtient dans les canyons profonds, tout en préservant les vrais lacets. Validé contre une montre à baromètre sur une randonnée en canyon. L\'aperçu et l\'option Enregistrer comme nouvelle gardent toujours votre original en sécurité.

---

## 1.37.11 — 1 juin 2026 — Rogner : Enregistrer comme nouvelle

- **Rogner** une trace propose désormais **Enregistrer comme nouvelle** (comme Optimize) — gardez la version rognée comme trace séparée et laissez l\'original intact.

---

## 1.37.10 — 1 juin 2026 — Montée et descente exactes

- Correction d\'une **montée/descente totale** follement gonflée sur les téléphones sans baromètre (une randonnée en canyon affichait +17 000 m au lieu de ~2 250 m). Le chiffre débruite maintenant l\'altitude avant de l\'additionner, à la manière dont Strava et Komoot calculent le dénivelé. S\'applique à toutes les traces stockées et importées.

---

## 1.37.5 — 21 mai 2026 — Overlay Diagnostics GPS (optionnel)

- Nouvel overlay **Diagnostics GPS** opt-in (Paramètres → Avancé) affichant en direct la qualité du fix, la précision et le détail de la source d\'altitude — utile pour comprendre les enregistrements à signal délicat.

---

## 1.37.0 — 17 mai 2026 — Altimètre barométrique et meilleure altitude

- Sur les téléphones équipés d\'un baromètre, ApexGPS l\'utilise désormais comme **source d\'altitude principale** — stable au mètre près et exempt du bruit GPS et des coupures en canyon.
- La montée/descente utilise maintenant un **seuil de 5 m** (le standard Strava/AllTrails) ; les traces existantes afficheront des chiffres plus petits et plus réalistes.
- Plus une série d\'améliorations de précision pour les téléphones **sans** baromètre — plusieurs contrôles de plausibilité de l\'altitude et un lissage pour rejeter les pics GPS, ainsi qu\'un champ optionnel de précision GPS dans le GPX exporté.

---

## 1.36.0 — 17 mai 2026 — Meilleur enregistrement en canyon

- L\'enregistrement **capture maintenant plus de points dans les canyons et les terrains resserrés** (capture brute avec des seuils de densité plus intelligents), afin que les descentes de canyon profond ne soient pas perdues.
- Nouvelle option **Nettoyer les sauts GPS** dans Optimize pour assainir les traces bruitées après coup.

---

## 1.35.2 — May 15, 2026 — Corbeille fiable · L\'icône poubelle n\'apparaît que pendant le glissement · Le tap près d\'un point milieu fonctionne

- **L\'icône corbeille n\'apparaît plus qu\'au glissement — elle surgit dès que vous faites un appui long sur un sommet ou un point milieu, s\'allume en rouge au survol, et disparaît au relâchement.** Avant, l\'icône était toujours visible en mode mesure et planification mais le geste « appui long puis glisser jusqu\'à la corbeille pour supprimer » n\'était pas évident pour la plupart des utilisateurs — ils voyaient la corbeille mais n\'arrivaient pas à comprendre comment y amener un point. Désormais la corbeille n\'apparaît que lorsque vous avez réellement saisi un point, rendant l\'affordance claire.
- **Lâcher un point milieu sur la corbeille le supprime maintenant de façon fiable.** Deux bugs intermittents corrigés : (1) le tremblement de la position au relâchement laissait parfois les coordonnées de dépôt à quelques pixels en dehors de la zone-poubelle même quand l\'icône s\'allumait en rouge — désormais le rougeoiement affiché est lui-même le signal, donc si vous voyez du rouge au relâchement, le point est supprimé ; (2) à quelques reprises un point milieu lâché sur la corbeille restait visuellement figé au niveau de l\'icône jusqu\'au changement de liste suivant — la ligne revient maintenant proprement à sa forme d\'origine à chaque abandon.
- **Taper la ligne près d\'un point milieu ne déforme plus le segment existant.** Avant, si vous essayiez de taper la ligne pour ajouter un nouveau sommet mais que vous atterrissiez près du point milieu entre deux sommets existants, le segment existant se déformait — votre tap était détourné en un glissement quasi nul qui insérait un sommet pile au point milieu. Désormais le tap est reconnu comme un tap et un nouveau sommet est ajouté à la fin de la liste, exactement comme quand vous tapez n\'importe où ailleurs sur la carte.

---

## 1.35.1 — 15 mai 2026 — Corrections de la corbeille · La planification de tracé commence là où vous avez tapé

- **La corbeille fonctionne désormais quand la carte est pivotée.** Avant, glisser une épingle de mesure ou un sommet de planification sur l\'icône poubelle en haut à droite échouait silencieusement dès que la carte avait été pivotée d\'un degré — l\'icône ne s\'allumait pas en rouge et le dépôt ne supprimait rien. Le test de collision lit maintenant les coordonnées brutes du doigt au lieu du repère interne de la carte pivotée, donc la corbeille fonctionne quelle que soit l\'orientation.
- **Supprimer la première épingle de mesure en mode suivi ne détruit plus l\'épingle suivante.** Quand vous mesurez avec le mode suivi actif, la première épingle (épingle A) s\'auto-cale sur votre position live. La jeter échouait avant de façon déroutante : A semblait revenir au fix GPS suivant, et l\'épingle que vous veniez de poser juste après (B) disparaissait silencieusement. Désormais jeter A garde A absente pour le reste de la session de mesure, et B + toutes les autres épingles restent en place. Basculez le mode mesure off puis on pour replacer A à votre position actuelle.
- **La planification de tracé ne pose plus automatiquement le sommet 1 à votre position actuelle.** La planification est un flux délibéré centré sur une zone de la carte — la plupart des utilisateurs panent vers la zone qu\'ils veulent planifier, puis entrent en mode plan. L\'auto-pose du sommet 1 à votre position GPS surprenait les utilisateurs planifiant des itinéraires lointains. La planification démarre maintenant vide ; le premier appui pose le sommet 1 exactement là où vous avez tapé, où que vous ayez pané la carte.

---

## 1.35.0 — 14 mai 2026 — Partager les traces & points visibles · Économie de batterie à grande vitesse · GPX depuis les messageries

- **Tout ce qui est visible sur la carte se partage d\'un seul appui.** Une nouvelle **icône de partage** s\'affiche en haut à gauche de la carte, juste à gauche du menu ☰. Appuyez dessus et un panneau s\'ouvre, listant chaque trace + point visible dans votre cadre actuel. Cochez ce que vous voulez, appuyez sur **Partager**, choisissez WhatsApp / e-mail / Drive — l\'ensemble part en un seul fichier `.gpx` nommé d\'après la zone que vous regardiez (par ex. `ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx`). Deux autres points d\'entrée utilisent le même panneau : une carte **Partager les traces & points visibles** dans le menu Cartes (utilise le cadre que vous aviez à l\'ouverture du menu), et une icône **partage** dans la barre supérieure des listes Traces / Points lorsque vous appuyez longuement pour en sélectionner plusieurs — regroupe les éléments sélectionnés directement sans panneau supplémentaire.
- **Économie de batterie à grande vitesse.** Un nouvel interrupteur dans **Paramètres → Avancé** (activé par défaut) réduit l\'échantillonnage GPS d\'une fois par seconde à une fois toutes les 10 secondes lorsque vous dépassez 36 km/h — voiture, train, vélo électrique rapide. Les trajets routiers restent enregistrés proprement ; la précision de voie est réduite en voiture. Réduit grosso modo de moitié la consommation GPS sur le tronçon autoroutier d\'un trajet sans perte visible de la forme de l\'itinéraire. Désactivez-le si vous avez besoin d\'un échantillonnage complet à grande vitesse.
- **Ouvrir d\'un appui les fichiers `.gpx` depuis WhatsApp / Telegram / Signal / Outlook.** Avant, les pièces jointes de ces applications retombaient sur la visionneuse de texte système parce qu\'elles annoncent le fichier comme `application/xml` générique au lieu du type MIME GPX canonique. ApexGPS accepte désormais aussi ces types génériques — appuyez une seule fois sur une pièce jointe `.gpx` dans n\'importe quelle messagerie et le menu système « Ouvrir avec » affiche ApexGPS comme option de premier rang.
- **Sauvegardes des cartes hors ligne en mode recette (multiplateforme).** Paramètres → Données → Sauvegarder remplace l\'unique case « Régions de carte enregistrées » par un sélecteur à trois choix : **Ne pas inclure** / **Recette** (petit — liste les régions à retélécharger, fonctionne entre Android et iOS) / **Tuiles complètes** (l\'ancien comportement — embarque les bundles bruts, volumineux mais restaurable hors ligne, Android uniquement). Une sauvegarde recette pèse environ 80 Ko même pour une douzaine de régions ; la restauration ajoute des lignes de remplacement dans **Cartes → Cartes hors ligne enregistrées** avec un bouton **Télécharger** pour récupérer les tuiles à la demande.
- **Le style de carte payant se masque sans clé.** L\'entrée **Outdoors (Thunderforest)** disparaît désormais du sélecteur de style de carte et du sélecteur de téléchargement de région hors ligne tant que vous n\'avez pas collé de clé API sous **Paramètres → Clés API**. Avant, la choisir sans clé retombait silencieusement sur OpenTopoMap sans explication. Collez une clé → l\'entrée réapparaît dans les deux menus.

---

## 1.34.2 — 14 mai 2026 — Masquer les sources de tuiles payantes sans clé

- **Le style « Outdoors (Thunderforest) » se masque désormais entièrement tant que vous n\'avez pas collé de clé API.** Avant, le choisir sans clé retombait silencieusement sur OpenTopoMap sans explication — vous appuyiez sur Outdoors, vous voyiez des tuiles OpenTopoMap, et vous vous demandiez pourquoi. Le sélecteur de style de carte et le sélecteur de téléchargement de région hors ligne omettent tous les deux l\'entrée Outdoors tant que **Paramètres → Clés API → Thunderforest** n\'a pas de clé enregistrée. Collez une clé → Outdoors réapparaît immédiatement dans les deux menus.

---

## 1.34.1 — 13 mai 2026 — Format de sauvegarde v2 (recettes de régions hors ligne, multiplateforme)

- **Les sauvegardes peuvent désormais ignorer les lourds bundles de tuiles et stocker une « recette » à la place.** Paramètres → Données → Sauvegarder remplace la case unique « Régions de carte enregistrées » par un sélecteur à trois choix : **Ne pas inclure** / **Recette** (petit — liste les régions à retélécharger, fonctionne entre Android et iOS) / **Tuiles complètes** (volumineux — l\'ancien comportement, Android uniquement). Une sauvegarde recette fait environ 80 Ko même pour une douzaine de régions ; la sauvegarde tuiles complètes équivalente pourrait peser 50–500 Mo. Restaurez une sauvegarde en mode recette et la liste des cartes enregistrées se remplit de lignes marquées « Pas encore téléchargée · X tuiles » avec un bouton **Télécharger** — appuyez pour retélécharger depuis le serveur de tuiles d\'origine (utilise votre cache actuel + une récupération fraîche pour le reste).
- **Une sauvegarde faite sur Android peut maintenant être restaurée sur iOS et vice versa — sauf pour les bundles de tuiles complets.** Traces, points, paramètres et recettes de régions font tous l\'aller-retour proprement. Le mode tuiles complètes reste Android uniquement parce qu\'iOS ne livre pas de consommateur MBTiles, mais le mode recette couvre les besoins pratiques de la plupart des utilisateurs (reconstruire sur le nouveau téléphone, accepter un court retéléchargement pour les régions qui comptent).
- **Restaurer une recette de style Outdoors vous incite à renseigner la clé API d\'abord.** Si une recette restaurée vise Thunderforest et que vous n\'avez pas de clé enregistrée, appuyer sur **Télécharger** affiche un toast unique vous dirigeant vers **Paramètres → Avancé → Clé API Thunderforest** ; une fois la clé en place, le téléchargement démarre normalement.

---

## 1.34.0 — 13 mai 2026 — Ajustement de tailles · Sports nautiques · Progression de restauration en direct · Pluriels corrects

- **Les marqueurs de waypoints sont environ 25 % plus grands par défaut.** « Normal » (1,0×) rend maintenant à la taille qu\'avait l\'ancien « Grand ». Si les waypoints semblent trop petits, le sélecteur propose toujours Petit / Normal / Grand / XL — Paramètres → Apparence → Taille de waypoint. Le réglage existant est conservé ; envisagez de descendre d\'un cran puisque toute l\'échelle a grandi.
- **Curseurs de découpe — les poignées rondes fonctionnent partout.** Avant, seule la ligne verticale de chaque poignée répondait ; toucher le bouton rond en bas ne déclenchait souvent rien parce que la zone tactile ne descendait pas jusqu\'en bas. Corrigé — les deux poignées rondes se saisissent maintenant depuis n\'importe quel point du cercle plus une petite bande en dessous.
- **Nouveau type d\'activité : Sports nautiques.** Sélectionnable depuis Détails de trace → Activité pour marquer une session de pagaie, voile, surf, kayak ou autre sport nautique. Même icône vague que le waypoint Cascade.
- **La restauration d\'une sauvegarde affiche maintenant une progression en direct.** Une grosse sauvegarde (centaines de traces, milliers de waypoints) bloquait l\'application sur un indicateur pendant plusieurs minutes sans signe de progression — facile à confondre avec un plantage. Le bouton Restaurer est maintenant au-dessus d\'une barre de progression + légende (« Restauration de la trace N sur M… » / « Restauration du waypoint N sur M… ») qui avance par trace puis tous les 100 waypoints.
- **Le polonais et l\'arabe affichent enfin des étiquettes correctement accordées au pluriel.** 13 chaînes contenant des compteurs (« X traces », « Y waypoints », « il y a Z minutes » etc.) passent maintenant par de vraies règles de pluriel. Le polonais obtient ses 4 formes complètes ; l\'arabe ses 6. Anglais / allemand / français / espagnol étaient déjà grammaticalement corrects ; la mécanique sous-jacente passe maintenant par le même chemin de façon cohérente.

---

## 1.33.8 — 10 mai 2026 — Outil mesure & planificateur d\'itinéraire : file d\'attente du premier point

- **Appuyez sur le FAB mesure ou planificateur avant que votre fix GPS soit prêt et le premier point s\'auto-pose dès que votre position arrive.** Avant, appuyer pendant que le GPS chauffait encore laissait un démarrage vide — il fallait toucher la carte manuellement pour poser l\'épingle A. Désormais l\'app affiche « Acquisition du fix GPS… » sur le bouton et met en file le placement auto du premier point ; une fois le fix arrivé, l\'épingle A apparaît à votre position actuelle et le suivi live prend le relais normalement. Reprend le même comportement de file d\'attente que le FAB d\'enregistrement a reçu en 1.33.7. Toucher la carte manuellement pour poser une épingle annule la file, donc vous ne perdez jamais un appui.

---

## 1.33.7 — 10 mai 2026 — Import GPX tolérant · Confidentialité dans À propos · Auto-démarrage de l\'enregistrement

- **Les imports de fichiers GPX avec des coordonnées mal formées ne plantent plus tout l\'import.** Un point de trace ou un waypoint avec une valeur `lat` / `lon` mal formée interrompait auparavant tout l\'import. L\'app ignore désormais le point fautif et continue d\'importer le reste — un mauvais point sur une randonnée de 10 000 points ne fait plus perdre le fichier. Les limites strictes (10 000 traces, 100 000 waypoints, 500 000 points par trace) lèvent toujours une erreur pour éviter les manques mémoire.
- **Politique de confidentialité directement sous Paramètres → À propos.** Une nouvelle ligne « Politique de confidentialité » se trouve sous Guide d\'utilisation ; appuyez pour lire la politique dans l\'app, sans connexion. Le même contenu est miroir sur `apexgps.duttra.de/privacy.html` (l\'URL de confidentialité du Play Store) pour quiconque veut la lire avant d\'installer.
- **Appuyez sur Enregistrer avant votre premier fix GPS et l\'enregistrement s\'auto-démarre dès l\'arrivée du fix.** Avant, appuyer sur Enregistrer avant qu\'un fix soit reçu démarrait immédiatement une trace vide — si vous appuyiez sur Arrêter avant l\'arrivée d\'un fix, vous sauvegardiez une trace à zéro point. Désormais le toast dit « Acquisition du fix GPS… » et l\'enregistrement se déclenche automatiquement à l\'instant où le premier fix non nul arrive — pas besoin d\'un deuxième appui.

---

## 1.33.6 — 9 mai 2026 — Fiabilité de la zone-poubelle après mise en arrière-plan

- **La zone-poubelle pour supprimer un sommet pendant la planification d\'itinéraire ou la mesure fonctionne à nouveau de façon fiable après que l\'application a été minimisée et rouverte depuis Récents.** Un défaut latent faisait que le geste « glisser un sommet sur la corbeille pour le supprimer » cessait silencieusement de fonctionner après que la fenêtre de l\'app se soit détachée puis rattachée (minimiser → toucher depuis Récents). Les limites de la zone-poubelle restaient figées sur les coordonnées d\'avant la mise en arrière-plan tandis que la position de la carte continuait à se mettre à jour, donc les dépôts n\'étaient plus détectés. Le test de collision lit maintenant les limites à neuf à chaque événement de glissement (et seulement quand l\'icône poubelle est effectivement attachée à la fenêtre) — la zone-poubelle reste donc fonctionnelle après n\'importe quel nombre de cycles de retour. Plus besoin de redémarrer l\'application comme contournement.
- **Interne : nettoyages de build pour la revue de production Play Store.** Une dépendance UI mise à jour (`androidx.activity:activity-compose` 1.9.3 → 1.10.1) pour résoudre les avertissements Vitals signalés sur la revue 1.33.5 (« edge-to-edge peut ne pas s\'afficher pour tous les utilisateurs ») — pur nettoyage, aucun changement de comportement. Extraction des symboles de débogage natifs activée pour les builds release (sans effet aujourd\'hui car les seules bibliothèques natives présentes dans l\'AAB sont livrées sans symboles par Google — s\'active automatiquement si une dépendance future en livre).

---

## 1.33.5 — 7 mai 2026 — Cache de tuiles ajustable + randonnée d\'accueil à la première installation

- **Choisissez l\'espace disque alloué au cache des tuiles.** Réglages → Cache hors-ligne propose désormais quatre préréglages : 250 Mo / 500 Mo (défaut) / 1 Go / 2 Go. La nouvelle limite s\'applique immédiatement — pas besoin de redémarrer. Les régions hors-ligne enregistrées sont stockées à part et non comptabilisées : modifier cette valeur ne supprime aucune région que vous avez délibérément téléchargée.
- **Une randonnée d\'accueil à chaque nouvelle installation.** Un enregistrement réel de la **traversée du Watzmann** (Berchtesgaden, Allemagne) — Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, boucle de ~22,6 km / +2250 m / environ 10–12 h de marche — est importé automatiquement lors de la première ouverture de l\'app. Trois points de repère l\'accompagnent (départ Wimbachbrücke, DAV Watzmannhaus, Watzmann-Mittelspitze). Les installations existantes ne sont pas affectées. Si vous supprimez les exemples et les voulez à nouveau plus tard, **Réglages → Données → Charger les exemples** les réimporte à la demande.

---

## 1.33.4 — 5 mai 2026 — Nettoyage des autorisations pour la fiche Play Store

- **Liste d\'autorisations Play Store plus propre.** Suppression d\'une déclaration héritée « stockage USB » qui n\'était jamais utilisée — l\'app met en cache les tuiles dans son stockage interne propre, pas sur USB / stockage partagé. La page d\'autorisations affiche désormais quatre entrées de moins ; rien ne change sur votre téléphone.

---

## 1.33.3 — 4 mai 2026 — Altitude au niveau de la mer correcte + écran de trace épuré + correction du suivi

- **L'altitude de la barre de stats indique maintenant les vrais mètres au-dessus du niveau de la mer.** Sur la plupart des téléphones Android, la puce GPS rapporte l'altitude par rapport à l'*ellipsoïde* — un modèle mathématique lisse de la Terre — et non l'océan réel. Dans le golfe Persique, l'écart est d'environ 30 m ; debout sur la corniche d'Abou Dhabi, on lisait environ **−27 m** au lieu de zéro. L'app utilise maintenant la valeur du niveau moyen de la mer de l'appareil quand elle est disponible (Android 14+ sur matériel compatible) et retombe sur une correction géoïdale globale embarquée (grille EGM96 à 1°, ~128 Ko) sur les appareils qui ne la fournissent pas (le Vivo X300 Pro en est un). Le niveau de la mer indique désormais **+0 m à quelques mètres**, partout dans le monde, quel que soit le téléphone. La même correction est appliquée au texte de position partagée et à l'altitude transmise à la prévision météo.
- **La vitesse de la barre de stats reste à 0 km/h quand vous êtes immobile.** Avant, le tremblement GPS à l'arrêt faisait grimper la vitesse affichée à 1–3 km/h sans mouvement réel. L'affichage indique maintenant zéro tant que vous ne dépassez pas le seuil de précision de vitesse rapporté par votre téléphone — l'enregistrement lui-même utilise toujours la valeur brute, donc un déplacement lent légitime n'est pas masqué.
- **Enregistrements plus propres dans les canyons et les zones bâties.** Trois nouvelles défenses contre les pics d'altitude par multitrajet (quand un mur réfléchit le signal GPS) : le filtre d'enregistrement écarte désormais les lectures d'altitude à mauvaise précision verticale, rejette les sauts brusques de plus de 50 m par rapport au précédent bon fix quel que soit le temps écoulé, et garde son contrôle de débit affûté même après de longues périodes sans altitude. Une trace du canyon de Wadi Hijr du 3 mai présentait huit sauts d'altitude d'une seconde de 70 à 300 m qui passaient à travers l'ancien filtre ; les nouvelles couches les attrapent.
- **Écran détail de trace — disposition simplifiée.** L'icône crayon de la barre d'outils a disparu — **tapez sur le nom de la trace** dans la barre d'outils pour la renommer. Une seule rangée de trois boutons se trouve sous le graphique d'altitude : **Rogner · Optimize Track (X pts) · Supprimer la trace**. L'ancienne pile de boutons pleine largeur et le menu à 3 points sont tous deux supprimés ; tout tient sur un écran de téléphone sans défilement.
- **Optimize est désormais aperçu-puis-enregistrer.** Confirmer l'optimisation dans la boîte de dialogue validait auparavant immédiatement, sans annulation possible. Désormais la trace simplifiée s'affiche dans le graphique + la carte de stats sous une petite boîte de dialogue indiquant `3214 → 500 points · 12.40 → 12.30 km`. **Enregistrer** l'écrit ; **Abandonner** (ou le retour matériel) l'abandonne. Aucune modification de la base tant que vous n'enregistrez pas.
- **FAB Suivre-moi : un seul tap pour reverrouiller.** Un bug faisait que paner la carte (ce qui atténuait le FAB Suivre-moi) puis taper dessus exigeait **deux taps** pour rendre le FAB bleu plein — l'animation de recentrage était mal interprétée comme un pan utilisateur prolongé. Désormais un seul tap reverrouille et recentre, comme cela aurait toujours dû être le cas.

---

## 1.33.2 — 30 avr. 2026 — Look de carte rafraîchi + vague de corrections de bugs

- **Écran de carte plus propre et plus moderne.** La barre supérieure, les FAB Couches / Mesurer / Suivre-moi, le bouton Enregistrer, la barre de stats et la pastille météo sont maintenant translucides — la carte transparaît faiblement derrière eux, ce qui rend l'écran moins cloisonné. La carte elle-même s'étend désormais d'un bord à l'autre, du tout en haut au tout en bas de l'écran.
- **Menus modernisés.** Le menu hamburger (en haut à droite) et le sélecteur de source de tuiles Couches apparaissent maintenant comme des cartes contextuelles arrondies avec icônes de tête, au lieu des rectangles plats qu'ils étaient avant. Les cibles tactiles sont plus grandes ; la source de tuiles active est marquée d'un nom en gras + une coche.
- **Arabe / persan / ourdou — chiffres occidentaux partout.** Les distances, altitudes, coordonnées, heures des notifications de position partagée et l'horloge horaire de la feuille météo ne s'affichent plus en chiffres arabes orientaux (`٣٫٤ كم`) — ils se lisent `3.4 km` quelle que soit la langue du téléphone. C'était une incohérence de longue date dans les étiquettes des graphiques et quelques constructeurs de notifications.
- **Graphiques en arabe : les gestes de balayage dans le bon sens.** Les graphiques d'altitude du détail de trace et de la planification avaient un balayage inversé en arabe — toucher le bord gauche visuel sautait à la fin de l'itinéraire. Désormais le balayage suit votre doigt correctement quelle que soit la langue.
- **Le retour matériel depuis l'aperçu Enregistrer / Abandonner de l'altitude abandonne maintenant l'aperçu** au lieu de naviguer silencieusement ailleurs en perdant la récupération non enregistrée. La barre d'aperçu reprend le motif « êtes-vous sûr ? » du mode planification.
- **La restauration de sauvegarde préserve désormais l'heure de début, l'heure de fin et le tag d'activité de vos traces enregistrées.** Les traces GPX importées étaient déjà couvertes (elles ne portent pas ces champs de toute façon) ; les traces enregistrées perdaient silencieusement les trois à chaque restauration. Si vous avez restauré une sauvegarde depuis l'arrivée de la fonction de marquage d'activité et remarqué que vos randonnées / sorties ont perdu leurs badges — voilà pourquoi. Faites une nouvelle sauvegarde maintenant et la prochaine restauration les conservera.
- **Complétion de traduction (de / fr / es / pl / ar).** Onze chaînes autour du flux de récupération d'altitude (« Récupération de l'altitude… », « Enregistrer », « Abandonner », « Impossible de récupérer l'altitude », etc.) et l'infobulle de balayage du graphique (« Touchez le graphique pour explorer ») sont maintenant traduites. Avant, elles étaient en anglais uniquement sur les téléphones non anglophones.
- **Resserrages divers.** Plusieurs messages d'état « Trace enregistrée » / « Acquisition du fix GPS » s'affichent maintenant comme de rapides toasts (~2 s, ne bloquent pas la carte) au lieu de snackbars en bas (~4 s, bloquaient les taps). Le chemin de démarrage du service d'enregistrement / suivi a été durci contre une rare situation de course pouvant journaliser un avertissement « le service n'a pas démarré ». La récupération d'altitude de la planification est plus rapide sur les longs itinéraires (les connexions réseau par lot sont maintenant réutilisées).

---

## 1.33.1 — 28 avr. 2026 — Tri peaufiné + récupération d'altitude pour les anciennes traces + ESRI par défaut

- **Rappuyez sur une rangée de tri pour inverser le sens.** Dans les listes Traces et Points, taper sur la rangée de tri **active** inverse maintenant l'ordre — `Plus récent d'abord` bascule en `Plus ancien d'abord`, `Nom (A→Z)` bascule en `Nom (Z→A)`, `Plus proche d'abord` bascule en `Plus loin d'abord`, `Plus de points` bascule en `Moins de points`. La rangée active affiche le nom directionnel plus une `✓`. Taper sur une autre rangée choisit le sens naturel de cette clé ; rappuyer l'inverse alors. Pas de bascule asc / desc séparée — garde le menu compact.
- **Triez et filtrez vos traces par activité.** La liste Traces gagne une cinquième clé de tri : **Activité** (alphabétique — Vélo, Randonnée, Tout-terrain, Parapente, Course, Marche). Les traces sans activité assignée tombent en bas en A→Z (et remontent en haut en Z→A) afin de repérer ce qui reste à marquer. Le menu de filtre gagne aussi une section **Activité** — six puces pour les types d'activité plus une puce « Aucune activité » — pour isoler « montre-moi seulement mes traces de randonnée » ou « montre-moi tout ce que je n'ai pas encore marqué ».
- **Tapez pour récupérer l'altitude des traces qui n'en ont pas.** Les fichiers GPX de certaines sources ne portent pas d'altitude par point, donc le détail de trace affichait un graphique d'altitude vide. Désormais : si une trace n'a pas d'altitude, la zone du graphique est remplacée par une carte **Tapez pour récupérer depuis le terrain**. Un tap tire l'altitude d'un modèle de terrain mondial (environ 30 m de précision, sans compte requis) pour chaque point de votre trace. Pendant le chargement vous voyez un compteur de progression `X / Y` et un bouton Annuler. Une fois terminé, le graphique se rend contre les nouvelles altitudes — mais elles ne sont **pas encore enregistrées** : une barre Enregistrer / Abandonner apparaît pour prévisualiser le résultat et faire machine arrière s'il semble incorrect.
- **ESRI Topo est le nouveau fond de carte par défaut sur les nouvelles installations.** Les installations existantes ne sont pas touchées — ce que vous aviez choisi sous **Paramètres → Style de carte** reste. Pour quelqu'un qui installe l'app pour la première fois, la carte s'ouvre sur ESRI Topo au lieu d'OpenTopoMap. Les tuiles ESRI rendent des étiquettes plus nettes aux niveaux de zoom de randonnée, surtout sur les écrans de type iPhone. L'ordre du sélecteur dans Paramètres est inchangé ; revenir en arrière se fait d'un tap.
- **Planification : plus facile de saisir un sommet, dépôt à la corbeille plus fiable.** Les cibles tactiles des sommets de planification et des poignées de point milieu ont reçu une vraie zone de toucher circulaire de ~28 dp (c'était le simple rectangle de l'icône — les ratés du doigt étaient fréquents sur les itinéraires denses). La zone de dépôt à la corbeille a reçu une petite marge de tolérance sur chaque bord, et la vérification « avez-vous lâché sur la corbeille ? » utilise maintenant la position réelle du marqueur en fin de glissement, pas un drapeau « en survol » parfois périmé. Effet net : la corbeille ne « cesse plus de fonctionner » après quelques sommets, et saisir le bon sommet sur un long plan est fiable.

---

## 1.33.0 — 27 avr. 2026 — Planifier une trace sur la carte

- **Nouveau : planification de trace.** Esquissez un itinéraire en tapant des points sur la carte et enregistrez-le comme une Trace normale — utile pour repérer la randonnée de demain, marquer une jonction repérée sur une carte papier, ou simplement dessiner la boucle dont vous vous souvenez. Ouvrez **menu → Traces** et tapez sur le nouveau bouton **+** (au-dessus du bouton dossier d'import). La carte s'ouvre en mode planification : tapez pour ajouter des arrêts numérotés sarcelle, appui long sur un arrêt pour le glisser, appui long sur le petit point entre deux arrêts pour en insérer un nouveau. Glissez n'importe quel arrêt sur l'**icône poubelle** (en haut à droite, sous la boussole) pour le supprimer — la ligne se reconnecte à travers les voisins restants. La corbeille s'allume en rouge quand un arrêt est en survol au-dessus.
- **Profil d'altitude pour les itinéraires planifiés.** Pendant la planification, tapez sur l'**icône graphique** à droite pour voir un vrai graphique d'altitude de votre brouillon. L'app échantillonne votre itinéraire tous les ~100 m et demande à Open-Meteo l'altitude du terrain à chaque échantillon, puis affiche la montée et la descente totales. Les longs itinéraires sont échantillonnés plus grossièrement pour que la récupération reste rapide ; vous verrez un compteur de progression `X / Y` et un bouton Annuler pendant le chargement.
- **Enregistrer le plan.** Tapez sur **✓ Enregistrer** dans la barre supérieure, nommez votre itinéraire, confirmez — la trace planifiée arrive dans votre liste Traces, exportable en GPX, comparable à un futur enregistrement. Si vous aviez chargé le profil d'altitude, la trace enregistrée porte les points échantillonnés denses ; sinon, juste les arrêts que vous avez tapés (avec une altitude à compléter plus tard si vous le souhaitez).

---

## 1.32.4 — 27 avr. 2026 — Correction de la boîte de découpe pour l'arabe

- **La boîte de dialogue Rogner la trace fonctionne maintenant en arabe.** Avant, ouvrir la boîte de découpe d'une trace en arabe n'affichait aucune trace visible tant que vous ne glissiez pas les curseurs vers l'intérieur. Corrigé : le repère de coordonnées du graphique et les gestionnaires de glissement des curseurs restent maintenant cohérents quelle que soit la langue.

---

## 1.32.3 — 27 avr. 2026 — Altitude en un tap pour les points

- **Récupérez l'altitude depuis le terrain.** Quand vous modifiez un point, le champ Alt (m) a maintenant une petite icône de téléchargement à droite. Tapez dessus et l'app remplit l'altitude depuis un modèle de terrain mondial (environ 30 m de précision) en utilisant la latitude / longitude que vous avez saisie. Utile quand vous tapez un point à la main, ou après en avoir glissé un à un nouvel endroit. L'icône est grisée tant que vous n'avez pas de coordonnées valides saisies ; elle affiche un bref indicateur pendant la récupération, et un rapide message « Impossible de récupérer l'altitude » si vous êtes hors ligne. Ce que vous aviez déjà saisi dans le champ est remplacé — vous l'avez demandé explicitement.

---

## 1.32.2 — 26 avr. 2026 — Météo activée par défaut + traductions complètes + bouton retour des Cartes

- **La météo est désormais activée d'origine.** La pastille de prévision et la ligne « Météo ici » sur les waypoints sont visibles sans devoir basculer un réglage. Vous pouvez toujours désactiver la météo dans **Paramètres → Météo** si vous préférez aucun appel réseau — les installations existantes conservent votre réglage précédent.
- **Traductions complètes pour la fonction météo.** Tous les textes météo — la pastille, la feuille (panneau actuel, bandeau 24 heures, tendances humidité / pression, bandeau 7 jours, étiquettes coucher / UV / pression / point de rosée), les rangées dans Paramètres et le titre du chapitre du guide — sont maintenant traduits en allemand, français, espagnol, polonais et arabe. Les libellés de conditions météo (« Pluie légère », « Orage + grêle », « Partiellement nuageux », …) suivent le vocabulaire météorologique standard de chaque langue.
- **Menu Cartes : le bouton retour referme désormais une carte ouverte avant de quitter.** Quand **Télécharger une nouvelle zone** ou **Cartes hors ligne enregistrées** était dépliée, retour ignorait le menu Cartes et vous renvoyait directement à la carte principale. Désormais retour referme d'abord la carte ouverte ; un appui de plus vous ramène à la carte principale. Cela correspond au comportement ailleurs (sous-écrans Paramètres, sélection multiple dans les listes de traces / waypoints).

---

## 1.32.1 — 25 avr. 2026 — Météo : petites corrections

- **Icônes soleil / lune correctes au passage de minuit.** Le bandeau météo sur 24 heures affichait des glyphes lune sur les heures d\'après-midi du *lendemain* (11h00, 14h00, 17h00) lorsqu\'on ouvrait la feuille tard le soir. Chaque heure choisit désormais son propre lever / coucher de soleil, donc les heures de jour montrent toujours les icônes côté soleil.
- **La prévision waypoint utilise vraiment l\'altitude du waypoint.** Quand un waypoint sommet se trouvait pratiquement aux mêmes coordonnées que votre position GPS actuelle, la prévision en cache pour la position courante était parfois renvoyée pour le waypoint au lieu d\'une requête fraîche tenant compte de l\'altitude. Sur un sommet à 1480 m la prévision était ~9 °C trop chaude. Le cache utilise maintenant l\'altitude comme clé, donc l\'altitude stockée du waypoint est toujours respectée.

---

## 1.32.0 — 25 avr. 2026 — Météo : finition par-point, plus d\'overlays carte

Après 1.31.0, les overlays météo en grille n\'ont pas passé le test visuel sur les niveaux de zoom de randonnée — ils apparaissaient comme des carrés colorés sans alignement réel avec le terrain, et la rangée du bas (curseur d\'overlay + pastille + barre vitesse / altitude / distance) prenait trop d\'écran. Cette version dépouille la carte et mise sur la feuille par-point, là où les détails utiles vivent.

- **Overlays carte retirés.** Plus de radar de précipitations ni de couvert nuageux sur le fond de carte, plus de curseur temporel. L\'écran **Paramètres → Météo** se réduit à un seul interrupteur principal.
- **Feuille par-point plus riche.** La feuille météo (toucher la pastille ou la ligne « Météo ici » d\'un waypoint) montre maintenant : panneau actuel avec emoji météo, température, « ressenti » ; lignes pour vent / humidité / point de rosée / pression / UV / coucher ; bandeau 24 heures avec icônes météo horaires + température ; tendance d\'humidité (bleu clair) et tendance de pression (vert) ; et bandeau 7 jours avec maxi / mini + icône. Conçu pour tenir sur un écran de téléphone classique.
- **L\'altitude par-waypoint est envoyée à la prévision.** Les waypoints avec un champ altitude stocké la transmettent au modèle, donc les prévisions de sommet utilisent la vraie hauteur au lieu de l\'altitude moyennée grossière. Idem pour la prévision de la pastille — elle utilise votre altitude GPS.
- **La pastille s\'aligne avec la carte du waypoint.** Le texte de la pastille de la barre de stats correspond désormais à ce que vous voyez en touchant un waypoint : emoji + temp + vent. Un fin séparateur a été ajouté entre la pastille et la rangée vitesse / altitude / distance pour qu\'elles se lisent comme un seul panneau.

---

## 1.31.0 — 25 avr. 2026 — Météo

ApexGPS affiche maintenant des informations météo de niveau randonnée depuis des APIs publiques gratuites, entièrement opt-in.

- **Pastille de prévision dans la barre de stats.** Une fois la météo activée dans **Paramètres → Météo**, une petite pastille au-dessus de la barre vitesse / altitude / distance affiche les conditions actuelles à votre position GPS : température, vent, humidité. La pastille se met à jour toutes les 15 minutes en ligne et indique quand les données sont périmées ou que vous êtes hors-ligne (grise et ajoute une horloge).
- **Feuille déroulante.** Touchez la pastille (ou la nouvelle ligne « Météo ici » d\'un panneau de waypoint) pour le détail complet — relevés actuels, prochaines 24 heures sous forme de courbe de température + barres de précipitations, et bandeau 7 jours avec maxi/mini et icônes.
- **Rafraîchissement manuel.** Un bouton ↻ dans l\'en-tête force une requête fraîche après reconnexion.
- **Overlays animés sur la carte.** Une nouvelle section **Overlays** dans le hub Cartes ajoute deux interrupteurs indépendants : radar de précipitations (pluie animée code couleur, 2 dernières heures + nowcast 30 min) et satellite nuageux (sommets nuageux IR géostationnaires). Ils n\'envoient pas votre position — ce sont juste des tuiles, indépendantes de la pastille météo.
- **Vie privée d\'abord.** Tout est désactivé par défaut. Les prévisions viennent d\'Open-Meteo, le radar de RainViewer ; deux APIs publiques gratuites sans compte ni clé. Votre position n\'est envoyée que si vous activez explicitement la pastille.

Lisez le chapitre complet sous **Paramètres → Guide d\'utilisation → Météo**.

---

## 1.30.2 — 25 avr. 2026

- **Tap sur la boussole respecte le verrouillage de rotation.** Appui long sur la boussole pour verrouiller la rotation de la carte ; une fois verrouillée, un simple tap sur la boussole ne ramène plus la carte au nord. (Il faudrait d\'abord rappuyer long pour déverrouiller, puis tapoter.) Cela rétablit l\'intention du verrou — figer l\'angle contre les entrées involontaires, y compris un tap parasite sur la boussole.
- **Notifications plus brèves, moins intrusives.** Les messages « Supprimé … » / « Déplacé … » / « Arrivé » / suivi-verrouillé / auto-pause-localisation s\'affichent maintenant comme un bref Toast Android (~2 s, overlay système) au lieu d\'un snackbar de 4 s qui bloquait le bas de la carte. Vous pouvez toucher un autre waypoint juste après en avoir supprimé un, sans attendre.

---

## 1.30.0 / 1.30.1 — 25 avr. 2026 — Qualité d\'enregistrement

La première randonnée après 1.29 (4 h 10 min, 9,98 km) a révélé que l\'enregistrement live de trace stockait beaucoup plus de points que nécessaire et avait absorbé une fausse chute d\'altitude due à une lecture d\'altitude bloquée. Les deux corrigés :

- **Enregistrements plus légers, plus lisses.** Un nouveau filtre ne garde un fix que si vous avez bougé d\'au moins 5 m, 15 secondes se sont écoulées ou l\'altitude a changé de 3 m+. Les fixes très imprécis (>25 m) sont écartés. Sur la randonnée test : ~4600 → ~1500 points stockés, aucun changement visible de la trace, distance inchangée. Moins de stockage, exports GPX plus petits, même trace.
- **Plus de fausses chutes d\'altitude.** Le fused location provider de certains Android se bloque et renvoie la même altitude en cache (par ex. `139 m` en randonnée à 1200 m) pendant des minutes. L\'enregistrement traite désormais ces lectures comme « pas de valeur » plutôt que de persister le mauvais chiffre. Le profil d\'altitude montre une coupure propre sur la fenêtre fautive au lieu d\'un creux à zéro, et les stats montée / descente ne reflètent que les vraies variations.
- **Altitude MSL sur Android 14+.** Quand disponible, l\'enregistrement utilise l\'altitude moyenne au-dessus du niveau de la mer plus honnête que le fallback WGS84, sujet au bug ci-dessus.

Si vous avez un enregistrement antérieur à 1.30.0 avec une mauvaise altitude, vous pouvez le refaire — l\'affichage dans la trace utilise les points persistés. Pas d\'étape de migration.

---

## 1.29.0 — 24 avr. 2026

- **Enregistrement live de trace.** Appuyez sur la pastille rouge en haut à gauche de la carte pour démarrer l\'enregistrement de votre sortie. Un chrono live `HH:MM:SS` remplace la pastille ; tap pour **Pause / Terminer / Supprimer**. Votre parcours se dessine comme une ligne rouge au fil de vos déplacements. Sur **Terminer** l\'enregistrement est sauvegardé comme nouvelle Trace et le panneau s\'ouvre automatiquement pour consulter distance, dénivelé et profil d\'altitude tout de suite.
- **Rogner la trace.** Sur l\'écran détail, **Rogner la trace** ouvre une boîte avec une mini-carte en aperçu et deux poignées glissables sur le graphique d\'altitude. Coupez un mauvais début (pas encore de fix GPS) ou une fin parasite (oublié d\'appuyer sur Terminer) sans perdre le reste de la trace. Destructif — une étape de confirmation dit exactement combien de points vous allez perdre.
- **Tag d\'activité par trace.** L\'écran Détail de trace a un nouveau menu **Activité** : Randonnée · Marche · Course · Vélo · Tout-terrain · Parapente. Les enregistrements démarrent par défaut en Randonnée ; les traces importées sans tag.
- **Altitude de point.** Le sheet d\'édition de point a un nouveau champ optionnel **Altitude (m)** — remplissez-le quand vous voulez porter une altitude pour un sommet / col connu / etc. Vide = aucune altitude stockée (comme pour les points importés sans donnée d\'altitude aujourd\'hui).
- **Détail de trace + édition de point rafraîchis.** Cartes groupées, libellés de section, icônes sur chaque ligne, icône spécifique à l\'activité sur la puce Activité, **Supprimer** encadré rouge pour coller à l\'action destructive, nouvelle stat **Points** sur l\'écran trace. L\'édition de point est plus serrée — le formulaire entier tient désormais au-dessus de la barre de navigation système sur la plupart des téléphones sans défilement.
- **Récupération après mort du processus.** Si Android tue l\'app en pleine sortie (mémoire faible, arrêt forcé), la ligne est préservée. Rouvrez l\'app et l\'enregistrement revient en pause — reprendre, terminer ou jeter.
- **Économie de batterie : cadence GPS adaptative.** Pendant l\'enregistrement écran éteint, la cadence des fixes passe de 2 s à 10 s pour économiser la batterie. Dès que vous déverrouillez le téléphone elle revient à 2 s pour la fluidité. Entièrement automatique.
- **Protection localisation système.** Appuyer sur enregistrer alors que l\'interrupteur de localisation système Android est désactivé affiche désormais un message avec un raccourci **Paramètres** au lieu de démarrer silencieusement un enregistrement mort.
- **Indice no-fix.** Si vous appuyez sur enregistrer avant que le GPS ait acquis un fix, un court message *« Acquisition GPS… »* vous explique pourquoi la ligne n\'a pas démarré. L\'enregistrement commence dès que le premier fix arrive.
- **Supprimé :** le bouton panique optionnel. La zone en haut à gauche appartient maintenant à la pastille d\'enregistrement.

---

## 1.28.0 — 24 avr. 2026

- **Arabe ajouté.** العربية rejoint l\'allemand, le français, l\'espagnol et le polonais aux côtés de l\'anglais. Six langues d\'interface dans **Paramètres → Apparence → Langue**.
- **Panneau des points maintenant traduit.** Un tap sur un point affichait auparavant « Elev 145 m · Dist 0,42 km » en anglais — quelle que soit la langue de l\'app. Désormais il suit la langue (ex. « Alt 145 m · Dist 0,42 km »).
- **Les chiffres restent occidentaux dans toutes les langues.** Coordonnées, distances, altitudes, caps — toujours `25.165`, `145`, `0.42`. Cohérent avec Google Maps / WhatsApp.

---

## 1.27.0 — 23 avr. 2026

- **Cinq langues d\'interface.** Allemand, français, espagnol, polonais et anglais. Choix dans **Paramètres → Apparence → Langue**, ou « Système par défaut » pour suivre le téléphone.
- **Guide hors ligne dans votre langue.** Les 11 chapitres du guide utilisateur (Paramètres → À propos → Guide utilisateur) sont traduits.
- **La langue survit à une restauration.** La langue choisie est incluse dans le ZIP.
- **Barre de stats aussi traduite.** VIT / ALT / DIST changent avec la langue.

---

## 1.26.2 — 22 avr. 2026

- **Clé API Thunderforest chiffrée au repos.** La clé collée dans **Paramètres → Avancé** est stockée dans un coffre-fort basé sur l\'Android Keystore, plus en clair. Les clés existantes migrent automatiquement au premier lancement. Les sauvegardes incluant les paramètres transportent la clé dans le ZIP (nécessaire pour la portabilité) — un nouvel avertissement rouge dans le dialogue de sauvegarde le rappelle.
- **Restauration plus sûre.** La restauration rejette désormais les ZIP avec traversal, limite à 100 000 entrées, 500 Mo par entrée et 2 Go total décompressé. Les sauvegardes malformées ne peuvent plus remplir votre stockage ni sortir du dossier de sauvegarde.
- **Bouton Annuler sur la sauvegarde.** Pendant une sauvegarde en cours, vous pouvez cliquer **Annuler** sous le bouton occupé pour interrompre sans attendre.
- **Progression de l\'import GPX.** Un snackbar « Import GPX… » s\'affiche pendant les gros imports — l\'app ne semble plus gelée.
- **Service de localisation plus fiable sur Android 14+.** Le service GPS démarre correctement sur Android 14 et 15 (auparavant parfois tué silencieusement). Périmètre du wake-lock réduit — devrait améliorer la batterie en suivi long.
- **Correction aperçu tuiles + hygiène en arrière-plan.** L\'aperçu de la fiche Carte hors ligne charge sans bloquer l\'UI. Interne : le service de téléchargement de tuiles ne peut plus ANR au shutdown. Les builds release n\'expulsent plus de logs de debug.
- **Supprimé :** le lien Buy-me-a-coffee dans Paramètres → À propos. ApexGPS reste gratuit sans pub, sans tracking, sans cloud.
- **Interne (pour les curieux) :** la base Room a désormais des migrations explicites (1→2→3) ; les upgrades préservent vos traces et points même si le schéma change. Le wipe au downgrade reste — sideloader une vieille APK par-dessus une neuve réinitialisera la base.

---

## 1.26.1 — 22 avr. 2026

- **Aperçu carte hors ligne — biseau corrigé.** L\'aperçu dans **Menu → Cartes hors ligne enregistrées → [tap une région]** débordait sur les stats et le bouton « Afficher sur la carte ». Il est désormais correctement coupé sur son rectangle 1,6:1.
- **Lien « Lire en ligne » in-app** dans Paramètres → À propos pointe vers `apexgps.duttra.de/docs/` (la doc rendue) au lieu de la vue brute GitHub.
- **Buy me a coffee.** Nouvelle section Support dans **Paramètres → À propos**. ApexGPS reste gratuit sans pub ni tracking — si vous aimez, un petit pourboire aide à financer les nouvelles fonctions.

---

## 1.26.0 — 21 avr. 2026

- **Guide utilisateur hors ligne.** Le guide complet de 10 chapitres est embarqué dans l\'app — ouvrez **Paramètres → À propos** et tap sur un chapitre pour le lire sans connexion. Les liens entre chapitres marchent in-app ; les liens externes ouvrent le navigateur.
- **Charger les données d\'exemple.** Nouveau bouton dans **Paramètres → Données** charge 3 points (Sommet / Point de vue / Départ de sentier) et 3 traces de longueurs et profils variés. Pour essayer l\'app sans GPX perso. Supprimables ensuite — ce sont des traces/points normaux après import.
- **Naviguer active le GPS automatiquement.** Tap sur Naviguer depuis une position partagée ou un point active la position en direct si elle était coupée. Plus de blocage « Acquisition GPS… » alors que vous vouliez démarrer la nav.
- **Pan de la carte re-déverrouille le suivi.** Régression des builds 1.2x : sous mises à jour GPS continues, la carte revenait à votre position chaque seconde même après un pan. Pan sur la carte → caméra déverrouillée (FAB en bleu moyen) comme avant ; le triangle continue de se mettre à jour.
- **Symboles qui plantaient.** Importer un GPX avec les symboles Point de vue / Col / Cascade / Pique-nique / Eau potable / Panneau / Ruines / Toilettes pouvait planter l\'app au rendu. Corrigé — les 32 symboles s\'affichent correctement.

---

## 1.25.x — 21 avr. 2026

- **Import GPX depuis la liste Traces** (icône dossier en haut à droite). Idem liste Points. Le FAB d\'import de la carte est supprimé — ce sont les écrans liste qui gèrent l\'import.
- **Ajouter un point par coordonnées** — « + » bleu dans la liste Points ouvre la boîte d\'édition avec Lat/Lon vides. Tapez ou collez une chaîne `lat, lon` dans Latitude (division automatique).
- **Modifier les coordonnées d\'un point.** Lat et Lon sont éditables avec validation inline (lat ∈ [-90, 90], lon ∈ [-180, 180]).
- **FAB Suivre-moi déplacé en bas** de la colonne de droite — au plus près du pouce. Couches au-dessus, Mesurer encore au-dessus.

---

## 1.24.x — 19 avr. 2026

- **Boussole de navigation plein écran.** En navigation, tap sur 🧭 dans la barre ouvre une grande boussole analogique : distance / ETA / vitesse / altitude en haut, cadran tournant avec aiguille bleue pointant le point, lat/lon/cap/précision en bas. Glisser vers le bas pour minimiser. Voir [Partager → La boussole](share-and-navigate.md#la-boussole-de-navigation-plein-écran).
- **Partager un point.** Panneau point avec un bouton Partager à côté de Naviguer et Modifier. Envoie le point via n\'importe quelle app de messagerie ; les destinataires avec ApexGPS l\'ouvrent directement comme position partagée, à enregistrer.
- **Barre de nav + barre stats plus propres.** La barre de nav affiche cap + ETA (cap en bleu — live), la distance est dans DIST de la barre stats. Plus de doublons.
- Aiguille de la boussole épurée au pivot central (polish visuel).

## 1.23.0 — 19 avr. 2026

- **Naviguer vers n\'importe quel point** directement depuis son panneau. Tap sur l\'icône personne marchant à côté de Modifier — même ligne bleu clair pointillée + distance/cap live + arrêt auto à 20 m que la nav de position partagée. Voir [Points → Naviguer vers un point](waypoints.md#naviguer-vers-un-point).

## 1.22.2 — 19 avr. 2026

- **Lien guide utilisateur** dans Paramètres → À propos. Ouvre cette doc dans le navigateur.

## 1.21.0 — 19 avr. 2026

- **Suivre-moi : pannez librement.** Glisser la carte ne se bat plus avec le GPS — le triangle continue, mais la carte reste où vous l\'avez posée. Tap sur le bouton pour re-centrer. Appui long pour couper le GPS instantanément. Trois états visibles (off / verrouillé / déverrouillé).
- **Boussole vers nord animée** au lieu de sauter. Retour au nord plus doux.

## 1.20.0 — 19 avr. 2026

- **Naviguer vers une position partagée.** Quand quelqu\'un vous partage un lien `apexgps.duttra.de`, tap sur Naviguer dans la barre du bas pour dessiner une ligne bleu clair pointillée de votre position à la sienne avec distance et cap live. Arrêt auto à 20 m. Voir [Partager → Naviguer vers une position partagée](share-and-navigate.md#naviguer-vers-une-position-partagée).
- **Repère visuel des positions partagées.** Une cible rouge apparaît à l\'endroit partagé. [Enregistrer] comme point ou [Masquer] pour effacer.

## 1.19.0 — 19 avr. 2026

- **Liste Points : filtre + tri.** Filtre par couleur ou symbole, tri par date / nom / plus proche. Même chose que les Traces. Voir [Points → Liste des points](waypoints.md#liste-des-points-menu--points).
- **Format de message partagé plus propre** — URL étiquetées (`ApexGPS:` / `Google Maps:`) avec ligne vide au-dessus.

## 1.18.x — 19 avr. 2026

- **Partager votre position actuelle.** Tap sur le triangle bleu → panneau info avec altitude, précision, heure, batterie → Partager via WhatsApp, SMS, e-mail, etc. Détails dans [Partager & naviguer](share-and-navigate.md).
- **App Links.** Les positions partagées depuis ApexGPS ouvrent directement l\'app sur les appareils qui l\'ont, avec marqueur rouge.
- **Fallback web** — si le destinataire n\'a pas ApexGPS, le lien ouvre une page avec aperçu + bouton Google Maps.

## 1.17.6 — 18 avr. 2026

- **Hub Cartes** redessiné. Téléchargement nouvelle zone et cartes hors ligne enregistrées vivent sur un seul écran, en cartes dépliables. Voir [Cartes hors ligne](offline-maps.md).
- Correction coins noirs à la rotation (plus de triangles noirs sur les bords).

## 1.16.0 — 17 avr. 2026

- **Paramètres** réorganisés en sous-écrans (Apparence / Stockage / Données / Clés API / À propos) avec aide inline.
- **Taille des points** (Petit / Normal / Grand / XL) dans Apparence.
- **Verrouillage rotation au lancement** — pour ceux qui haïssent les rotations accidentelles.

## 1.15.0 et antérieures

- App noyau : import GPX, liste traces, points avec 32 symboles, téléchargement cartes hors ligne, boussole + rotation, mesure de distance, sauvegarde/restauration ZIP, optimisation de trace.

---

*Pour un niveau de détail bug-report ou contexte dev, voir le [repo privé](mailto:sandwalker.one@proton.me) — contacter le développeur pour l\'accès.*
