# Get Spigot

The fastest and easiest way to download any version of [Spigot](https://www.spigotmc.org/) to your local computer.

The build script in this repository uses the [Spigot Build Tools](https://www.spigotmc.org/wiki/buildtools/) and a [Git](https://git-scm.com/) bash script to run a Spigot build for a specific [Minecraft](https://minecraft.net) version. You can use these files to host a Minecraft server or develop Minecraft server plugins.

### How It Works

The build script takes the version of Minecraft you want to build for as a parameter. A new directory will be created for the version you pass in. You can keep multiple versions in this repository, all of which will be usable on your computer. This makes it easy to obtain and manage multiple different versions of Spigot on your local machine.

This command will create lots of files, but you will probably only need some of them. These files have various uses, but most people use them to either [host a Minecraft server](/#Files-For-Hosting-a-Minecraft-Server) or [develop Minecraft server plugins](/#Files-For-Developing-Minecraft-Server-Plugins). See the below sections for more information on how to do this.

### Getting Started

- Clone this repository anywhere on your local computer
- Open a [Git bash](https://superuser.com/questions/1053633/what-is-git-bash-for-windows-anyway#1053657) window
  - If you do not have this program installed, you can install it by simply installing [Git](https://git-scm.com/downloads)
- Navigate to this repository inside the Git bash window
  - You can do this by typing `cd "\<repository_location\>"` in the Git bash window
- Run `./build.sh <version>` in the Git bash window
  - Replace \<version\> with the desired Minecraft version
  - For example, `./build.sh 1.12.2` will output the files for Minecraft version 1.12.2 in a new directory named 1.12.2

### Files For Hosting a Minecraft Server

To host a Minecraft server, you need a version of Minecraft to run on that server. Because Minecraft is written in the Java programming language, this will be a [JAR](https://en.wikipedia.org/wiki/JAR_(file_format)) file. You can download the vanilla Minecraft server JAR file from the [Mojang website](https://minecraft.net/en-us/download/server/), but if you use this file you won't be able to run any Bukkit or Spigot plugins. To run Bukkit or Spigot plugins, you need a slightly modified version of the Minecraft server JAR file. The build script in this repository generates this file for you. You can learn more about hosting a Minecraft server [here](https://minecraft.gamepedia.com/Tutorials/Setting_up_a_server).

- Bukkit server file location: `/<version>/CraftBukkit/target/craftbukkit-<version>.jar`
- Spigot server file location: `/<version>/Spigot/Spigot-Server/target/spigot-<version>.jar`

### Files For Developing Minecraft Server Plugins

To develop plugins for Minecraft servers you will need to download Spigot / Bukkit to your local computer. These files are not available online, and build automation tools like [Maven](https://maven.apache.org/) do not always have access to all of the files that you will need.

The easiest and fastest way to make sure that you have all the files you need is to simply have the build script in this repository generate them for you. If you want to make a plugin for a server running Minecraft version 1.12.2, simply run the build script and pass that version as a parameter. Then add the Bukkit / Spigot dependency to your plugin. If you are using Maven, you can do this by adding the below dependency to your `pom.xml` file. Note that this method does not require you to tell Maven where these files are stored on your local machine - it just works.

``` XML
<dependencies>
    <dependency>
        <groupId>org.spigotmc</groupId>
        <artifactId>spigot</artifactId>
        <version>1.12.2-R0.1-SNAPSHOT</version>
        <scope>provided</scope>
    </dependency>
</dependencies>
```

You can learn more about developing Minecraft server plugins from resources online. I highly recommend watching [this video tutorial series](https://www.youtube.com/watch?v=7dyopdta7ZI&list=PLKDE2sUUNmsv6RYCCu74sCKbETWdManka) or reading the official [Spigot development wiki](https://www.spigotmc.org/wiki/spigot-plugin-development/).

### Why This Is Necessary

Why should I use this repository to obtain a Spigot build? Why can't I just download the files I want online?

Good question! The answer is that distributing copyrighted intellectual property over the internet is illegal. Because Spigot is built on top of Minecraft, it is illegal to distribute the files from a Spigot build online because those files include Minecraft source files, which are the copyrighted intellectual property of Mojang.

To get around this, you must generate the files yourself using the Build Tools provided by Spigot. You can then legally use these files to run a server and develop plugins for Minecraft servers.

### What The Build Script Does

- Checks for updates to this repository
  - If there are updates, then they are pulled in and the script quits
  - When this happens, simply re-run the build script after it quits
- Downloads the latest version of the Spigot Build Tools
- Makes sure there are no changes to source controlled files
  - If you accidentally make changes to source controlled files, simply undo the changes and re-run the script
- Creates a new subdirectory for the version you are building
  - If the directory already exists, the contents of the directory are deleted
  - Deleting old builds allows a corrupted build to be re-generated successfully
- Uses the Spigot Build Tools to generate the desired files for the specified version

### Legal

This project is in no way affiliated with [Minecraft](https://minecraft.net), [Mojang](https://mojang.com), [Microsoft](https://www.microsoft.com/en-us/), [Spigot](https://www.spigotmc.org/), [Bukkit](https://bukkit.org/), or any other organization.
