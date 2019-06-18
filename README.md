# Hi
Hey, im Schokokeksrepublik, if you want some features, if you find a bug, let me know (on Github or Steam).


# Whats new
First of all, after some crashing and so on, i started everything from Scratch again. New stuff is:
Timers, Talents, example Modifier, example Ability, Startitems, Thinker, so basically the files you find inside game/dota_addons/addon_template_butt/scripts/vscripts/.

# Startitems
Lets you add free Items, Abilities, Talents or Modifiers, that everyone gets.

# Thinker
Events that trigger at a Timer. Give free Rapiers after 20 Minutes or teleport everyone to the midlane (hero:SetAbsOrigin(Vector(0,0,120))) every 5 Minutes.

# Talents
If you want to add a new Talents, you have to add it to the game/..../scripts/npc/npc_abilites_custom.txt , and create a file in game/..../scripts/vscripts/talents/ as like the example talent.

# Abilities
If you want to add a new Ability, you can give it to every hero in the 

# Modifiers
Modifiers are Buffs or Debuffs. The advantage of Modifiers is, that you dont have to edit the KV files, they are only in lua. To use them you have to use LinkLuaModifier(name, filepath, LUA_MODIFIER_MOTION_NONE) and then you can add them to the heroes or so.
You can add them to some events, like entity_spawned, entity_killed, or so. Modifiers have a little odd thing, that they technically exist twice, once on the players computer and once on the server, thats maybe good to keep in mind.
Modifiers can do stuff on a lot of events, found in the API. Most of the events are triggered on the whole map, not only the hero. For that you have to add the CONSTANT in DeclareFunctions and add the function also to the .lua file.

# Settings
The Loadscreen settings. Feel free to balance your game here.

# Lua Tipps
-- This is a comment (not Code)

If you have a typo in a file, the whole file turns useless.

If you have a function, e.g. function examplemodifier:OnAttackLanded(event), you can read the whole event on the console using:
"for k,v in pairs(event) do print("OnAttackLanded:",k,v) end"
Sometimes events might miss a value (like event.attacker).
The console can be opened in Dota (depending on your key assignment) or from asset browser. Filter for "VScript".

Arrays (or tables as they are called in lua) usually start with 1, but some Dota Stuff, like PlayerIDs start with 0, since they originally come from the C++ hardcode of Dota.

If a variable has no value, it is "nil" and is like false. (So you can do "if (test) then..." instead of "if (test~=nil)").

This "hero:GetLevel()" equals to "hero.GetLevel(hero)". "if (hero.GetLevel) then test = hero:GetLevel()" can be used to ensure this function exists.

# Links
Lua API : https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools/Scripting/API
(Important Sections: CDOTA_BaseNPC, CDOTA_BaseNPC_Hero, PlayerResource and the very Bottom with the CONSTANTS)
