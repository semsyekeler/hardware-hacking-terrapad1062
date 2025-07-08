# Chapitre I : Réparation et Résurrection

Tout a commencé après une tentative infructueuse d'installation d'un système d'exploitation (Brunch OS). La tablette ne pouvait ni démarrer Windows, ni poursuivre l'installation ; elle entrait constamment dans une boucle de "Réparation Automatique" ou tombait directement sur l'écran UEFI Shell. L'appareil était "brické" logiciellement, devenu totalement inutilisable.

## Diagnostic de la Panne : Une Approche Systématique et Factuelle

Pour trouver l'origine du problème, j'ai suivi une méthode simple mais efficace : tester le matériel à deux niveaux distincts, le noyau du système d'exploitation et le firmware de l'appareil lui-même.

| **Niveau 1 : Test Matériel avec le Noyau Linux** | **Niveau 2 : Test de l'Appareil avec le Firmware UEFI** |
| :---: | :---: |
| En démarrant le système avec une clé USB Live de Linux Mint, l'application `GParted` a reconnu sans problème le stockage eMMC de 64 Go de la tablette. Je pouvais créer des partitions et les formater. C'était la preuve claire et nette que la puce de stockage était physiquement intacte. | Sur l'écran UEFI Shell, cependant, la commande `map -r` qui liste les périphériques n'affichait aucune entrée (`blkX`) correspondant au stockage eMMC. Cela révélait que le cerveau de la tablette, l'UEFI, ne pouvait pas reconnaître au niveau matériel une mémoire pourtant physiquement fonctionnelle. |
| <img src="../../assets/images/thumbnail_17477595295231327780041398629873.jpg.jpg" width="450"> | <img src="../../assets/images/Outlook-qgcwu443.png" width="450"> |
| *GParted indiquait que la puce eMMC était vivante. Le problème n'était pas matériel.* | *La commande `map -r` prouvait que l'UEFI ne voyait pas cette même mémoire.* |

**Diagnostic Final :** Bien que les résultats de ces deux tests semblent contradictoires, ils pointaient en réalité précisément vers le problème : l'anomalie ne se situait pas dans la puce eMMC elle-même, mais dans une corruption de la configuration du firmware UEFI ou de sa NVRAM. L'installation ratée avait corrompu la couche logicielle qui permet à l'appareil de reconnaître son propre matériel.

## Solution : Surmonter la Contrainte du Port Unique

Lorsque j'ai présenté ces preuves claires au support technique de Wortmann AG, ils ont confirmé que le problème était connu et que la solution consistait à reflasher le BIOS. Ils m'ont fourni le fichier BIOS nécessaire et les instructions.

Cependant, il y avait une contrainte matérielle sérieuse : **un seul port USB** sur l'appareil. Le processus de flashage nécessitait à la fois un clavier USB pour taper les commandes et une clé USB contenant les fichiers.

Pour surmonter ce problème, j'ai développé la méthode suivante :

1.  **Mémoriser la Commande :** J'ai d'abord branché le clavier USB. Dans l'EFI Shell, j'ai tapé la commande `Flash.nsh` et appuyé sur Entrée (sans me soucier du message d'erreur). Cela a enregistré la commande dans l'historique temporaire du Shell.
2.  **Changer de Périphérique :** J'ai débranché le clavier et branché la clé USB contenant les fichiers du BIOS.
3.  **Rappeler la Commande :** Sans clavier, j'ai utilisé les **boutons physiques de Volume Haut/Bas** de la tablette pour naviguer dans l'historique des commandes. Lorsque la commande `Flash.nsh` est réapparue à l'écran, j'ai appuyé une fois sur le **Bouton d'Alimentation** (qui agit comme la touche Entrée) pour exécuter la commande.

Grâce à cette méthode peu orthodoxe, le flashage s'est terminé avec succès, et le cerveau de la tablette a de nouveau reconnu la mémoire qu'il avait oubliée. Avec cette opération, l'appareil est sorti du coma et est revenu à la vie.

### Fichiers Requis

*   **Fichier BIOS du Terra Pad 1062 :** Vous pouvez accéder au fichier de flashage du BIOS fourni par le fabricant via le lien ci-dessous.
    *   [Lien de Téléchargement pour TERRAPAD1062_BIOS_FLASH.zip](https://github.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/raw/refs/heads/main/TERRAPAD1062_BIOS_FLASH.zip)
    *   **Avertissement :** La mise à jour du BIOS est une opération risquée. Vous assumez l'entière responsabilité de l'utilisation de ce fichier. Assurez-vous que l'alimentation de l'appareil n'est pas interrompue pendant le processus.

---
**[Chapitre Suivant : Évolution Matérielle →](./2_Evolution_Materielle.md)**

---
<div align="center">

**[📥 Télécharger cette page (Fichier .md)](https://raw.githubusercontent.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/main/docs/fr/1_Reparation_et_Resurrection.md)** | **[📦 Télécharger le projet complet (.zip)](https://github.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/archive/refs/heads/main.zip)**

</div>