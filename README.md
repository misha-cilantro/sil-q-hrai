# Sil-Q
Sil-Q is a computer role-playing game with a strong emphasis on discovery and
tactical combat. It has a simple but rich combat system which allows for a
great variety of choice.

## Sil-Q hrai

hrai - Quenya for easy (probably, I only searched a little)

I adore the gameplay of Sil-Q, but I'm terrible at it. I've created Sil-Q hrai
as an easy mode version of Sil-Q so you can adjust difficulty and enjoy the 
fantastic gameplay and emmaculate First Age vibes without dying 30 minutes
in EVERY. SINGLE. TIME.

There are several dials to adjust difficulty:

1. Dungeon pressure. (DONE)
   Sil-Q forces you lower and lower into the dungeon as you play so prevent
   grinding. But this is hrai, and we support a little grinding!
   
   On character creation, select dungeon pressure 1 to 5.

   1 is no pressure at all, you only ever go down one level.
   2 lowers pressure by 1/4.
   3 lowers pressure by 1/3.
   4 lowers pressure by 1/2.
   5 is standard Sil-Q pressure.

2. Elven ressurection. (PLANNED)
   The First Children do not leave the world on death, but go to the halls of Mandos
   where they may rest before bodily ressurecting in the world.

   This means when you die playing an elf you may choose to ressurect. You will start
   back on the first floor with all your skills etc., but your equipment will be lost.

3. Restore to start of floor. (PLANNED)
   On character creation, choose whether to allow restoring to the start of the floor
   on death. Every time you start a floor, a save game is made that you can restore to.

   This option overrides elven ressurection.

For faireness, your dungeon pressure, number of elven ressurections, and/or restore
on death is recorded on your character sheet so that everyone knows you're a not
a Serious Business Roguelike player (like me!) :)

(I beat Angband as a teen using my brother's save game backup batch file. Max cheat.
Still one of my iconic childhood gaming experiences, idc. Good gameplay is good gameplay.)

## Compiling Instructions

Compiling Sil-Q is not very difficult, and has been tested on Windows, Linux, and OS X.

Makefiles for various other systems still exist as a legacy from Sil. If you manage
to build Sil-Q for a system other than Windows, Linux, or OS X please create a git branch
with any changes necessary, update this file and open a github pull request against
https://github.com/sil-quirk/sil-q.

The first step is the same on all systems, so do this and then look through
this file for advice on your specific system. 

0. Install the Sil source code:

   Unzip the file "Sil-src.zip". It will become a folder called "Sil"
   which contains subfolders called "lib" and "src". Move it to wherever
   you want to keep it. The src folder contains all the source code
   while the lib folder contains other files that the game uses.
   When you are done compiling, the game will be automatically installed
   in the Sil folder as well.


### Linux or Unix with gcc  (tested with Sil-Q)

   There are several different unix setups for Sil-Q:

   X11: Allows multiple windows, has correct colours.
   GCU: Works in a terminal using 'curses', has only 16 or 8 colours.
   CAP: Works even in old terminals, but is monochrome.

1. Mess with the Makefile:

   Edit Makefile.std in the src directory.
   Look for the section listing multiple "Variations".
   Choose the variation that you like best.
   Remove the # comments from that section's code.
   Comment out the default section.

2. Compile Sil-Q:

   Run "make -f Makefile.std install" in the src directory.

3. Run Sil-Q:

   Go back to the Sil folder and start Sil-Q with "sil".

### Windows with Cygwin   (tested with Sil-Q)

1. Getting the free Cygwin compiler: 

   Download the free Cygwin compiler. It provides a shell interface very
   similar to a normal Unix/Linux shell with many useful tools. Install it
   and start the Cygwin terminal. Make sure to get the 32 bit version.

   Note you will have to ensure "make" and the mingw C compiler are installed
   as they may not be included in your Cygwin default installation.

2. Compile Sil-Q: 

   In the Cygwin terminal change to the src directory and run 
   "make -f Makefile.cyg install". 
   Sil should now be compiled and installed into the Sil folder.  
   The executable file will be called Sil.exe. 

3. Run Sil-Q: 

   Go back to the Sil folder and run Sil.exe. 

### Windows with Visual Studio 2022 (experimental, tested with Sil-Q on MSVC 2022)

1. Acquire Microsoft Visual Studio 2022.

2. Compile Sil-Q:

   Assuming you have MSVC 2022, this should be as simple as selecting Debug or
   Release, opening sil-q.sln in the msvc2019 directory and selecting Build Solution
   from the Build menu.

3. Run Sil-Q:

   Go back to the Sil folder and run Sil.exe.

NOTE: This is a very new and very raw port, and requires testing.

### OS X with Xcode  (tested with Sil-Q; Xcode 11.6 on OS X 10.15.5)

1. Get Xcode from the app store if not installed:

   Use App Store to get Xcode, a free set of development tools from Apple.

2. Compile Sil-Q:

   In a Terminal window, change to the src directory and run
   "make -f Makefile.cocoa install".
   Sil-Q should now be compiled and set up as an OS X application, Sil.app,
   in the folder above the src directory.  You may move Sil.app to wherever
   you like.

   If you are using an arm-based Mac and want a native application, use
   "make -f Makefile.cocoa ARCHS=arm64 install"
   instead of the command given above.  To generate a universal application
   that will run natively on either x86_64 or arm, use
   "make -f Makefile.cocoa ARCHS='x86_64 arm64' install".
   Building for arm likely requires at least Xcode 12.2 or later.  Before
   building for a different set of architectures, run
   "make -f Makefile.cocoa clean" to clean up any object files that may not
   match your new set of selected architectures.

3. Run Sil-Q:

   In a Finder window, navigate to where you placed Sil.app.  Then double
   click on it to run it.  If you are running 10.15 or later and haven't run
   Sil-Q or Sil before, you'll see a dialog about granting Sil-Q access to
   your Documents folder since it wants to place saved games, the high
   score file, and some other data in Documents/Sil.

