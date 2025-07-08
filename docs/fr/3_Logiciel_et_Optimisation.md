# Chapitre III : Logiciel et Optimisation

Une fois les modifications matérielles terminées, l'étape suivante consistait à installer l'écosystème logiciel le plus adapté à ce matériel et à le transformer en une station de travail efficace.

## A. La Quête du Système d'Exploitation : Une Aventure Ardue

*   **Problème :** Un processeur de faible puissance comme l'Intel Atom Z8500 peut facilement être mis à rude épreuve par les systèmes d'exploitation modernes. Mon objectif était de trouver le système offrant l'expérience la plus fluide, tant pour la consommation de médias que pour la productivité.
*   **Expériences et Résultats :**
    *   **L'Aventure Ubuntu :** Pendant l'installation, l'écran s'éteignait constamment à des moments aléatoires, ce qui a non seulement interrompu le processus d'installation, mais a également montré qu'une utilisation stable serait impossible.
    *   **La Tentative Debian (Net Install) :** Dans le but de créer un double démarrage, j'ai effectué l'installation la plus minimale possible de Debian. Mon objectif était de créer un environnement Linux ultra-léger pour la consommation de médias. Cependant, le résultat a été une expérience extrêmement lente, lourde et loin des capacités matérielles de la tablette par rapport à Windows 10, se transformant en une véritable torture.
*   **Décision Finale :** Les tests ont confirmé que pour cette combinaison matérielle spécifique, la plateforme la plus stable, compatible et performante était **Windows 10**. L'intégration sans faille des pilotes pour l'écran tactile, le stylet et les capteurs a été un facteur décisif.

<p align="center">
  <img src="../../assets/images/debian%20net%20install%20kde%20plasma%20denerken%20kod%20ekrani%20a%C3%A7%C4%B1k.jpg" width="550">
</p>
<p align="center">
  <i>Juste une des innombrables tentatives dans le monde de Linux. Chaque distribution a présenté un défi différent en matière de compatibilité matérielle.</i>
</p>

## B. Choix Logiciels Cruciaux : Vitesse et Stabilité

Voici les logiciels qui ont le mieux fonctionné sur ce matériel et qui ont transformé la tablette en une véritable station de travail portable, en offrant un **démarrage rapide et une utilisation stable** :

| Catégorie | Logiciel Choisi | Description et Lien de Téléchargement |
| :--- | :--- | :--- |
| **Codage** | **Sublime Text** | Grâce à sa structure incroyablement légère, il s'ouvre instantanément et offre une utilisation fluide même avec les plus gros fichiers de code. <br> *[Site Officiel](https://www.sublimetext.com/)* |
| **PDF** | **PDF-XChange Editor** | Contrairement aux alternatives lourdes comme Adobe Reader, il s'ouvre très rapidement et offre des performances stables sans ralentir, même en naviguant dans de gros PDF. <br> *[Site Officiel](https://www.tracker-software.com/product/pdf-xchange-editor)* |
| **Bureautique** | **SoftMaker FreeOffice** | L'alternative la plus rapide et la plus légère à Microsoft Office. Il ouvre et modifie les fichiers Word, Excel et PowerPoint à une vitesse surprenante. <br> *[Site Officiel](https://www.freeoffice.com/en/)* |
| **E-mail**| **Wino Mail** | Combine une interface moderne et épurée avec une structure légère qui ne consomme pas les ressources système. <br> *[Microsoft Store](https://apps.microsoft.com/detail/9ncrcvjc50wl?hl=en-us&gl=us)* |
| **Bureau à Distance**| **Parsec** | Grâce à sa technologie à faible latence, il permet de se connecter à distance à l'ordinateur principal et d'effectuer des tâches lourdes de manière fluide depuis cette tablette. <br> *[Site Officiel](https://parsec.app/)* |

<p align="center">
  <img src="../../assets/images/programs.jpg" width="700">
</p>
<p align="center">
  <i>Des logiciels légers et puissants qui révèlent le potentiel de l'appareil.</i>
</p>

## C. Optimisations pour l'Usage Quotidien

| Problème YouTube et Solution | Solution OneNote et Stylet |
| :---: | :---: |
| <img src="../../assets/images/freetube.jpg" width="350"> | <img src="../../assets/images/one%20note%20for%20windows%2010%20tablet%20d%C4%B1%C5%9F%20%C3%A7ekim.jpg" width="350"> |
| **Problème :** Regarder YouTube depuis un navigateur signifiait des saccades constantes et des décalages audio/vidéo. <br><br> **Solution :** Le client **[FreeTube](https://freetubeapp.io/)**, qui contourne le navigateur, a été installé. Cette seule application a complètement transformé la capacité de consommation de médias de la tablette, offrant une expérience fluide, sans publicité et sans aucune saccade. | **Problème :** Absence d'une application de prise de notes fluide et d'un stylet. <br><br> **Solution :** La version la plus rapide, `OneNote for Windows 10` (du Microsoft Store), a été combinée avec l'application **[VirtualTablet](https://www.sunnysidesoft.com/virtualtablet/)**. VirtualTablet connecte le téléphone au PC comme une tablette graphique, me permettant d'utiliser le stylet du téléphone dans OneNote. |

### Optimisation du Navigateur et Astuces pour l'Écran Tactile
*   **Le Navigateur le plus Rapide :** Dans ma quête pour trouver le meilleur navigateur pour ce matériel, j'ai testé toutes les alternatives populaires. Les tests ont clairement montré que le navigateur consommant le moins de ressources système et offrant les performances les plus fluides est **Microsoft Edge**.
*   **Consommation Média Générale :** Hormis YouTube, l'appareil ne rencontre aucun problème pour la lecture de vidéos depuis le navigateur, comme regarder des films ou des séries. Le navigateur Edge optimisé peut lire ce type de contenu de manière fluide.
*   **Problème Tactile Critique sur les Navigateurs Basés sur Chromium et sa Solution :**
    *   **Problème :** Sur des navigateurs comme Chrome ou Brave, en appuyant sur le bouton "ouvrir un nouvel onglet" (+), le système interprétait mal la position précise du toucher et agissait comme si le bouton "fermer l'onglet" (X) juste à côté avait été pressé.
    *   **Solution :** Pour surmonter ce problème, il faut **maintenir le doigt sur le bouton pendant un court instant à chaque clic** au lieu de simplement taper. Ce petit délai donne au système suffisamment de temps pour reconnaître correctement la bonne position.

Grâce à ces logiciels et optimisations, la tablette a surmonté tous les inconvénients de son matériel pour devenir un système Windows portable complet.

---
**[← Chapitre Précédent : Évolution Matérielle](./2_Evolution_Materielle.md) | [Chapitre Suivant : Au-delà des Limites - Nouvelles Capacités →](./4_Au-dela_des_Limites.md)**

---
<div align="center">

**[📥 Télécharger cette page (Fichier .md)](https://raw.githubusercontent.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/main/docs/fr/3_Logiciel_et_Optimisation.md)** | **[📦 Télécharger le projet complet (.zip)](https://github.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/archive/refs/heads/main.zip)**

</div>