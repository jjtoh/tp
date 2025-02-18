# User Guide

## <span style="color:orange ">Introduction</span>

Timetabler is a **desktop app** that allows **NUS students** taking official NUS modules to **view their classes** and **plan their timetable efficiently** in AY22/23. The desktop app is optimmized for use via a Command Line Interface (CLI).


## <span style="color:orange ">Quick Start</span>

1. Ensure that you have Java `11` or above installed.
2. Down the latest version of `tp` from [here](https://github.com/AY2223S1-CS2113-T17-3/tp/releases/).
3. Copy the jar file into an empty folder.
4. Open a command window or terminal for mac in that folder.
5. Run the command `java -jar tp.jar` in the same folder.
6. You will be prompted to enter the `semester` (1 or 2) you are planning for when the program first starts.


##  <span style="color:orange ">Features</span>


* [Add module](#adding-a-module-add) `add`
* [List all modules](#listing-modules-list) `list`
* [Find info on a module](#finding-information-on-a-module-info) `info`
* [Set lesson for a module](#setting-a-modules-lessons-set) `set`
* [Delete a module](#deleting-a-module-add) `delete`
* [Auto-allocate lessons](#auto-allocating-all-modules-allocate) `allocate`
* [Print timetable](#printing-the-timetable-print) `print`
* [Quit program](#quitting-the-program-quit) `quit`


###  <span style="color:orange ">Adding a module: `add`</span>
Command used to initiate the process of adding a new module.

* You will be prompted to enter the module code after this command.
* The module code is not case sensitive but must be of an official NUS module.

**Example of Usage:**
input: `add`

```
Please enter module code
```
input: `cs2040c`
```
Successfully added new module: CS2040C : Data Structures and Algorithms
```
---
###  <span style="color:orange ">Listing modules: `list`</span>
Command used to list out all modules added to user's timetable.

* Modules with duplicate lesson types means that students are expected to go for at least that number of classes of that lesson type.

*For example: 2 Lecture slots means that students are expected to attend 2 different lecture slots.*

* The app does not restrict users from leaving empty lesson slots or other unoffical lesson combinations. This gives users freedom and caters to their unique situations.

**Example of Usage:**
input: `list`

```
Here are your modules:
1. CS2040C: Data Structures and Algorithms
     [Lecture] Undetermined Day   Undetermined Time - Undetermined Time
     [Lecture] Undetermined Day   Undetermined Time - Undetermined Time
     [Laboratory] Undetermined Day   Undetermined Time - Undetermined Time
```
---
###  <span style="color:orange ">Finding information on a module: `info`</span>
Command used to see information on a module.

* Only module name, module code and description will be shown.

**Example of Usage:**
input: `info`

```
Please enter module code
```
input: `cs1010`
```
Here are some information about the module:
Module Code: CS1010
Module Name: Programming Methodology
Module Description: This module introduces the fundamental concepts of problem solving by computing and programming using an imperative programming language. It is the first and foremost introductory course to computing.  Topics covered include computational thinking and computational problem solving, designing and specifying an algorithm, basic problem formulation and problem solving approaches, program development, coding, testing and debugging, fundamental programming constructs (variables, types, expressions, assignments, functions, control structures, etc.), fundamental data structures (arrays, strings, composite data types), basic sorting, and recursion.
```
---
###  <span style="color:orange ">Setting a module's lessons: `set`</span>
Command used to initiate the process of setting lesson for a module.

* Only lessons of modules which are already added can be set.
* Duplicates can be set and lesson slots can be left empty to cater to students' unique situations.
* Only one lesson can be set at a time.
* Follow the prompts at each stage of the setting process carefully and only enter valid inputs.

**Example of Usage:**
input: `set`

```
Which module would you like to set lessons for? Enter corresponding valid index
1. CS2040C : Data Structures and Algorithms
```
input: `1`
```
Which lesson type do you want to set? Enter corresponding valid index
1. Lecture     2. Lecture     3. Laboratory     
```
input: `2`
```
Which is your preferred timeslot? Enter corresponding valid index
1. [Lecture] Wednesday   10:00 - 12:00
2. [Lecture] Thursday   17:00 - 18:00
```
input: `1`
```
Successfully set your lesson!
```
---
###  <span style="color:orange ">Deleting a module: `delete`</span>
Command used to initiate the process of deleting a new module.

* You will be prompted to choose the module to delete after this command.

**Example of Usage:**
input: `delete`

```
Which module you would like to delete? Please enter the index of that module. 
Here are your modules:
1. CS2040C: Data Structures and Algorithms
     [Lecture] Undetermined Day   Undetermined Time - Undetermined Time
     [Lecture] Wednesday   10:00 - 12:00
     [Laboratory] Undetermined Day   Undetermined Time - Undetermined Time

```
input: `1`
```
Successfully deleted module!
```
---
###  <span style="color:orange ">Auto-allocating all modules: `allocate`</span>
Command used to initiate the process of automatically allocating modules.

* Modules are allocated in the order they were added / listed as per the command `list`.
* In the case where it is impossible to have a permutation of lessons such that there is no clash, the user will be notified and the lessons will not be allocated.
* Users can still choose to manually set the modules to clash with the command `set`.

**Example of Usage:**
input: `allocate`

```
All your mods have been successfully allocated!
```
---
###  <span style="color:orange ">Printing the timetable: `print`</span>
Command used to produce a timetable for a straightforward view.

* Legend and other things to take note of will be printed below the timetable.
* Only lessons which are correctly set will be reflected in the timetable.
* Clashes are indicated with `XXXXXX` in place of the module code. At the end of the timetable, clashed modules will be listed out, if any.
Alternatively, you may use `list` command to find the clash and deconflict with `set` feature.

**Example of Usage:**
input: `print`

```              :              :              :              :              :               
              : MON          : TUE          : WED          : THU          : FRI           
==============:==============:==============:==============:==============:===============
   0800       :              :              :XXXXXXXXXXXXXX:              :               
   0830       :              :              :XXXXXXXXXXXXXX:              :               
   0900       :              :              :XXXXXXXXXXXXXX:              :               
   0930       :              :              :XXXXXXXXXXXXXX:              :               
   1000       :              :              :XXXXXXXXXXXXXX:              :               
   1030       :              :              :              :              :               
   1100       :              :              :              :              :               
   1130       :              :              :              :              :               
   1200       :              :              :              :--------------:               
   1230       :              :              :              :CS1231        :               
   1300       :              :              :              : SEC          :               
   1330       :              :              :              :              :               
   1400       :              :              :              :--------------:               
   1430       :              :              :              :              :               
   1500       :              :              :              :              :               
   1530       :              :              :              :              :               
   1600       :              :              :              :              :-------------- 
   1630       :              :              :              :              :CS2113         
   1700       :              :              :--------------:              : LEC           
   1730       :              :              :CS2113 TUT    :              :               
   1800       :              :              :--------------:              :-------------- 
   1830       :              :              :              :              :               
   1900       :              :              :              :              :               
   1930       :              :              :              :              :               
   2000       :              :              :              :              :               
   2030       :              :              :              :              :               
   2100       :              :              :              :              :               
   2130       :              :              :              :              :               
   2200       :              :              :              :              :               

These are the clashed modules : 
CS1231
ES2631

 * Note that timings indicated refers to the start of the corresponding 30 minutes timeslot.
 * Slots with XXXXXX indicates that there is a clash between two or more lessons.
 * Modules, if any, that start before 8am or ends after 10pm timings are excluded.
 * Timings are approximated to 30 minutes block with valid assumption that NUS mods are typically designed in such blocks.
```
---
###  <span style="color:orange ">Quitting the program: `quit`</span>

Command used to exit the program and stop its execution.

**Example of usage**
input: `quit`

``` 
 _____            __   __             ___              _       _ 
/  ___|           \ \ / /            / _ \            (_)     | |
\ `--.  ___  ___   \ V /___  _   _  / /_\ \ __ _  __ _ _ _ __ | |
 `--. \/ _ \/ _ \   \ /  _ \| | | | |  _  |/ _` |/ _` | | '_ \| |
/\__/ /  __/  __/   | | (_) | |_| | | | | | (_| | (_| | | | | |_|
\____/ \___|\___|   \_/\___/ \__,_| \_| |_/\__, |\__,_|_|_| |_(_)
                                            __/ |                
                                           |___/                 
```

##  <span style="color:orange ">FAQ</span>

**Q**: How do I transfer my data to another computer?

**A**: Copy all data files `Sem1DataDirectory` or / and `Sem2DataDirectory` together with the jar file to the new computer, in the same directory.
