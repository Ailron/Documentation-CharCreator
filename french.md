# Présentation

CharCreator est un script sous RageUI reconstituant au plus proche la création de personnage GTA ONLINE lors de son début . 

# Dépendance

CharCreator est une ressource assez lourde et doit posséder quelques dépendances basiques pour fonctionner et avoir la meilleure expérience .

CharCreator aura besoin de plusieurs dépendance pour son fonctionnement :
- [skinchanger](https://github.com/esx-framework/skinchanger)
- [esx_skin](https://github.com/esx-framework/esx_skin)
- [esx_identity](https://github.com/esx-framework/esx_identity) (facultatif)

# Installation
Après être assuré d'avoir installer au moins les deux ressources obligatoires , il vous faudras faire quelques modifications dessus pour que CharCreator fonctionne correctement.

### SkinChanger
1. Selon la version de SkinChanger que vous possédez , à l'intérieur du `client/main.lua` à partir de la ligne 1 , il vous faudra impérativement rajouter cette partie de code . **Attention selon votre version certaine ligne de ce code se situe peut-être déjà dans votre liste vérifiez donc les doublons** :

```markdown
-- CharCreator Section
{label = _U('mother_heritage'), 			name = 'mom',				value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('father_heritage'), 			name = 'dad',				value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('nose_width'),	 			name = 'nose_1',			value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('nose_height'), 				name = 'nose_2',			value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('nose_peak'), 				name = 'nose_3',			value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('nose_bone'), 				name = 'nose_4',			value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('nose_peak_2'), 				name = 'nose_5',			value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('nose'), 					name = 'nose_6',			value = 0.0,	min = 0,	zoomOffset = 0.6,		camOffset = 0.65},
{label = _U('eyebrows_depth'),				name = 'eyebrows_5',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('eyebrows_height'),				name = 'eyebrows_6',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('cheekbones_height'), 			name = 'cheeks_1',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('cheekbones_width'),			name = 'cheeks_2',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('cheek_width'),				name = 'cheeks_3',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('opening_eyes'),				name = 'eye_open',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('lips_thick'),				name = 'lips_thick',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('jaw_width'),				name = 'jaw_1',				value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('jaw_length'),				name = 'jaw_2',				value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('chin_height'),				name = 'chin_height',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('chin_lenght'),				name = 'chin_lenght',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('chin_width'),				name = 'chin_width',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('chin_hole'),				name = 'chin_hole',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
{label = _U('neck_thick'),				name = 'neck_thick',			value = 0.0,	min = 0,	zoomOffset = 0.4,		camOffset = 0.65},
```

2. Pour la catégorie vêtements , CharCreator a besoin de savoir quelles sont les vêtements à ajouter dans cette catégories , Toujours à partir de la ligne 1 jusqu'à la fin de la liste il vous faudras ajouter à l'intérieur de la ligne une variable : `clothe = true` pour les ligne où `name` =
 `'tshirt_1'` , `'tshirt_2'` , `'torso_1'` , `'torso_2'` , `'decals_1'` , `'decals_2'` , `'arms'` , `'arms_2'` , `'pants_1'` , `'pants_2'` , `'shoes_1'` , `'shoes_2'` , `'mask_1'` , `'mask_2'` , `'chain_1'` , `'chain_2'` , `'helmet_1'` , `'helmet_2'` , `'glasses_1'` , `'glasses_2'` , `'watches_1'` , `'watches_2'` , `'bracelets_1'` , `'bracelets_2'` , `'bags_1'` , `'bags_2'`.
 
Exemple : pour `'tshirt_1'` vous passerez de cela :
```markdown
{label = _U('tshirt_1'), name = 'tshirt_1', value = 0, min = 0, zoomOffset = 0.75, camOffset = 0.15, componentId = 8},
```
A cela :
```markdown
{label = _U('tshirt_1'), name = 'tshirt_1', value = 0, min = 0, zoomOffset = 0.75, camOffset = 0.15, componentId = 8, clothe = true},
```
Et vous répéterez cela pour tous ce qui vous sont demandez .
```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Ailron/Documentation-CharCreator/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

