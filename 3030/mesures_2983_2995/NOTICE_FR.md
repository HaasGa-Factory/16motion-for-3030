# 16motion adapté à 29,83 × 29,95 mm — prototype

Cette variante utilise les mesures du profilé du prototype : **X = 29,83 mm, Y = 29,95 mm**, ouverture G = 8,07 mm et plats P gauche/droite = 8,17 mm. Aucun calcul de moyenne entre X et Y. L'appui partiel des roulements sur les plats est conservé pour ce prototype.

## Fichiers à utiliser et quantités

| Pièce | Modèle paramétrique | STL | Quantité |
|---|---|---|---:|
| Paire X | `Plaque_X_2983.FCStd` | `Plaque_X_2983.stl` | **2** |
| Paire Y | `Plaque_Y_2995.FCStd` | `Plaque_Y_2995.stl` | **2** |
| Entretoise commune | Objet Spacer dans les deux modèles | `Entretoise.stl` | **16 au total** |

Ne pas imprimer quatre fois la même plaque et ne pas mélanger avec les STL nominaux 30/30 du modèle nominal. Marquer X ou Y au feutre sur les impressions pour les distinguer. Les petites différences se voient difficilement à l'œil.

`Assemblage_mesure.FCStd` contient les quatre plaques, 16 roulements, 16 entretoises, huit tiges M4 et huit tiges M3 de réglage. `Eclate_mesure.FCStd` s'ouvre directement dans la vue éclatée. Ces présentations utilisent des copies et liens internes, à régénérer après modification des modèles maîtres.

## Orientation des deux paires

Repère des mesures de section : **X** est la distance de 29,83 mm entre faces gauche/droite ; **Y** la distance de 29,95 mm entre faces haut/bas.

- Les deux **plaques X** se montent sur les côtés **haut et bas** ; leurs roulements roulent sur les faces gauche/droite, écartées de X.
- Les deux **plaques Y** se montent sur les côtés **gauche et droit** ; leurs roulements roulent sur les faces haut/bas, écartées de Y.

La lettre indique donc la dimension contrôlée par les roulements, et non la normale à la plaque. Dans FreeCAD, l'axe longitudinal du rail s'appelle aussi X : ce repère CAO est distinct de celui des mesures de section. Les étiquettes des plaques dans l'arbre reprennent les lettres des photos.

## Paramètres et fidélité au modèle

Dans `Spreadsheet`, **B3 (Ideal extrusion width) reste à 30 mm** sur les deux variantes. **B4 (Actual extrusion width) vaut 29,83 mm pour X et 29,95 mm pour Y**. B1 = 0,1 mm de compensation d'impression, B6 = 4 mm et B7 = 5 mm sont inchangés. Les 204 objets, les expressions, les logements et les leviers de l'auteur sont conservés. Seules les valeurs du tableur, les annotations et l'affichage changent.

Les plans d'emboîtement restent à 16 mm du centre, selon le paramétrage nominal du modèle. Les axes fixes sont à B4/2 + 4,45 mm et les axes réglables à B4/2 + 4,7 mm. Les positions des roulements et des vis de présentation suivent ces valeurs pour chaque paire. La visserie et les entretoises ne sont pas mises à l'échelle.

STL : **mm**, échelle 100 %, déviation de surface **0,1 mm**, angulaire **5°**, non relative. Maillages réimportés et comparés aux dimensions des solides ; détails dans `verification_mesures.json`. Les deux pièces sont visibles dans chaque modèle, l'entretoise étant décalée à X = 58 mm pour l'affichage seulement. Les STL sont exportés avant ce décalage.

## Quincaillerie et montage

Pour le chariot complet : **16 roulements 684 (4 × 9 × 4 mm), 8 vis M4 × 40 mm, 8 vis M3 × 16 mm et 8 écrous M3 autofreinés**, plus les fixations propres aux accessoires. Matériau conseillé par l'auteur : PETG, supports depuis le plateau. Les têtes/filets et écrous ne sont pas détaillés dans la présentation.

1. Ébavurer les pièces et dégager les fentes des leviers sans amincir leurs charnières.
2. Tarauder M4 les deux avant-trous fixes Ø3,7 mm en diagonale sur chaque plaque ; conserver les passages Ø4,2 mm.
3. Installer les écrous M3 et les vis de réglage au simple contact, sans précharger.
4. Emboîter les deux paires dans l'orientation indiquée. Ajouter les couples entretoise/roulement sur les axes M4, relief de l'entretoise tourné vers le roulement. Ne pas forcer les axes désalignés ; serrer sans écraser le plastique.
5. Vérifier que les bagues extérieures tournent librement, engager sur l'extrémité ébavurée du profilé puis régler progressivement par paires. Garder un coulissement libre sur la course entière. Selon le critère de l'auteur, le chariot doit encore descendre sous son poids sur un profilé vertical ; le retenir à la main.

## Appui partiel accepté et limites du prototype

Les K calculés valent **2,71 mm pour une face large de X** et **2,77 mm pour une face large de Y**, sous l'hypothèse de coins symétriques et des mêmes G/P sur les faces concernées. Ce ne sont pas des rayons certifiés. Avec les dimensions mesurées et l'empilement de cette présentation, la largeur projetée du roulement au-dessus du vrai plat est estimée à **environ 3,21 mm sur 4 mm**. Il s'agit d'un recouvrement géométrique, pas d'une mesure de la surface de contact sous charge.

Le rail reste une enveloppe rectangulaire de **29,83 × 29,95 mm**. La forme exacte des coins et l'intérieur des rainures n'ont pas été inventés. Les roulements fixes (objets `Roulement684_i_2` et `Roulement684_i_3`, i = 0 à 3) présentent toujours 0,05 mm de pénétration théorique dans cette enveloppe, tandis que les réglables ont 0,20 mm de jeu. Le décalage d'axes de 0,25 mm au repos nécessite déplacement et/ou inclinaison au montage. Les intersections avec les tiges simplifiées sont consignées, et les intersections M4/avant-trou doivent être distinguées du taraudage non représenté.

Les contrôles CAO vérifient solides, recalculs, maillages et interférences de la pose rigide. Ils ne simulent pas les déformations, le réglage de précharge, la charge admissible ou l'usure. Vérifier sur ce premier montage : rotation, absence de blocage et de jeu, appuis, alignement, tenue des taraudages, absence de fissure des leviers et de marques excessives sur l'aluminium. Les mesures le long de toute la course n'ont pas été fournies ; le coulissement reste donc à vérifier sur cette longueur.

Source : **mosomate / 16motion**, https://github.com/mosomate/16motion — licence **CC BY-NC 4.0**. Le modèle original est conservé à la racine du dépôt. Pour reproduire les variantes, ouvrir une copie de `Plate.FCStd`, régler B3 à 30 mm et B4 à 29,83 mm (paire X) ou 29,95 mm (paire Y), puis recalculer le tableur, Plate, Spacer et Assets. Exporter Plate et Spacer avec les réglages de maillage indiqués ci-dessus. Les documents de présentation sont des copies de formes et doivent être actualisés séparément après toute modification.
