# ELKSmoria
This fork repository is to make a roguelike game for ELKS based on UMoria 5.6 and it is just started.  
ELKS is the Embeddable Linux Kernel Subset in the following repository.  
https://github.com/jbruchon/elks

The code size is limitted to 128KB, and the data segment size is limitted to 64KB,
so great amount of shrink is needed.

Now I am triying to create a Warrior only game with a few treasures on the field without shops.

## How to play
Please place the following files under the morifile directory of the current directory.

./morifile/license
./morifile/newselks
./morifile/origcmds
./morifile/roglcmds

morisave and moriscor files are also created under the current directory after save the game.

When starting the new game, you can select whether you use the Umoria original key or Rougue key.
./elksmori without option will start the game with the former key which use numeric key(1-9) to move.
./elksmori -r will start the game with the latter key which use "hjklyubn." key to move.

You can see the help file for keys by hitting "?" after creating character and starting the game.
Also, you can see what the character on the screen means by hitting "/" then the character.

First you will be in the Town(without any stores...).
You can see "@" for player, ">" for down staircase to the dungeon, and maybe "P" for people.
Go on the ">" and press ">" to step down.

You have Soft Leather Armor, Cloak. Dagger, and 5 Woodden Torches at the beginning.
Press "i" to see the inventory, then press "w" and select these to Wear/Wield.

There is no potion at the begining, but you can heal yourself by
hitting "5" for original key, "." for rogue key several times to spend turns.

You can attack monsters by just moving toward them.

Ctrl-X will save the game and Exit.

## How to build
Link $TOPDIR of the ELKS repository as elks_repository in the source directory of this repository.  
Link files in elks directory in the source directory.  
Link unix.c in unix directory in the source directory.

cd source  
ln -s $TOPDIR elks_repository  
ln -s ../elks/\*.\* .  
ln -s ../unix/unix.c .  
mv Makefile.elks Makefile  

make clean  
make  

The following text is the README of the original repository.

----------------------------------------------------------------------
# UMoria
Official source code of the roguelike UMoria.

## Introduction
This repository contains the official source code of the roguelike UMoria (see http://en.wikipedia.org/wiki/Moria_%28video_game%29 and http://www.roguebasin.com/index.php?title=Moria for more info) as retrieved from Beej's Moria Page (http://beej.us/moria/).

I have checked in each version in order and tagged it, so that those interested in the historical development of the source will be able to explore it using Git/Github tools.

I have no plans to host official binaries here at this time, but am open to it if people are interested.

## Personal projects
Personal projects by myself and others may be found on branches and/or forks. These will not be merged into the master branch without the official blessing of David Grabiner (see http://www.remarque.org/~grabiner/moria.html or http://www-math.bgsu.edu/~grabine/moria.html), the official UMoria maintainer.

Binaries for personal projects may be released here, however.

## License Information
The source code to versions 5.5.2 and older is licensed under a combination of GPLv2 and Public Domain, per the Free Moria project (http://free-moria.sourceforge.net/).

David Grabiner's 5.6 changes have been released under the GPLv3.

## Background
I have a long-standing interest in UMoria. It was my first roguelike, and I eventually produced the DJGPP 32-bit DOS port, which has stood as the last official PC release. Later, I participated in the Free Moria project, and ever since then I've toyed with the idea of playing with the source code once in a while. I've finally decided to at least start this project to get the official source code history onto Github, and in parallel I've produced a Cygwin port of the Unix source for use on modern Windows PCs.
