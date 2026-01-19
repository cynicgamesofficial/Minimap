Minimap - Ultimate Classic Minimap for GZDoom
Feature-Rich HUD Minimap and Radar System

Minimap is a comprehensive navigation and radar system for GZDoom that brings modern HUD features to classic Doom gameplay. It provides both a minimap display and a real-time radar overlay with extensive customization options, waypoint support, and interactive map controls.

Installation
Simply drag the PK3 file into GZDoom or load it via the command line. Compatible with most mods, though it may conflict with other HUD modifications.
Requires GZDoom 4.0 or newer.

Core Features
Minimap Display

Real-time automap rendered as a HUD element
Configurable size and position on screen
Rotating or fixed orientation modes
Distance-based rendering for performance
Color-coded lines (normal, blocking, actionable)
Fullscreen map mode with time freeze
Omniscience mode to reveal entire map

Radar System

Live enemy tracking with health bars
Item and projectile detection
Customizable radar range and zoom
Monster type indicators
Friend/foe color coding
Key item highlighting

Waypoint System

Create custom waypoints with names and colors
Auto-waypoints for level start and exit
Interactive waypoint menu (Mouse3)
Delete waypoints by name or proximity
Persistent across game sessions

Interactive Controls

Pan and zoom the minimap independently
Fullscreen mode with cursor navigation
Switch indicator system with distance display
Compass overlay for orientation


How to Use
Basic Controls
Default Keybinds:
KeyActionMToggle fullscreen mapMouse3Open waypoint menuMouse4/5Zoom in/out (fullscreen mode)Arrow KeysPan map when not following player
Console Commands:
ucm_hide true/false                    - Toggle entire minimap
ucm_drawmap true/false                 - Show/hide map lines
ucm_drawplayer true/false              - Show player indicator
ucm_drawcompass true/false             - Show compass overlay
ucm_omniscience true/false             - Reveal entire map
ucm_mapfollow true/false               - Follow player movement
ucm_drawrotation true/false            - Rotate map with player

Display Settings
Size and Position:
ucm_mapsize 32-512                     - Minimap size (default 100)
ucm_xoffset -30 to 9999                - Horizontal position
ucm_yoffset -30 to 9999                - Vertical position
ucm_fullscreenzoom 0.1-5.0             - Fullscreen zoom multiplier
Rendering:
ucm_maprenderdist 128-8192             - Map line render distance (default 8192)
ucm_radardist 0-500                    - Radar range for actors (0 = disabled)
ucm_radarzoom 1-100                    - Radar zoom level (default 3)

Radar Configuration
What to Display:
ucm_drawitems 0/1/2                    - 0=none, 1=counted items, 2=all items
ucm_drawmissiles true/false            - Show projectiles
ucm_drawhealthbars true/false          - Enemy health bars
ucm_hidemonsters true/false            - Hide monster sprites
ucm_drawkeys true/false                - Show key items

Waypoint System
Creating Waypoints:

Press Mouse3 to open waypoint menu
Enter name and choose color
Click "Create" (places at player position)
Or enable fullscreen mode and use cursor to place at any location

Managing Waypoints:
ucm_markstart true/false               - Auto-waypoint at level start
ucm_markexit true/false                - Auto-waypoint at exit
Delete waypoints via the waypoint menu by name or closest to player.

Switch Indicators
The mod can highlight interactive switches on the minimap:
ucm_maxswitchdist 0-500                - Switch detection range (0 = disabled)
ucm_mustuse true/false                 - Only show USE-activated switches
ucm_showrepeatable true/false          - Show repeatable switches differently
ucm_showdistance true/false            - Display distance to switches
ucm_specific 0-280                     - Filter by specific line special
After changing switch settings, run ucm.switches.apply in console to refresh.

Visual Customization
Colors:
Access via Options Menu → Minimap → Map Colors
ucm_color_normal                       - Normal map lines
ucm_color_solid                        - Blocking lines
ucm_color_action                       - Actionable lines
ucm_color_border                       - Minimap border
ucm_color_backg                        - Background
ucm_color_compas                       - Compass indicators
ucm_color_stats                        - Statistics text
Opacity:
ucm_color_alpha 0.0-1.0                - Map line opacity
ucm_color_backgalpha 0.0-1.0           - Background opacity

Fullscreen Map Mode
Press M to enter fullscreen mode:

Game freezes (time stop powerup)
Arrow keys move cursor
Mouse4/5 zoom in/out
View statistics (kills, secrets, items, playtime)
Place waypoints with cursor
Pan anywhere in the level

Statistics shown:

Kills, Secrets, Items (with percentages)
Total playtime (hours:minutes:seconds)
Death counter
Map name and level name


Alignment Presets
Quick positioning via console:
align.upperleft
align.upperright  
align.lowerleft
align.lowerright
Or use the menu: Minimap → Map Alignment

Tips and Tricks
Performance Optimization

Disable ucm_radardist if you don't need enemy radar
Turn off ucm_drawhealthbars for cleaner display

Navigation

Use omniscience mode (ucm_omniscience true) to explore new maps
Enable compass overlay for better orientation when map rotation is on
Fullscreen mode is great for planning routes and marking objectives

Multiplayer

Waypoints are per-player
Map exploration is shared in co-op
Stats track individual performance

Advanced

Combine with automap keybinds for maximum flexibility
Use specific switch filtering to track quest objectives
Customize colors for different gameplay styles (speedrunning, exploration, etc.)


Menu Access
All settings available in:
Options → Minimap
Includes:

General settings
Radar configuration
Minimap options
Color customization
Control bindings
Switch filtering


File Structure
Minimap.pk3/
├── CVARINFO.txt         - Console variables
├── KEYCONF.txt          - Key bindings
├── MAPINFO.txt          - Event handlers
├── MENUDEF.txt          - Menu definitions
├── TEXTURES.txt         - HUD sprites
├── ZSCRIPT.txt          - Script entry point
└── zscript/
    ├── ucm_freeze.zsc           - Time freeze for fullscreen
    ├── ucm_waypoints.zsc        - Waypoint system
    ├── ucm_minimap.zsc          - Main minimap renderer
    ├── ucm_math.zsc             - Math utilities
    └── ucm_interactivity.zsc    - Input handling

Technical Notes
This fork includes several improvements over the original:

Enhanced waypoint system with cursor placement in fullscreen mode
Better fullscreen map implementation with proper time freeze
Improved omniscience mode that properly reveals map geometry
Auto-waypoints for start/exit with toggle options
Optimized rendering with distance culling
Cleaner code organization and variable management

The minimap renders the automap data directly to HUD, tracking player position and rotation in real-time. The radar system uses thinker iteration to locate and display actors within range. Fullscreen mode grants a temporary time freeze powerup for strategic planning.
Color-coded indicators help identify different map elements at a glance, while the switch detection system can highlight specific interactive objects based on their line special type.

Enjoy your enhanced navigation experience in GZDoom!
