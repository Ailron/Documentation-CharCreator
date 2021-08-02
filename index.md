# Presentation

CharCreator is a script under RageUI which reconstructs the GTA ONLINE character creation as closely as possible when when you started Online.

# Dependency

CharCreator is a heavy resource and needs to have some basic dependencies to work for the best experience.

CharCreator will need several dependencies for its work:
- [skinchanger](https://github.com/esx-framework/skinchanger)
- [esx_skin](https://github.com/esx-framework/esx_skin)
- [esx_identity](https://github.com/esx-framework/esx_identity) (optional)

# Setup
After making sure you have installed at least the two mandatory resources, you will need to make some modifications to them for it's working.
### Esx_skin
1. Depending on the version of esx_skin , inside `client/main.lua` , replace line 295 : `TriggerEvent('skinchanger:loadSkin', {sex = 0}, OpenSaveableMenu)` by 
```markdown
TriggerEvent('charcreator:CharCreator')
```
### SkinChanger
1. Depending on the version of Skinchanger you have, inside `client / main.lua` from line 1, you will need to add this part of the code.
**Be careful depending on your version, certain line of this code may already be in your list so check for duplicates** :

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

2. For the clothing category, CharCreator needs to know what are the clothes to add in this category, Always from line 1 to the end of the list you will need to add inside each line mentioned, a variable : `clothe = true` for lines where` name` =
 `'tshirt_1'` , `'tshirt_2'` , `'torso_1'` , `'torso_2'` , `'decals_1'` , `'decals_2'` , `'arms'` , `'arms_2'` , `'pants_1'` , `'pants_2'` , `'shoes_1'` , `'shoes_2'` , `'mask_1'` , `'mask_2'` , `'chain_1'` , `'chain_2'` , `'helmet_1'` , `'helmet_2'` , `'glasses_1'` , `'glasses_2'` , `'watches_1'` , `'watches_2'` , `'bracelets_1'` , `'bracelets_2'` , `'bags_1'` , `'bags_2'`.
 
3. Example : for `'tshirt_1'` , you have to change this :

```markdown
{label = _U('tshirt_1'), name = 'tshirt_1', value = 0, min = 0, zoomOffset = 0.75, camOffset = 0.15, componentId = 8},
```
4. To this :

```markdown
{label = _U('tshirt_1'), name = 'tshirt_1', value = 0, min = 0, zoomOffset = 0.75, camOffset = 0.15, componentId = 8, clothe = true},
```
5. And you will repeat this for everyone you ask.

6. in the function `ApplySkin` , modify the line `SetPedHeadBlendData(playerPed, Character['face'], Character['face'], Character['face'], Character['skin'], Character['skin'], Character['skin'], 1.0, 1.0, 1.0, true)` until the end of the function by :

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
### Esx_identity
1. If you want the identity part in the script , follow this installation.
Depending on the version of esx_identity you have, inside the `server/main.lua`,
Place this piece of code:

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
The `config.lua` file allows you to configure some script parameters without touching the codes to customize the script your way. The inside of the config already explains each configuration and its usefulness.

The file `messages.lua` is the translation of the script in 2 languages: English and French. You can change the translations if you wish, be aware that the translations refer as much as possible to that of the GTA: Online character creation and that some translations have been rephrased for more meaning.

# Crédits
Based on the source of [NicooPasPris](https://github.com/NicooPasPris/nicoo_charcreator)
