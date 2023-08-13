# PITMAN - Source Code

Here is the HuBASIC source code for the classic **PITMAN** game, released in
August 1985 as a type-in from the Japanese magazine Oh!MZ, playable on Sharp
MZ-700/1500 computers.


## Code Transcription Notes

The BASIC source contains control characters and special graphic characters
unique to Sharp MX-700/1500 computers. Here are some notes on how those were
handled when transcribing from the magazine.

* CLR (clear screen) control character, replaced with ⓒ
* Move Cursor/Arrow key input control characters, replaced with ← → ↑ ↓
* Various graphic characters are replaced with an appropriate ASCII/Unicode
  character (e.g. ▄ and ▒)
* LINE 170: stick figure sprite for the player lives, replaced with §
* LINES 1160-1240: included Japanese translations, these have been omitted


## Oh!MZ Game Article

The following text is transcribed from the Oh!MZ, August 1985 magazine article
(_online tools were used for this translation, which was then manually
edited and formatted_).

PITMAN is a puzzle game with 50 levels designed for the Sharp MZ-700 or MZ-1500, and written in HuBASIC.

### How to type in/execute the game

Type in the BASIC code found in Listing 1 (`pitman.bas`), and save it

```basic
SAVE "PITMAN"
```

Please type the machine language from Listing 2 (`levels.asm`) with

```basic
LIMIT &HE000
```

After entering the data and verifying the checksum, save it

```basic
SAVEM "PIT", &HE000, &HF300
```

Run the game with

```basic
RUN "PITMAN"
```

The game will start after automatically loading the machine language data. If you stop the program in the middle, press `F1` to resume execution.

### How to Play

When the title screen appears, press the space bar or keys 1-9 to start the game. If you press the space bar, you will start from the 1st level, and if you press 1 to 9, you will start from the level that is the number multiplied by 5.

The purpose of the puzzle is to operate PITMAN with the cursor keys and collect all the gold castles on the screen.

The rules are as follows:

* **Ladders** - PITMAN can move up, down, left and right.
* **Gold Bullion** - Can only be taken from the left or right. If there is a blank space under the gold nugget, the nugget will fall.
* **Soil** - Dig from the left or right to proceed. Once dug, it disappears and cannot be restored.
* **Stone** - You can move it left or right. It will fall like a gold nugget.
* **Wall** - Blocks your way. You can't even push it. It doesn't fall.
* **PITMAN** - When the floor is missing and you are not on the ladder, you will fall, and when the top is missing you can jump (there is a level where you can use this jump). You can move up, down, left and right according to the above rules.

The following commands can be used during the game.

* `G`: **GIVE UP** - Play the same level with one less life. Press it when you get stuck.
* `N`: **NEXT** - Loose a life and play the next level.
* `B`: **BACK** - Play the previous level by one less.
* `E`: **EDITOR** - Enter the editor.
* `F1` - Return to the title screen.

### Editor

We've added an editor to this game with the idea of finding new designs with the user's creativity. The editor is entered by pressing the `E` key on the title screen or while playing the game. The commands for the editor are explained below.

`H: HELP`

All command names. ↓ Display their contents.

`P: PLAY`

You can start the game from any level.

`L: LOAD`

Load data. The file format is machine language and the filename is "PIT".

`S: SAVE`

Save data. The file format is machine language and the file name is "PIT".

`C: CLEAR`

Erase the data of any surface.

`E: EDIT`

Enter screen creation mode - to move the cursor (`F1`), and to place the
character. Correspondence between numbers and characters is:

1. space
2. chopsticks 2
3. gold bars
4. warriors
5. stones
6. walls
7. PITMAN

Press `N` to go to the next page, `B` to go to the previous page, and `R` to
return to waiting for command input.

`D: DATA OUT/IN`

Used for saving/loading data. Converts 88-byte data to 46-character ASCII code
(0 to 9, A to Z) and vice-versa. Use it when exchanging PITMAN data in data
banks, etc., or when submitting your original level.

* OUT: Data → ASCII. Save to tape in ASCII format.
* IN: data from keyboard or tape. After entering the data, -> Convert the data.

Note: DATA OUT/IN is one data - if two or more PITMAN are placed in the data,
they will disappear, be careful.

Since this MZ-700/1500 program uses color instructions and characters specific
to it, porting it to other models will be quite difficult. For those of you who
still don't understand, here's a variable table. Please note that X, X1, and X2
are used for chores outside of the game. Use the editor to create a unique
original.

```text
MX, MY   PITMAN X, Y
HX, HY   X, Y coordinate change value
X1, X2   Drop range of stones and gold nuggets
X,Y      X, Y coordinate chores
L        Level
M        Misses (rest)
G        Number of gold bars
GB       PITMAN's background character (0: blank, 1: ladder)
SY       My Style
Q, I     Chores (FOR~NEXT)
A$, B$   For inputting and outputting various characters
```

Please send your levels to Oh!MZ. It would be nice if we could collect the
designs that everyone has made and make PITMAN2.

> "PITMAN", which was selected as the special prize game of the month, please
> type it anyway. It's a thinking game with 100% enthusiasm.
> Ingenious character graphic screens, with a total of 50 levels, which were
> made by him. Plus, it comes with an editor function, so there's nothing more
> to say. Zankawa is a high school student. I have high hopes for his future
> success. (editing room.H.)


## Copyright Information

Transcribed by Michael R. Cook, 2023.

PITMAN, COPYRIGHT 1985 Y. ISOKAWA.
