# Spigot

The fastest and easiest way to download any version of Spigot.

This repository uses the [Spigot](https://www.spigotmc.org/) [Build Tools](https://www.spigotmc.org/wiki/buildtools/) and a [Git](https://git-scm.com/) bash script to run a Spigot build for a specific [Minecraft](https://minecraft.net) version.

This is accomplished by running the script and passing in the version of Minecraft you want to use as a parameter. When running this command, a new directory will be created for the version you pass in, and the `BuildTools.jar` file will be used to generate the desired files in that directory. If the directory already exists, it will be overwritten for this version. You can keep mutliple versions, all of which will be usable on your computer. This repository should always contain the latest version of the Build Tools, and will automatically update before you run the script, which guarentees that you are always using the latest version of the Build Tools. This makes it easy to obtain and manage multiple different versions of Spigot on your local machine.

### Usage

Run `build.sh <version>` from the command line.

For example, `build.sh 1.12.2` will output the Spigot files for Minecraft version 1.12.2 in a newly created directory.

### But Why?

Why is this necessary? Why should I use this repository to obtain a Spigot build? Why can't I just download the files I want online?

This is a good question. The answer is that distributing copyrighted intillectual property over the internet is illegal. Because Spigot is built ontop of Minecraft, it is illegal to distribute the files from a Spigot build online because those files include Minecraft source files, which are the coprighted intillectual property of Mojang.

To get around this, you must generate the files yourself using the Build Tools provided by Spigot. You can then legally use these files to run a server and develop plugins for Minecraft servers.

### Legal

This project is in no way affiliated with [Minecraft](https://minecraft.net), [Mojang](https://mojang.com), [Microsoft](https://www.microsoft.com/en-us/), [Spigot](https://www.spigotmc.org/), [Bukkit](https://bukkit.org/), or any other organization.
