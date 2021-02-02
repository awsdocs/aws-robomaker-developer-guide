# Common Tasks<a name="worlds-creating-common-tasks"></a>

This section contains common tasks for creating simulation world templates\. Many of the tasks specify desired connections or desired shapes\. Simulation WorldForge makes a best effort to generate worlds according to simulation world template parameters\. Generated worlds might not always include all desired properties\. 

**Topics**
+ [Specifying a List of Rooms for a Floor](#worlds-creating-task-list-rooms-for-floor)
+ [Requesting a Long Hallway](#worlds-creating-task-hallway)
+ [Requesting a Doorway Between Rooms](#worlds-creating-task-doorway-between-rooms)
+ [Requesting a Wide Floor Plan Footprint](#worlds-creating-task-request-wide-footprint)
+ [Requesting a Custom Ceiling Height](#worlds-creating-task-custom-ceiling-height)
+ [Specifying the Same Material Types to Floors in Different Rooms](#worlds-creating-task-same-material-floors)
+ [Specifying Different Material Types to Floors Between Rooms of the Same Type](#worlds-creating-task-different-material-floors)
+ [Specifying More and Less Furniture in Rooms](#worlds-creating-task-furniture-more-less)
+ [Adding Specific Furniture Types to all Bedrooms and a Single Shared Living/Dining Room](#worlds-creating-task-furniture-single-bedroom)
+ [Specifying a Room without Furniture](#worlds-creating-task-no-furniture)

## Specifying a List of Rooms for a Floor<a name="worlds-creating-task-list-rooms-for-floor"></a>

 The room type influences the floor plan by contributing to what rooms are adjacent\. The room type is also used to determine the types of material for its flooring and walls and the types of furniture to randomly place by default\. You may override the default flooring and walls material types and furniture types by room type or room name\. 

You can select from the following room types: Bedroom, Bathroom, Living Room, Dining Room, Kitchen, Hallway, Closet\. 

The following examples specifies a three room house\. The sizes and shapes of the rooms are determined by default\. 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Floor plan**, choose **Rooms**\. 

1. In the **Rooms** pane, choose **Add room**\. 

1. Add details for the room\. You can specify a room **Name**, **Room type**, **Desired area** and **Desired aspect ratio**\. 

1. Choose **Save** to save the new room\. Repeat until you have the rooms you desire\. If you add too many, you can delete them from the **Rooms** pane\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Rooms": [
  {
   "Type": "Bedroom",
   "Name": "My Master Bedroom",
  },
  {
   "Type": "Bathroom",
   "Name": "My Ensuite",
  },
  {
   "Type": "Kitchen",
   "Name": "My Kitchen",
  }
]
```

------

## Requesting a Long Hallway<a name="worlds-creating-task-hallway"></a>

You can use the `DesiredShape` property to request the preferred shape of a room\. `Type` has no affect on the shape\. In the following example, the `Hallway` aspect ratio is low\. When it is combined with a large enough `Area`, it indicates a desire for a long, narrow hallway\. Simulation WorldForge will attempt to generate rooms similar to the desired shape\. 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Floor plan**, choose **Rooms**\. 

1. In the **Rooms** pane, choose **Add room**\. 

1. Specify a room **Name**, then choose **Hallway** for **Room type**\. 

1. Specify a **Desired area** of `20` and a **Desired aspect ratio** of `4:1`\. 

1. Choose **Save** to save the hallway\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Rooms": [
  {
    "Type": "Hallway",
    "Name": "My Hallway",
    "DesiredShape": {
      "Area": 20.0,
      "AspectRatio": {
        "x": 4, "y": 1
      }
    }
  }
]
```

------

Valid room area range is 10 meters to 300 meters\. Valid room aspect ratio range is 1:4 to 4:1\. 

## Requesting a Doorway Between Rooms<a name="worlds-creating-task-doorway-between-rooms"></a>

If you have two rooms, and the rooms share at least one wall, you can request a `DesiredConnections` between the two rooms\. Simulation WorldForge will try to place the rooms adjacent and, depending on the `ConnectionType`, either place a `Doorway` in a random location along an adjacent wall or create `Opening` by removing an adjacent wall entirely\. 

 The following example requests an open connection for the living room and kitchen\. It also requests a separate doorway connection for the bedroom and bathroom: 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Floor plan**, choose **Connections**\. 

1. In the **Connections** pane, choose **Add connection**\. 

1. In the **Desired connections** pane, select **Opening** for **Connection type** and then select a room for **Location 1** and **Location 2**\. For example, "My Living Room" and "My Kitchen"\. 

1. Choose **Save** to save desired connections\. 

1. Repeat to add a **Door** as a desired connection between two other locations\. For example, "My Bedroom" and "My Bathroom"\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"DesiredConnections": [
  {
    "Location": [ "My Living Room", "My Kitchen" ],
    "ConnectionType": "Opening"
  },
  {
    "Location": [ "My Bedroom", "My Bathroom" ],
    "ConnectionType": "Doorway"
  }
]
```

------

Valid number of connections per room is 4 and a maximum of one opening connection for each pair of rooms\.

## Requesting a Wide Floor Plan Footprint<a name="worlds-creating-task-request-wide-footprint"></a>

If you want a longer or wider floor plan layout that affects all of the rooms, you can request a `DesiredAspectRatio` for the `Footprint`\. Simulation WorldForge uses this preference to influence the overall shape and positions of the rooms so the floor plan better fits the requested footprint aspect ratio\. The desired aspect ratio is optional and defaults to a square\. 

The following examples overrides the default square ratio \(1:1\) to a prefer a wider layout where all of the rooms are more likely to be stretched and placed to create a non\-square footprint: 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Floor plan**, choose **World dimensions**\. 

1. In the **World dimensions** pane, under **Desired apsect ratio**, specify a **Width ** of `1` and a **Length** of `4`\. 

1. Choose **Save** to save the new room\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Footprint": {
  "DesiredAspectRatio": { 
    "x": 1, "y": 4 
  }
}
```

------

The valid range for `DesiredAspectRatio` is a range from 1:4 to 4:1\. 

## Requesting a Custom Ceiling Height<a name="worlds-creating-task-custom-ceiling-height"></a>

The floor plan ceiling height determines the height of the walls for all the rooms\. The default ceiling height is 2\.4 meters\. In this example, we override the default to 3\.2 meters: 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Floor plan**, choose **World dimensions**\. 

1. In the **World dimensions** pane, specify a **Ceiling height** of `3.2`\. 

1. Choose **Save** to save the new room\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Ceiling": {
  "Height": 3.2
}
```

------

## Specifying the Same Material Types to Floors in Different Rooms<a name="worlds-creating-task-same-material-floors"></a>

Use either room types or room names and list multiple rooms for the interior flooring section\. In the following example, all of the bedrooms, living rooms and dining rooms will have a random floorboard material assigned\. 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Interiors**, choose **Flooring**\. 

1. In the **Flooring** pane, choose **Add flooring**\. 

1. In the **Custom flooring** pane, specify a flooring **Set name**\. For example, "Flooring Material Set 1"\. 

1. Under **Filter type**, choose **By room type**\. 

1. Under **Room types**, select **Bedrooms**, **Living rooms**, and **Dining rooms**\. 

1. Under **Custom flooring**, choose **Add material** and then choose **Floorboard**\. 

1. Choose **Save** to save the flooring set\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Flooring": {
  "MaterialSets": [
    {
      "Name": "Flooring Material Set 1",
      "TargetSet": {
        "RoomTypes": [ "Bedroom", "Living", "Dining" ]
      },
      "SampleSet": {
        "MaterialTypes": [ "Floorboards" ]
      }
    }
  ]
}
```

------

## Specifying Different Material Types to Floors Between Rooms of the Same Type<a name="worlds-creating-task-different-material-floors"></a>

In the following example, all of the bedrooms, living rooms and dining rooms will have a random floorboard material assigned except for “Bedroom 3”\. It will be assigned a random carpet material\. 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Interiors**, choose **Flooring**\. 

1. In the **Flooring** pane, choose **Add flooring**\. 

1. In the **Custom flooring** pane, specify a flooring **Set name**\. For example, "Flooring Material Set 1"\. 

1. Under **Filter type**, choose **By room type**\. 

1. Under **Room types**, select **Bedrooms**, **Living rooms**, and **Dining rooms**\. 

1. Under **Custom flooring**, choose **Add material** and then choose **Floorboard**\. 

1. Choose **Save** to save the flooring set\. 

1. In the **Flooring** pane, choose **Add flooring**\. 

1. In the **Custom flooring** pane, specify a flooring **Set name**\. For example, "Flooring Material Set for Bedroom 3"\. 

1. Under **Filter type**, choose **By room name**\. 

1. Under **Room name**, select a room name\. For example, "Bedroom 3"\. 

1. Under **Custom flooring**, choose **Add material** and then choose **Carpet**\. 

1. Choose **Save** to save the flooring set\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Flooring": {
  "MaterialSets": [
    {
      "Name": "Flooring Material Set 1",
      "TargetSet": {
        "RoomTypes": [ "Bedroom", "Living", "Dining" ]
      },
      "SampleSet": {
        "MaterialTypes": [ "Floorboards" ]
      }
    },
    {
      "Name": "Flooring Material Set for Bedroom 3",
      "TargetSet": {
        "RoomNames": [ "Bedroom 3" ]
      },
      "SampleSet": {
        "MaterialTypes": [ "Carpet" ]
      }
    }
  ]
}
```

------

## Specifying More and Less Furniture in Rooms<a name="worlds-creating-task-furniture-more-less"></a>

You can specify how densely furniture is spaced by room names or room types\. By default, rooms are randomly furnished with moderate spacing\. In the following example, all bedrooms are randomly furnished with dense spacings\. The living room and dining room are furnished sparsely\. All other rooms are furnished by default\. 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Interiors**, choose **Furniture**\. 

1. In the **Furniture** pane, choose **Add custom furniture**\. 

1. In the **Custom furniture** pane, specify a custom furniture **Set name**\. For example, "Dense Furniture Arrangement"\. 

1. Under **Filter type**, choose **By room type**\. 

1. Under **Room types**, select **Bedrooms**\. 

1. Toggle **Override furniture** to use default furniture\. 

1. Under **Furniture density**, choose **Dense**\. 

1. Choose **Save** to save the furniture set\. 

1. In the **Furniture** pane, choose **Add custom furniture**\. 

1. In the **Custom furniture** pane, specify a custom furniture **Set name**\. For example, "Sparse Furniture Arrangement"\. 

1. Under **Filter type**, choose **By room name**\. 

1. Under **Room names**, select the rooms you want to have sparse furniture density\. For example, "My Living Room" and "My Dining Room"\. 

1. Toggle **Override furniture** to use default furniture\. 

1. Under **Furniture density**, choose **Sparse**\. 

1. Choose **Save** to save the furniture set\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Furniture": {
  "FurnitureArrangements": [
    {
      "Name": "Dense Furniture Arrangement",
      "TargetSet": {
        "RoomTypes": [ "Bedroom" ]
      },
      "DesiredSpatialDensity": "Dense"
    },
    {
      "Name": "Sparse Furniture Arrangement",
      "TargetSet": {
        "RoomNames": [ "My Living Room", "My Dining Room" ]
      },
      "DesiredSpatialDensity": "Sparse"
    }
  ]
}
```

------

## Adding Specific Furniture Types to all Bedrooms and a Single Shared Living/Dining Room<a name="worlds-creating-task-furniture-single-bedroom"></a>

You can specify the types of furniture for a room by room names or room types\. In the following example, all bedrooms are moderately furnished with random beds, desks, dressers, and floor lamps\. The room “My living/dining room” is densely furnished with random dining tables, dining chairs, floor lamps, sofas, and coffee tables\. All other rooms are furnished by default\. 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Interiors**, choose **Furniture**\. 

1. In the **Furniture** pane, choose **Add custom furniture**\. 

1. In the **Custom furniture** pane, specify a custom furniture **Set name**\. For example, "Bedroom Furniture"\. 

1. Under **Filter type**, choose **By room type**\. 

1. Under **Room types**, select **Bedrooms**\. 

1. Ensure **Override furniture** is selected\. If it is not selected, Simulation WorldForge will use default furniture\. 

1. Under **Furniture types**, choose **Add furniture** and then select **Beds**, **Desks**, **Dressers**, and **Floorlamps**\. 

1. Choose **Save** to save the furniture set\. 

1. In the **Furniture** pane, choose **Add custom furniture**\. 

1. In the **Custom furniture** pane, specify a custom furniture **Set name**\. For example, "Living and Dining Furniture"\. 

1. Under **Filter type**, choose **By room name**\. 

1. Under **Room names**, select a room\. For example, "My living and dining room"\. 

1. Ensure **Override furniture** is selected\. If it is not selected, Simulation WorldForge will use default furniture\. 

1. Under **Furniture types**, choose **DiningTables**, **DiningChairs**, **FloorLamps**, **Sofas**, and **CoffeeTables**\. 

1. Under **Furniture density**, choose **Dense**\. 

1. Choose **Save** to save the furniture set\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Furniture": {
  "FurnitureArrangements": [
    {
      "Name": "Bedroom Furniture",
      "TargetSet": {
        "RoomTypes": [ "Bedroom" ]
      },
      "SampleSet": {
        "ModelTypes": [ 
          "Beds",
          "Desks",
          "Dressers",
          "FloorLamps"
        ]
      }
    }
    {
      "Name": "Living and Dining Furniture",
      "TargetSet": {
        "RoomNames": [ "My living and dining room" ]
      },
      "SampleSet": {
        "ModelTypes": [ 
          "DiningTables",
          "DiningChairs",
          "FloorLamps",
          "Sofas",
          "CoffeeTables"
        ],
        "DesiredSpatialDensity": "Dense"
      }
    }
  ]
}
```

------

## Specifying a Room without Furniture<a name="worlds-creating-task-no-furniture"></a>

Specify an empty list for the model set for the furnishing arrangement\. All other rooms are furnished by default: 

------
#### [ Using the console ]

1. In the **Simulation world template edit** screen, under **Interiors**, choose **Furniture**\. 

1. In the **Furniture** pane, choose **Add custom furniture**\. 

1. In the **Custom furniture** pane, specify a custom furniture **Set name**\. For example, "No furniture"\. 

1. Under **Filter type**, choose **By room name**\. 

1. Under **Room names**, select the rooms that you want to have no furniture\. For example, "My Spare Room"\. 

1. Ensure **Override furniture** is selected\. If it is not selected, Simulation WorldForge will use default furniture\. 

1. Under **Furniture types**, make sure no types are chosen\. 

1. Choose **Save** to save the furniture set\. 

------
#### [ Using the AWS CLI ]

**Example**  
You can use the following JSON in the `templateBody` as part of a call to `create-world-template`\.   

```
"Furniture": {
  "FurnitureArrangements": [
    {
      "Name": "No Furniture",
      "TargetSet": {
        "RoomNames": [ "My Spare Room" ]
      },
      "SampleSet": {
        "ModelTypes": []
      }
    }
  ]
}
```

------