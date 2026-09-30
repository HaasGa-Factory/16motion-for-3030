# Adaptation 3030 — prototype mesuré

Cette variante du projet [mosomate/16motion](https://github.com/mosomate/16motion) conserve le modèle paramétrique de l'auteur et ses dimensions de quincaillerie. Elle est adaptée à **un profilé mesuré à 29,83 × 29,95 mm**, pas à tous les profilés 3030.

![Coulissement du chariot](demonstration_client/Coulissement_3030_sans_texte.gif)

## Pièces à imprimer

| Pièce | Quantité | STL | Modèle paramétrique |
|---|---:|---|---|
| Plaque X, largeur réelle 29,83 mm | 2 | [STL X](mesures_2983_2995/Plaque_X_2983.stl) | [FreeCAD X](mesures_2983_2995/Plaque_X_2983.FCStd) |
| Plaque Y, largeur réelle 29,95 mm | 2 | [STL Y](mesures_2983_2995/Plaque_Y_2995.stl) | [FreeCAD Y](mesures_2983_2995/Plaque_Y_2995.FCStd) |
| Entretoise commune | 16 | [STL](mesures_2983_2995/Entretoise.stl) | Objet Spacer dans les modèles ci-dessus |

STL en millimètres, à imprimer à 100 %. Déviation de surface 0,1 mm et angulaire 5°. Aucun STL n'a subi de mise à l'échelle globale. Ne pas imprimer quatre fois la même variante de plaque.

## Projet Bambu Studio prêt à trancher

Le fichier [plaqueXY-entretoise.3mf](../Bambustudio/plaqueXY-entretoise.3mf) regroupe toutes les pièces nécessaires :

- **plateau 1** : 2 plaques X et 2 plaques Y ;
- **plateau 2** : 17 entretoises, dont 16 pour le montage et 1 de secours.

Réglages enregistrés dans le projet : **Bambu Lab H2S**, buse **0,4 mm**, couches de **0,20 mm**, **PETG**, deux parois, remplissage grille à 15 %, supports arborescents automatiques limités au plateau et plateau PEI texturé.

Le 3MF contient la disposition des pièces et les paramètres de tranchage, mais pas un G-code universel. Avant impression, choisir dans Bambu Studio l'imprimante, la buse, le plateau et le filament réellement installés, relancer le tranchage puis vérifier chaque couche dans l'aperçu. Sur une autre imprimante, conserver les géométries et adapter les vitesses, températures, refroidissement et supports au matériel utilisé.

## Montage et quincaillerie

La [notice en français](mesures_2983_2995/NOTICE_FR.md) précise les paramètres, l'orientation des plaques et le réglage de précharge. Pour un chariot : 16 roulements 684 (4 × 9 × 4 mm), 8 vis M4 × 40 mm, 8 vis M3 × 16 mm et 8 écrous M3 autofreinés. Les avant-trous fixes des plaques sont à tarauder M4 ; les fixations d'accessoires sont supplémentaires.

[Assemblage FreeCAD](mesures_2983_2995/Assemblage_mesure.FCStd) · [Vue éclatée FreeCAD](mesures_2983_2995/Eclate_mesure.FCStd) · [Image éclatée](mesures_2983_2995/Eclate_mesure.png)

## Démonstration du coulissement

[GIF sans texte](demonstration_client/Coulissement_3030_sans_texte.gif) · [Scène FreeCAD](demonstration_client/Demonstration_3030.FCStd) · [Macro](demonstration_client/Demonstration_3030.FCMacro)

Le GIF montre une course illustrative de 180 mm sur un rail de 320 mm. Pour déplacer la scène FreeCAD, modifier `Commande.Position` entre −90 et +90 mm. La macro s'exécute dans FreeCAD et charge l'assemblage du dossier voisin ; conserver cette arborescence. Elle propose lecture/pause, curseur et transparence des plaques. Les modèles de fabrication ne sont pas modifiés.

## Vérifications et limites

Les rapports [du prototype](mesures_2983_2995/verification_mesures.json) et [de l'animation](demonstration_client/verification.json) consignent les contrôles réalisés dans FreeCAD 1.1.3 : recalculs, géométrie, fermeture et dimensions des maillages, positions de présentation.

Le rail est une enveloppe rectangulaire simplifiée : coins et rainures ne sont pas modélisés. L'appui des roulements sur les plats est partiel. La précharge nécessite un réglage réel ; les interférences de la pose rigide sont expliquées dans la notice. L'animation impose la translation et ne simule ni rotation des roulements, ni frottements, ni déformations, ni capacité de charge. Le coulissement et la tenue mécanique restent à vérifier sur un premier montage imprimé et sur toute sa course.

## Origine et licence

Conception originale : **mosomate / 16motion**. Modifications de cette variante : valeurs du tableur pour les deux paires, exports STL, présentations d'assemblage, animation et documentation. Le `Plate.FCStd` original reste inchangé à la racine.

Licence originale **CC BY-NC 4.0**, conservée dans [LICENSE](../LICENSE). La clause non commerciale s'applique ; cette adaptation n'accorde pas de droits supplémentaires.
