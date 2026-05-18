# Lasagne dumpling - culinary and visual research decisions

## 1. Sous-recettes et dependances

- **Farce porc-shiitake aromatique**: porc hache maigre, shiitakes haches finement, oignons verts, gingembre, ail, soya, hoisin, vinaigre de riz, sambal oelek, huile de sesame grillee. Elle doit devenir une farce crue collante, brillante et tartinable avant tout montage.
- **Moule carre huile**: moule compact de 8 po / 20 cm. L'huile doit etre visible comme film fin, pas comme bain d'huile.
- **Montage facon lasagne de dumplings**: alterner farce tres mince et pates a dumplings plates; finir par les pates. Les wrappers doivent rester plats, tuiles ou chevauches, jamais plies en dumplings individuels.
- **Hydratation et cuisson vapeur**: ajouter seulement 3 c. soupe d'eau dans le moule; placer le moule dans une grande casserole avec eau chaude a mi-hauteur a l'exterieur du moule; cuire couvert 25 min. La vapeur cuit le porc et hydrate les wrappers.
- **Finition**: sauce soya, oignon vert cisele, sesame blanc seulement apres cuisson, sur surface chaude, pale, brillante et vapeur.

Ordre reel contraignant: farce et moule avant montage; montage avant eau; eau + bain vapeur avant garniture; garniture apres cuisson.

## 2. Transformations fragiles

- Farce friable -> farce collante brillante: elle doit coller a la cuillere/spatule, avec flecks de shiitake, vert d'oignon et rouge de sambal.
- Wrapper cru pale -> feuille tendre translucide: le risque majeur est que le modele invente des nouilles de lasagne, tortillas, raviolis ou dumplings plies.
- Porc cru -> couches cuites juteuses: cuisson vapeur sans brunissement; viser beige opaque, humide, jamais rose cru ni gris sec.
- Bain vapeur -> reveal: garder le moule carre visible et l'eau a l'exterieur; eviter l'effet soupe ou bouillonnement dans le moule.
- Surface pale -> hero glossy: soya en rubans fins, vapeur, sesame blanc et oignon vert; eviter une surface noyee ou boueuse.

## 3. Opportunites texture / hook

- Hook le plus sexy: macro de sauce soya qui glisse sur le dessus vapeur et translucide, puis coupe rapide qui clarifie le moule carre.
- Alternative plus process: farce porc-shiitake brillante et sticky etalee tres mince, suivie des wrappers qui tombent comme des feuilles souples.
- Payoffs desirables: lid lift avec condensation; seam des wrappers qui gonfle; spatula lift d'un coin carre avec couches horizontales; pluie de sesame et scallion; jus sombre qui perle sur la tranche.
- ASMR utile: slap humide de farce, frottement de spatule, wrapper flasque qui se pose, petit splash des 3 c. soupe d'eau, souffle vapeur, drizzle soya, pluie seche de sesame.

## 4. Risques de scale / geometrie

- Moule: 8 po / 20 cm carre, 4 portions; pas grand plat familial, pas ramequins.
- Wrappers: environ 20 pates a dumplings palm-size, plates, tuiles/chevauchees; pas de pliage, pas de scellage, pas de paquets individuels.
- Couches: farce mince 3-5 mm par couche, pas patties de viande.
- Hauteur finale: slab vapeur compact d'environ 3-5 cm, portion carree autour de 9-10 cm si coupee en quatre.
- Identite culinaire: aucune tomate, aucun fromage, aucun cheese pull, aucune nouille longue de lasagne.
- Eau: seulement 3 c. soupe dans le moule; eau chaude a mi-hauteur a l'exterieur du moule dans la casserole.
- Garniture: 2-3 pincees visibles d'oignon vert fin + leger sesame, pas morceaux geants ni poussiere invisible.

Questions qui changent vraiment la video:

- Wrappers ronds ou carres?
- Portion finale en quatre carres nets ou service plus scoop/juteux?
- Moule glass/ceramique/metal, ou acceptation de l'asset BakingDish comme reference de forme?

## 5. Recommandations de references specifiques minimales

Assets existants a privilegier:

- `@KitchenLayoutContextWide`: continuite structurelle de cuisine.
- `@KitchenIslandOverhead`: mixing, huilage, montage en couches.
- `@KitchenIslandDefault`: identite ilot / hero final.
- `@InductionWide` + option `@InductionCloseup`: cuisson vapeur en casserole couverte.
- `@CharacterSheet`, `@PoseTopDown`, option `@PoseThreeQuarterRight`: identite Licorn, mains de montage, satisfaction finale.
- `@BakingDish`: moule carre / plat de cuisson.
- `@Spoon`, `@Spatula`, option `@Tongs`, `@SaucepanLarge`: farce, drizzle, etalage, wrappers, casserole.

Reference recette generee minimale:

- **Conditionnelle seulement**: `@FinishedDumplingLasagnaCutaway`, une reference finale/cutaway si le storyboard exige une portion soulevee avec couches lisibles. C'est la seule reference non-asset recommandee, car le plat peut deriver vers dumplings individuels ou lasagne occidentale.

A ne pas creer maintenant:

- Pas de reference farce crue.
- Pas de reference montage wrappers.
- Pas de reference intermediaire vapeur sauf si la generation perd le moule carre ou transforme l'eau en soupe.
