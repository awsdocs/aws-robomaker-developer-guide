# Understanding Simulation World Templates<a name="worlds-managing-simworld-templates-components"></a>

This section describes the components of a simulation world template\. Components include the floor plan and preferences for interior materials and furniture\. Simulation WorldForge provides defaults for many of the components including materials, furniture selection, and room connectivity\. You can override the defaults with your own preferences\. Simulation WorldForge will make a best effort to follow your preferences when generating worlds\. 

## Floor Plan<a name="worlds-managing-simworld-templates-components-floorplan"></a>

The floor plan specifies an indoor floor plan for a single\-story, residential building\. It includes the world dimensions, the number and types of rooms, and parameters that influence how rooms are connected\. 

Every world is guaranteed to have a clear 1 meter cylinder centered at coordinate `(0,0,0)`, the default robot starting position\. Simulation WorldForge determines the room\. 

### World Dimensions<a name="worlds-managing-simworld-templates-components-floorplan-worldims"></a>

You can configure an aspect ratio and a ceiling height for the building\. Valid aspect rations are from 1:4 to 4:1\. Valid ceiling height is 2\.4 to 4\.0 meters\. All measurements are in meters and square meters\. The console supports conversion between the US and metric system\. 

### Rooms<a name="worlds-managing-simworld-templates-components-floorplan-rooms"></a>

You can specify the number of rooms, room type, room name, desired area, desired aspect ratio, and interior features\. The following room types are supported: 
+ Bedroom
+ Bathroom
+ Living
+ Dining
+ Kitchen
+ Hallway
+ Closet

Furniture, wall material, and floor material are selected from types appropriate for the room type\. For example, a bathroom might be assigned a tile wall, a linoleum floor, and have a toilet and a shower\. 

### Connections<a name="worlds-managing-simworld-templates-components-floorplan-connections"></a>

Simulation WorldForge automatically connects all rooms by default\. You can connect rooms by an opening or a doorway\. When rooms are connected by an opening, the rooms will be in an open floor plan\. There is no wall\. Rooms connected by a doorway have a narrow, doorless opening\. Doorway openings are randomly placed along the adjacent wall\. 

You can override default connections with desired connections\. For example, if you have a kitchen, dining room, and a bedroom, you can request a door connection between the kitchen and bedroom\. Simulation WorldForge will make a best effort to make the connection, but it is not guaranteed\. 

## Interiors<a name="worlds-managing-simworld-templates-components-interiors"></a>

You can select from a number of different interior material and furniture types\. Simulation WorldForge randomly assigns flooring, walls, and furniture to rooms by room type\. For example, a kitchen might be assigned an oven and dining room table and chairs\. 

You can select material types for flooring and walls as a custom set\. When you create a custom set, you can apply the custom assignment by **room type** or **room name**\. You can have multiple custom sets\. If there is a conflict, a custom assignment for a room always has precedence over one for room type\. 

For example, assume you have custom set "Modern Flooring" assigned to all bedrooms and a custom set "Chic Flooring" assigned to the room "Master Bedroom"\. When Simulation WorldForge assigns flooring materials, "Master Bedroom" will be assigned flooring material from the "Chic Flooring" set\. Other bedrooms will have flooring material selected from the "Modern Flooring" set\. 

This rule also applies to custom furniture sets\.

### Flooring Material Types<a name="worlds-managing-simworld-templates-components-interiors-flooring"></a>

Supported flooring types include the following: 
+ Carpet
+ Concrete
+ Floorboards
+ Linoleum
+ Parquetry
+ Tiles

Flooring material is randomly chosen from all of the flooring material types selected\. For example, if you specify `Carpet`, `Concrete`, `linoleum` and `parquetry`, the floor of your room might be concrete\. 

### Wall Material Types<a name="worlds-managing-simworld-templates-components-interiors-walls"></a>

Supported wall material types include the following: 
+ Brick
+ Concrete
+ Stone
+ Tiles
+ Wood panels
+ Wall paint
+ Wallpaper

Wall material is randomly chosen from all of the wall material types selected\. For example, if you specify `Brick`, `Tiles` and `Wallpaper`, your room might have walls that use tile and wallpaper\. Simulation WorldForge might not assign wall material from all chosen wall material types\. 

### Furniture Types<a name="worlds-managing-simworld-templates-components-interiors-furniture"></a>

Simulation WorldForge supports the following furniture types:
+ Baths
+ Bar cabinets
+ Beds
+ Bookcases
+ Coffee tables
+ Console tables
+ Corner cabinets
+ Desk chairs
+ Desks
+ Dining chairs
+ Dining tables
+ Dish washers
+ Dressers
+ End and side tables
+ Floor lamps
+ Fridges
+ Living room chairs
+ Kitchen islands and carts
+ Media storage
+ Nightstands
+ Ottomans
+ Ovens
+ Serving carts
+ Showers
+ Sideboards and buffets
+ Sofas
+ Storage
+ Storage benches
+ Toilets
+ Vanity counters
+ Washing machines and dryers

Furniture is randomly chosen from all of the furniture types selected\. For example, if you specify `Sideboards and buffets`, `Sofas` and `Console tables`, your room might have a sofa and two console tables, but no sideboard or buffet\. Simulation WorldForge might not assign material types from all chosen furniture types\. 