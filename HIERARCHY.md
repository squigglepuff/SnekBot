# Directory Hierarchy

## Summary
This document is here to give a basic idea as to the directory/file hierarchy of this project.

**Single Layer View**
```
<root>
├── core
├── gui
├── obs
├── system
├── tests
├── twitch
└── util
```

Each directory seen here is a "module" and they are initialized with a **_init_.py** file. This file 99% of the time is blank, if you're wanting to include the module, you'll instead
want to import the "directory/directory_name.py" file which acts like a "master include" file for the whole module.

The only file outside of this whole mess is "snekbot", which is simply a "main.py" file who does a bit of extra lifting to make sure SnekBot will run correctly and then runs **core.app**.

## Modules
### Core
This directory houses all the "core" functionality and objects for the application. This module is also responsible for managing the event queue and main run-loop via it's **app** sub-module.

### GUI
This directory houses all the "GUI" objects that interface/interact with PyQT. It's important to note that this module and *Core* run on the same thread, so thread-affinity isn't too big a deal until you're needing to communicate with *OBS* or *Twitch*.

### OBS
**NOTE: This runs on it's own thread!**

This directory houses all the "OBS" objects that interact with "obspython" and OBS.

### System
This directory houses all the "system" libraries. These are all custom "in-house" libs, but are needed by all other modules.

### Twitch
**NOTE: This runs on it's own thread!**

This directory houses all the "Twitch" objects and functionality for the application.

### Util
This directory houses all the "Utility" objects/functions. This is much like "System" in that it's needed and vital, but some of it may be written other persons or acquired by other means.

## Tests Directory
This directory contains test scripts used to prove concepts and unit-test ideas before putting them into the system.
