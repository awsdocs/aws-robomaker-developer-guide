# Sample World Templates in JSON<a name="worlds-creating-sample-templates-in-json"></a>

The `templateBody` \(simulation world template body\) is an input parameter of the [https://docs.aws.amazon.com/robomaker/latest/dg/API_CreateWorldTemplate.html](https://docs.aws.amazon.com/robomaker/latest/dg/API_CreateWorldTemplate.html)\. This parameter is a JSON\-formatted string\. The JSON specifies a simulation world template and contains the parameters Simulation WorldForge will use to generate worlds\. 

This section contains sample simulation world template bodies\. 

**Topics**
+ [One Bedroom House](#worlds-creating-sample-templates-in-json-one-bedroom-house)
+ [One room only](#worlds-creating-sample-templates-in-json-one-room)
+ [Two rooms](#worlds-creating-sample-templates-in-json-two-room)

## One Bedroom House<a name="worlds-creating-sample-templates-in-json-one-bedroom-house"></a>

The following example specifies a one bedroom house\. It specifies interior materials and furniture\. 

```
{
  "name": "OneBedroomHouse",
  "templateBody": {
    "Version": "1",
    "Buildings": [
      {
        "Floors": [
          {
            "Floorplan": {
              "Footprint": {
                "DesiredAspectRatio": {
                  "x": 1,
                  "y": 1
                }
              },
              "Ceiling": {
                "Height": 3
              },
              "Rooms": [
                {
                  "Type": "Bedroom",
                  "Name": "Bedroom",
                  "DesiredShape": {
                    "Area": 25,
                    "AspectRatio": {
                      "x": 1,
                      "y": 1.2
                    }
                  }
                },
                {
                  "Type": "Living",
                  "Name": "Living room",
                  "DesiredShape": {
                    "Area": 30,
                    "AspectRatio": {
                      "x": 1,
                      "y": 1.5
                    }
                  }
                },
                {
                  "Type": "Bathroom",
                  "Name": "Bathroom",
                  "DesiredShape": {
                    "Area": 10,
                    "AspectRatio": {
                      "x": 1,
                      "y": 1.5
                    }
                  }
                },
                {
                  "Type": "Kitchen",
                  "Name": "Kitchen",
                  "DesiredShape": {
                    "Area": 15,
                    "AspectRatio": {
                      "x": 1.5,
                      "y": 1
                    }
                  }
                }
              ],
              "DesiredConnections": [
                {
                  "Location": [
                    "Bathroom",
                    "Living room"
                  ],
                  "ConnectionType": "Doorway"
                },
                {
                  "Location": [
                    "Living room",
                    "Kitchen"
                  ],
                  "ConnectionType": "Opening"
                },
                {
                  "Location": [
                    "Bedroom",
                    "Living room"
                  ],
                  "ConnectionType": "Doorway"
                }
              ]
            },
            "Interior": {
              "Flooring": {
                "MaterialSets": [
                  {
                    "Name": "Floorboard room types",
                    "TargetSet": {
                      "RoomTypes": [
                        "Kitchen"
                      ]
                    },
                    "SampleSet": {
                      "MaterialTypes": [
                        "Floorboards"
                      ]
                    }
                  },
                  {
                    "Name": "Carpet room types",
                    "TargetSet": {
                      "RoomTypes": [
                        "Living",
                        "Bedroom"
                      ]
                    },
                    "SampleSet": {
                      "MaterialTypes": [
                        "Carpet"
                      ]
                    }
                  },
                  {
                    "Name": "Bathroom",
                    "TargetSet": {
                      "RoomNames": [
                        "Bathroom"
                      ]
                    },
                    "SampleSet": {
                      "MaterialTypes": [
                        "Parquetry"
                      ]
                    }
                  }
                ]
              },
              "Walls": {
                "MaterialSets": [
                  {
                    "Name": "Brick room types",
                    "TargetSet": {
                      "RoomTypes": [
                        "Living"
                      ]
                    },
                    "SampleSet": {
                      "MaterialTypes": [
                        "Brick"
                      ]
                    }
                  },
                  {
                    "Name": "Tiles room types",
                    "TargetSet": {
                      "RoomTypes": [
                        "Bathroom"
                      ]
                    },
                    "SampleSet": {
                      "MaterialTypes": [
                        "Tiles"
                      ]
                    }
                  }
                ]
              },
              "Furniture": {
                "FurnitureArrangements": [
                  {
                    "Name": "Dense furniture room types",
                    "TargetSet": {
                      "RoomTypes": [
                        "Living",
                        "Bedroom",
                        "Kitchen",
                        "Bathroom"
                      ]
                    },
                    "DesiredSpatialDensity": "Dense"
                  }
                ]
              }
            }
          }
        ]
      }
    ]
  }
}
```

## One room only<a name="worlds-creating-sample-templates-in-json-one-room"></a>

The following example specifies a one bedroom house\. It specifies interior furniture\. 

```
{
  "Version": "1",
  "Buildings": [
    {
      "Floors": [
        {
          "Floorplan": {
            "Footprint": {
              "DesiredAspectRatio": {
                "x": 1,
                "y": 1
              }
            },
            "Ceiling": {
              "Height": 3
            },
            "Rooms": [
              {
                "Type": "Bedroom",
                "Name": "Bedroom",
                "DesiredShape": {
                  "Area": 40,
                  "AspectRatio": {
                    "x": 1,
                    "y": 1.61
                  }
                }
              }
            ],
            "DesiredConnections": []
          },
          "Interior": {
            "Furniture": {
              "FurnitureArrangements": [
                {
                  "Name": "Bedroom furniture",
                  "TargetSet": {
                    "RoomNames": [
                      "Bedroom"
                    ]
                  },
                  "DesiredSpatialDensity": "Dense"
                }
              ]
            }
          }
        }
      ]
    }
  ]
}
```

## Two rooms<a name="worlds-creating-sample-templates-in-json-two-room"></a>

The following example specifies a one bedroom house\. Simulation WorldForge will determine details including floor material, wall material, furniture placement, and connectivity\. 

```
{
  "name": "TwoRooms",
  "templateBody": {
    "Version": "1",
    "Buildings": [
      {
        "Floors": [
          {
            "Floorplan": {
              "Footprint": {
                "DesiredAspectRatio": {
                  "x": 1,
                  "y": 1
                }
              },
              "Ceiling": {
                "Height": 3
              },
              "Rooms": [
                {
                  "Type": "Living",
                  "Name": "Living room",
                  "DesiredShape": {
                    "Area": 30,
                    "AspectRatio": {
                      "x": 1,
                      "y": 1.5
                    }
                  }
                },
                {
                  "Type": "Dining",
                  "Name": "Dining room",
                  "DesiredShape": {
                    "Area": 30,
                    "AspectRatio": {
                      "x": 1,
                      "y": 1.5
                    }
                  }
                }
              ],
              "DesiredConnections": []
            },
            "Interior": {}
          }
        ]
      }
    ]
  }
}
```