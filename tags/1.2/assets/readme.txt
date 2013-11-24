=========================
WEAPONS OF FURY: RELOADED
=========================

version 1.2 - 01 nov 2013



Introduction
------------

Weapons of Fury: Reloaded is a mod for the game Quake III Arena. The gameplay idea is based on the Weapons of Fury mod that was released for Quake 3 ages ago. However, this mod has fallen off the face of the Internets, never to be heard of again. Weapons of Fury: Reloaded aims to recreate the Weapons of Fury experience and add a slew of additional features.

This mod changes the rules of Quake 3 a bit. There are no weapons or ammo boxes in the map and everybody spawns with a Rocket Launcher with unlimited ammo. Whenever you make a frag, you're awarded a Plasmagun that will replace your Rocket Launcher. Making a frag with the Plasmagun awards you a Shotgun, and so on. Whenever you make a frag with the last weapon, the BFG, you are awarded 10 points instead of one.

The catch, however, is that whenever you are fragged, you spawn again with the Rocket Launcher and you have to start all over again. The default weapon order is as follows: RL -> PG -> SG -> LG -> RG -> GL -> MG -> BFG. However, server administrators can modify this weapon order.



Installation
------------
Simply unzip the files from this ZIP package into your Quake 3 folder. The result should be a wofreloaded folder inside your Quake 3 installation folder with pak0.pk3 in it. To load the mod, start Quake 3 from the command line like this:

quake3.exe +set fs_game wofreloaded



For server administrators
-------------------------

WoF:R features a number of new cvars that can be used to tweak the progress of the game.
To change the order in which weapons are awarded, use the g_weaponOrder1, g_weaponOrder2, g_weaponOrder3, ..., g_weaponOrder9 cvars. Assign the value for each weapon to them:

set g_weaponOrder1 "5"
set g_weaponOrder2 "8"
set g_weaponOrder3 "3"
set g_weaponOrder4 "6"
set g_weaponOrder5 "7"
set g_weaponOrder6 "4"
set g_weaponOrder7 "2"
set g_weaponOrder8 "9"
set g_weaponOrder9 ""

To clear a weapon from the weapon order, assign "" to that cvar. Gaps are allowed in the weapon order and you do not have to  use all the weapons and one weapon may appear more than once. For instance, the following setup is valid:

set g_weaponOrder1 "3"
set g_weaponOrder2 "7"
set g_weaponOrder3 "5"
set g_weaponOrder4 "9"
set g_weaponOrder5 ""
set g_weaponOrder6 "4"
set g_weaponOrder7 ""
set g_weaponOrder8 "5"
set g_weaponOrder9 ""

In the example above, players will progress from SG -> RG -> RL -> BFG -> GL -> RL.

The default weapon order can be restored by typing \exec wofreloaded_default.cfg in the console.
Additionally, the amount of points that are awarded for making a frag with the last weapon in the weapon order can be set through g_lastWeaponPoints. The default value is 10.



Advanced scoring system
-----------------------

Weapons of Fury: Reloaded features an optional advanced scoring system. This is enabled by setting the g_enableAdvancedScoring cvar to "1".
When advanced scoring is enabled, the number of points awarded to the player making the frag can be configured per weapon order slot, using the g_weaponPoints1, g_weaponPoints2, g_weaponPoints3, ..., g_weaponPoints9 cvars. The g_lastWeaponPoints cvar is ignored when advanced scoring is enabled.

For instance, take the following configuration on top of the default weapon order:

set g_enabledAdvancedScoring "1"
set g_weaponPoints1 "1"
set g_weaponPoints2 "2"
set g_weaponPoints3 "3"
set g_weaponPoints4 "4"
set g_weaponPoints5 "5"
set g_weaponPoints6 "6"
set g_weaponPoints7 "7"
set g_weaponPoints8 "20"

Each consecutive frag will now award the player one more point than the previous frag. A frag with the last weapon, the BFG, will award 20 points. This system allows the system administrator to more carefully balance the game.

The above configuration can instantly be set by typing \exec wofreloaded_advanced.cfg in the console
Note that the default points progression for advanced scoring is configured to be identical to the non-advanced system. Thus awarding 1 point for each frag, except for the BFG, which awards 10 points.



Contact
-------
Contact at eraesr@gmail.com
or go to http://www.theenginesofcreation.com



Change history
--------------
1.2 (01 nov 2013)
    - Fixed issue with g_weaponOrder variables not being read correctly.

1.1 (12 nov 2010)
    - Players are now awarded a 'killstreak' award when scoring a frag with the last weapon
    - Added new advanced scoring system
    - Renamed defaultweaponorder.cfg to wofreloaded_default.cfg and added wofreloaded_advanced.cfg

1.0.1 
    - Fixed a bug where reaching the last weapon would broadcast the wrong weapon name to other players.
    - Scoring a frag with the last weapon broadcasts this to other players.
    - Getting fragged while carrying the last weapon broadcasts this to other players.

1.0 
    - Initial release



License
-------
This mod and it's sourcecode is released under the GNU General Public License v3. It's sourcecode is available on http://code.google.com/p/wofreloaded