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
### Esx_skin
1.Selon la version de esx_skin , à l'intérieur de `client/main.lua` , remplacer la ligne 295 : `TriggerEvent('skinchanger:loadSkin', {sex = 0}, OpenSaveableMenu)` par 
```markdown
TriggerEvent('charcreator:CharCreator')
```
### SkinChanger
1. Selon la version de Skinchanger que vous possédez , à l'intérieur du `client/main.lua` à partir de la ligne 1 , il vous faudra impérativement rajouter cette partie de code . **Attention selon votre version certaine ligne de ce code se situe peut-être déjà dans votre liste vérifiez donc les doublons** :

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

2. Pour la catégorie vêtements , CharCreator a besoin de savoir quelles sont les vêtements à ajouter dans cette catégories , Toujours à partir de la ligne 1 jusqu'à la fin de la liste il vous faudras ajouter à l'intérieur de chaque ligne mentionnée, une variable : `clothe = true` pour les lignes où `name` =
 `'tshirt_1'` , `'tshirt_2'` , `'torso_1'` , `'torso_2'` , `'decals_1'` , `'decals_2'` , `'arms'` , `'arms_2'` , `'pants_1'` , `'pants_2'` , `'shoes_1'` , `'shoes_2'` , `'mask_1'` , `'mask_2'` , `'chain_1'` , `'chain_2'` , `'helmet_1'` , `'helmet_2'` , `'glasses_1'` , `'glasses_2'` , `'watches_1'` , `'watches_2'` , `'bracelets_1'` , `'bracelets_2'` , `'bags_1'` , `'bags_2'`.
 
3. Exemple : pour `'tshirt_1'` vous passerez de cela :

```markdown
{label = _U('tshirt_1'), name = 'tshirt_1', value = 0, min = 0, zoomOffset = 0.75, camOffset = 0.15, componentId = 8},
```
4. A cela :

```markdown
{label = _U('tshirt_1'), name = 'tshirt_1', value = 0, min = 0, zoomOffset = 0.75, camOffset = 0.15, componentId = 8, clothe = true},
```
5. Et vous répéterez cela pour tous ceux qui vous sont demandez .

6. Dans la fonction `ApplySkin` , modifiez la ligne `SetPedHeadBlendData(playerPed, Character['face'], Character['face'], Character['face'], Character['skin'], Character['skin'], Character['skin'], 1.0, 1.0, 1.0, true)` jusqu'à la fin de la fonction par :

```markdown
SetPedHeadBlendData(playerPed, Character['mom'], Character['dad'], nil, Character['mom'], Character['dad'], nil, Character['face'], Character['skin'], nil, true)

local Face = {[0] = 'nose_1', [1] = 'nose_2', [2] = 'nose_3', [3] = 'nose_4', [4] = 'nose_5', [5] = 'nose_6', [6] = 'eyebrows_5', [7] = 'eyebrows_6', [8] = 'cheeks_2', [9] = 'cheeks_1', [10] = 'cheeks_3', [11] = 'eye_open', [12] = 'lips_thick', [13] = 'jaw_1', [14] = 'jaw_2', [15] = 'chin_height', [16] = 'chin_lenght', [17] = 'chin_width', [18] = 'chin_hole', [19] = 'neck_thick'}

for k,v in pairs(Face) do
	if Character[v] then
		SetPedFaceFeature(GetPlayerPed(-1), k, Character[v])
	end
end

SetPedHeadOverlay(playerPed, 		3, 	Character['age_1'],  (Character['age_2'] / 10) + 0.0) 				-- Age + opacity
SetPedHeadOverlay(playerPed, 		1, 	Character['beard_1'],  (Character['beard_2'] / 10) + 0.0) 			-- Beard + opacity
SetPedHeadOverlayColor(playerPed, 	1, 	1, Character['beard_3'],  Character['beard_4'])     				-- Beard Color
SetPedHeadOverlay(playerPed, 		2,  	Character['eyebrows_1'], (Character['eyebrows_2'] / 10) + 0.0) 			-- Eyebrows + opacity
SetPedHeadOverlayColor(playerPed,  	2,  	1,  Character['eyebrows_3'],  Character['eyebrows_4'])				-- Eyebrows Color
SetPedHeadOverlay(playerPed, 		4,  	Character['makeup_1'], (Character['makeup_2'] / 10) + 0.0) 			-- Makeup + opacity
SetPedHeadOverlayColor(playerPed,  	4,  	1,  Character['makeup_3'],  Character['makeup_4'])				-- Makeup Color
SetPedHeadOverlay(playerPed,  		8,  	Character['lipstick_1'], (Character['lipstick_2'] / 10) + 0.0)			-- Lipstick + opacity
SetPedHeadOverlayColor(playerPed,  	8,  	1,  Character['lipstick_3'],  Character['lipstick_4'])				-- Lipstick Color
SetPedComponentVariation(playerPed, 	2, 	Character['hair_1'], Character['hair_2'], 2)	      				-- Hair
SetPedHairColor(playerPed, 		Character['hair_color_1'], Character['hair_color_2']) 		    			-- Hair Color
SetPedEyeColor(playerPed, 		Character['eye_color'], Character['eye_color']) 					-- Eyes Color
SetPedHeadOverlay(playerPed, 		5,	Character['blush_1'], (Character['blush_2'] / 10) + 0.0)			-- Blush + opacity
SetPedHeadOverlayColor(playerPed, 	5, 	1,   Character['blush_3'])							-- Blush Color
SetPedHeadOverlay(playerPed, 0,		Character['blemishes_1'], (Character['blemishes_2'] / 10) + 0.0)			-- Body Blemishes + opacity
SetPedHeadOverlay(playerPed, 		6,	Character['complexion_1'], (Character['complexion_2'] / 10) + 0.0)		-- Complexion + opacity
SetPedHeadOverlay(playerPed, 		7,	Character['sun_1'], (Character['sun_2'] / 10) + 0.0)				-- Sun Damage + opacity
SetPedHeadOverlay(playerPed, 		9,	Character['moles_1'], (Character['moles_2'] / 10) + 0.0)			-- Moles/Freckles + opacity
SetPedHeadOverlay(playerPed, 		10,	Character['chest_1'], (Character['chest_2'] / 10) + 0.0)			-- Chest Hair + opacity
SetPedHeadOverlayColor(playerPed, 	10, 	1,	Character['chest_3'])							-- Torso Color
SetPedHeadOverlay(playerPed, 		11,	Character['bodyb_1'], (Character['bodyb_2'] / 10) + 0.0)			-- Body Blemishes + opacity


if Character['ears_1'] == -1 then
	ClearPedProp(playerPed,  2)
else
	SetPedPropIndex(playerPed, 2, 			Character['ears_1'], Character['ears_2'], 2)               			-- Ears Accessories
end

SetPedComponentVariation(playerPed, 8,  	Character['tshirt_1'],Character['tshirt_2'], 2)     				-- Tshirt
SetPedComponentVariation(playerPed, 11, 	Character['torso_1'], Character['torso_2'], 2)      				-- torso parts
SetPedComponentVariation(playerPed, 3, 		Character['arms'], 0, 2)                             				-- torso
SetPedComponentVariation(playerPed, 10, 	Character['decals_1'], Character['decals_2'], 2)    				-- decals
SetPedComponentVariation(playerPed, 4, 		Character['pants_1'], Character['pants_2'], 2)       				-- pants
SetPedComponentVariation(playerPed, 6, 		Character['shoes_1'], Character['shoes_2'], 2)       				-- shoes
SetPedComponentVariation(playerPed, 1, 		Character['mask_1'], Character['mask_2'], 2) 						-- mask
SetPedComponentVariation(playerPed, 9, 		Character['bproof_1'], Character['bproof_2'], 2) 					-- bulletproof
SetPedComponentVariation(playerPed, 7, 		Character['chain_1'], Character['chain_2'], 2) 	    				-- chain
SetPedComponentVariation(playerPed, 5, 		Character['bags_1'], Character['bags_2'], 2) 						-- Bag

if Character['helmet_1'] == -1 then
	ClearPedProp(playerPed,  0)
else
	SetPedPropIndex(playerPed, 0, Character['helmet_1'], Character['helmet_2'], 2)              				-- Helmet
end

if Character['watches_1'] == -1 then
	ClearPedProp(playerPed,  6)
else
	SetPedPropIndex(playerPed, 6, Character['watches_1'], Character['watches_2'], 2)   
end

if Character['bracelets_1'] == -1 then
	ClearPedProp(playerPed,  7)
else
	SetPedPropIndex(playerPed, 7, Character['bracelets_1'], Character['bracelets_2'], 2)   
end

SetPedPropIndex(playerPed, 1, Character['glasses_1'], Character['glasses_2'], 2) 								-- Glasses

```
### Esx_identity (optionnelle)
1. Si vous avez installé esx_identity et vous souhaitez la partie identité du script alors suivez cette installation .
Selon la version de esx_identity que vous possédez , à l'intérieur du `server/main.lua` ,
PLacez ce morceau de code :

```markdown
RegisterNetEvent('esx_identity:checkidentity')
AddEventHandler('esx_identity:checkidentity', function(value,check)
	-- print('lancé')
	local identity = false
	if check == "name" then
		identity = checkNameFormat(value)
	elseif check == "dob" then
		identity = checkDOBFormat(value)
	elseif check == "sex" then
		identity = checkSexFormat(value)
	elseif check == "height" then
		identity = checkHeightFormat(value)
	end

	TriggerClientEvent('charcreator:receivecheck', source, identity)
end)
```
# Configuration
Le fichier `config.lua` permet de configurer quelques paramètres du script sans toucher au codes pour personnaliser le script à votre façon . L'intérieur du config vous explique déjà chaque configuration et son utilité .

Le fichier `messages.lua` est la traduction du script sous 2 langues : Anglais et Français . Vous pouvez si vous le souhaitez modifiez les traductions , sachez que les traductions se réfèrent le plus possible à celui de la création de personnage GTA:Online et que certaines traductions ont été reformuler pour plus de sens .

# Crédits
Basé sur la ressource de [NicooPasPris](https://github.com/NicooPasPris/nicoo_charcreator)
