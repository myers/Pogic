# Pogic TODO

* don't reinvent the wheel on client side API.  Talk with the MCP guys and the ModLoader guys.  Work together
* Why can't overlord spawn other creatures?
* have overlord print out a list of creatures it can spawn when you do /spawn with no args
* figure out how to do new skins
* figure out how to do new sounds
* put all the mods in the same class loader
* unload all the mod classes on server disconnect
* use the sha2 hash to figure out if we already have the file
* get some folks to review the sandboxing in the client mod
* allow the client with the mod installed to connect to vanilla smp servers too
* obfuscate the client mod, and the sample client mod so we can install in vanilla minecraft client
* mod download progress screen
* allow the http server to be turned off (in server.properites)
* allow the http server to have another port than 8081 (in server.properites)
* allow the http url where the client mods can be found to be set (in server.properites)
* have the client mod jar file embedded in the server side plugin for easy of installation
* sandbox the client mod code even more.  It should only be able to make a limited number of calls on the client.
* add support for new blocks
* add support for new items
* add support for new dialog boxes (like the inventory dialog box)
* add support for new on screen display items
* add support for forcing texture packs
