# Pogic

This is a Minecraft Client Side Mod that will download other client mods as
requested by a server.  Using this you can add new creatures to your SMP
server.

The client side mods are run in a Java sandbox keeping your computer safe
from evil servers out there.

## Prerelease Demo Video

http://www.youtube.com/watch?v=uftHwJFKyzo

## Release Status

*THIS MOD IS NOT READY FOR USE*

That said, if you are a developer, and know how to use git, eclipse, mvn, ant,
patch, and the [Minecraft Coder Pack][mcp] you can try this out on your own
computer.

There are hard coded assumptions that you the server is on "localhost" and
that port 8081 is free.

## Developer setup directions

These directions should work on a unix system (e.g. Linux or Mac OS X)

    export WORKSPACE=~/workspace # this is your eclipse work space
    cd $WORKSPACE
    git clone https://github.com/myers/Pogic.git

    cd $WORKSPACE
    git clone https://github.com/Bukkit/Bukkit.git
    cd Bukkit
    mvn clean install

    cd $WORKSPACE
    git clone https://github.com/myers/CraftBukkit.git
    mvn clean package

    cd $WORKSPACE
    mkdir myserver
    cd myserver
    mkdir plugins
    cp -v $WORKSPACE/Pogic/server.sh .
    cd $WORKSPACE
    ln -s $WORKSPACE/myserver/plugins .

    # Download Minecraft Coder Pack in mcp29a.zip
    # unpack to $WORKSPACE/mcp29a
    # read README-MCP.TXT
    # decompile the client
    cd $WORKSPACE/mcp29a/sources/minecraft
    patch -p0 < $WORKSPACE/Pogic/pogic.mcp.patch
    cd $WORKSPACE/mcp29a
    sh script/recompile.sh

    cd $WORKSPACE
    git clone https://github.com/myers/SamplePogicPlugin.git
    cd SamplePogicPlugin
    ant deploy

    cd $WORKSPACE
    git clone https://github.com/myers/SamplePogicMod.git
    cd SamplePogicMod
    ant deploy

    # this install a Bukkit plugin that let's you spawn creatures
    cd $WORKSPACE
    git clone https://github.com/myers/Overlord.git
    cd Overlord
    ant deploy
    
    cd $WORKSPACE/myserver
    ./server.sh

    # in another terminal, be sure to define $WORKSPACE
    cd $WORKSPACE/mcp29a
    sh scripts/test_game.sh

    # connect to localhost in the Minecraft client
    # point where the creature should spawn
    # hit the chat key when connect and type
    /o BabyCreeper

[mcp]: http://mcp.ocean-labs.de/index.php/MCP_Releases
