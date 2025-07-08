# Chapitre II : Évolution Matérielle

Ce chapitre détaille les modifications et améliorations matérielles qui ont permis de transcender les capacités standard de l'appareil.

## Rétro-ingénierie : Analyse du Port d'Ancrage

*   **Objectif :** Analyser le connecteur magnétique **Pogo-Pin** à 5 broches situé sous la tablette, conçu pour son clavier d'origine, afin de le transformer en un port fonctionnel.
*   **Méthode :** La structure des broches a été vérifiée à l'aide d'un schéma technique fourni par le fabricant (Photo 1) et de mesures effectuées avec un multimètre. Sur la base de cette vérification, j'ai créé mon propre schéma de connexion (Photo 2). L'analyse a révélé que le port abritait une interface USB 2.0 pleinement fonctionnelle.
*   **Résultat :** Avec les informations obtenues, un adaptateur personnalisé a été fabriqué pour doter l'appareil d'un port USB-A externe. L'adaptateur a été conçu pour s'adapter parfaitement à la cavité interne de la tablette, préservant ainsi l'intégrité ergonomique.

<p float="left">
  <img src="../../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../../assets/images/pin%20diyagram%20tablet.png" width="400" />
</p>
<p align="center">
  <i>Photo 1 : Schéma original fourni par le fabricant. &nbsp;&nbsp;&nbsp;&nbsp; Photo 2 : Structure des broches vérifiée par mes propres mesures. (Face avant = écran, face arrière = coque)</i>
</p>

### Numérotation et Fonctions des Broches

La configuration des broches obtenue suite à l'analyse est la suivante :

| Numéro de Broche | Fonction              | Correspondance Schéma | Description                                                                   |
| :--------------: | --------------------- | :-------------------: | ----------------------------------------------------------------------------- |
| **1**            | **Alimentation +5V**  |      `+V_5P0_KB`      | Fournit l'alimentation aux accessoires externes. Conforme aux normes USB.   |
| **2**            | **Données USB - (DN)**|    `USB2_MODEM_DN`    | Ligne de données négative standard USB 2.0.                                 |
| **3**            | **Données USB + (DP)**|    `USB2_MODEM_DP`    | Ligne de données positive standard USB 2.0.                                 |
| **4**            | **Détection Clavier** |        `KB_DET`       | Détecte si le clavier est connecté. Activé par le clavier externe en étant tiré vers la masse (Broche 5) à travers une **résistance de 1k Ohm**. |
| **5**            | **Masse (GND)**       |         `GND`         | Masse de référence commune pour le circuit.                                   |

<p align="center">
  <img src="../../assets/images/tablete%20ba%C4%9Flanan%20usb%20di%C5%9Fi%20k%C4%B1s%C4%B1m.jpg" width="450">
</p>
<p align="center">
  <i>La prise USB personnalisée conçue sur la base des informations obtenues par rétro-ingénierie.</i>
</p>

## Avant de Commencer les Modifications : Ouverture du Boîtier

**AVERTISSEMENT :** Ces opérations nécessitent de l'expérience. Vous pourriez causer des dommages permanents à votre appareil et annuler la garantie. Vous assumez l'entière responsabilité.

*   **Outils Requis :**
    *   Embout de tournevis Torx T4
    *   Un outil fin et flexible pour faire levier, comme un médiator en plastique ou une vieille carte de crédit

*   **Instructions de Démontage :**
    1.  **Retirez les Bonnes Vis :** Dévissez **toutes les vis** de la coque arrière. Celles-ci incluent les vis noires sur le support (kickstand) et les vis blanches/argentées en bas.
    2.  **AVERTISSEMENT CRITIQUE :** Ne touchez **jamais** aux vis de la charnière qui relient le kickstand directement au châssis métallique de la tablette ! Retirer ces vis complique le remontage de l'appareil et est une étape inutile.
    3.  **Séparez la Coque :** Une fois toutes les vis retirées, insérez délicatement l'outil en plastique entre le boîtier et la coque arrière et faites sauter doucement les clips pour séparer la coque.

<p align="center">
  <img src="../../assets/images/tablet%20kasa.jpg" width="700">
</p>
<p align="center">
  <i>Processus de démontage : Les vis connectant le kickstand à la charnière (3x2 noires) et les 4 vis argentées en dessous doivent être retirées.</i>
</p>

*   **Conseils de Montage :**
    *   Lors de l'installation des vis inférieures près des parties magnétiques, la vis peut glisser de son logement en raison de l'attraction magnétique. Vous devrez peut-être guider la vis avec votre doigt pour l'aligner.
    *   Manipulez les nappes (câbles plats) avec une extrême délicatesse ; elles peuvent se déchirer facilement.
    *   Veillez à ce que les vis ou les outils métalliques n'entrent pas en contact avec les composants SMD sur la carte mère, afin d'éviter les courts-circuits.

## Modification 1 : Mise à Niveau du Système Audio

*   **Problème :** Les haut-parleurs d'origine de l'appareil avaient un son faible et aigu, particulièrement insuffisant pour les contenus avec des dialogues.
*   **Solution :** Une paire de haut-parleurs de meilleure qualité, avec leurs propres chambres acoustiques, provenant d'un vieil ordinateur portable, a été soudée aux sorties des haut-parleurs d'origine de la tablette.
*   **Détail d'Ingénierie :** Les câbles des haut-parleurs ont été passés à travers les grilles de haut-parleurs d'origine de la tablette. Les haut-parleurs ont été positionnés pour s'adapter parfaitement à la géométrie du boîtier, préservant ainsi l'ergonomie et l'intégrité physique de l'appareil. Le résultat a été une amélioration significative de la qualité sonore.

<p align="center">
  <img src="../../assets/images/hoparlor_lehimlerken.jpg" width="450">
</p>
<p align="center">
  <i>Montage de l'ancien haut-parleur d'ordinateur portable.</i>
</p>

## Modification 2 : Résolution du Problème du "Clavier Fantôme"

*   **Problème :** Le contact des broches métalliques de la prise USB personnalisée avec le châssis en aluminium de la tablette déclenchait involontairement la broche `KB_DET` (Détection Clavier), ce qui bloquait des fonctions comme la rotation automatique de l'écran. Débrancher et rebrancher la batterie résolvait temporairement le problème, mais l'erreur se répétait car le contact persistait.
*   **Solution :** La zone de contact a été isolée électriquement à l'aide de colle chaude, un matériau isolant, ce qui a résolu le problème de manière permanente.

## Autres Améliorations Mécaniques

*   **Remplacement de la Lentille de Caméra :** La lentille de caméra d'origine, qui était rayée, a été remplacée par une lentille intacte soigneusement extraite d'un vieil ordinateur portable en brisant son châssis. Le montage a été réalisé en conservant l'adhésif d'origine de la lentille.
*   **Élimination du Grincement du Châssis :** Des pièces de support ont été ajoutées à l'intérieur aux points de flexion du boîtier pour empêcher l'affaissement, augmentant ainsi la stabilité mécanique et éliminant complètement les grincements.

<p align="center">
  <img src="../../assets/images/tablet%20modifiye%20edilmi%C5%9F%20hal%20i%C3%A7i.png">
</p>
<p align="center">
  <i>Disposition interne de la tablette une fois toutes les modifications terminées.</i>
</p>

---
**[← Chapitre Précédent : Réparation et Résurrection](./1_Reparation_et_Resurrection.md) | [Chapitre Suivant : Logiciel et Optimisation →](./3_Logiciel_et_Optimisation.md)**

