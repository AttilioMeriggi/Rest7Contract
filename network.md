# Network Endpoints
[Back to the list of all defined endpoints](endpoints.md)

## Read Author Graph
**GET /api/app/neo4j/authorngraph/<:uuid>?depth=<depth>**

```json
{
  "id": "4d68f32e-6122-428c-81a9-6bcf03d1abad",
  "name": "[Steve Smith]",
  "data": {
    "relation": ""
  },
  "children": [
    {
      "id": "8eda467a-2dae-4103-a3f6-d5059f6afe52",
      "name": "[Claire Williams]",
      "data": {
        "relation": "dc_title:[Web Research], dc_type:[Magazine]"
      },
      "children": []
    },
    {
      "id": "5fa18343-13b8-417c-ad61-618088144546",
      "name": "[Tom Taylor]",
      "data": {
        "relation": "dc_title:[Web Research], dc_type:[Magazine]; dc_title:[Software Research], dc_type:[Item]; dc_title:[Cluster Analysis], dc_type:[Item]"
      },
      "children": [
        {
          "id": "6f4b6137-a238-46ca-b860-2c70978d7815",
          "name": "[Daniel Brown]",
          "data": {
            "relation": "dc_title:[Microeconomics], dc_type:[Item]"
          },
          "children": []
        },
        {
          "id": "8eda467a-2dae-4103-a3f6-d5059f6afe52",
          "name": "[Claire Williams]",
          "data": {
            "relation": "dc_title:[Web Research], dc_type:[Magazine]"
          },
          "children": []
        }
      ]
    }
  ]
}
```

The method is used to export a graph based on a data structure that can be easily displayed with 
[JavaScript InfoVis Toolkit](https://philogb.github.io/jit/)

The structure of an authorGraph json is
```
{
  "id": "4d68f32e-6122-428c-81a9-6bcf03d1abad",
  "name": "[Steve Smith]",
  "authorNGraphData": null,
  "children": [
    <authorGraph_01>,
    <authorGraph_02>,
    ...
  ]
}
```
that define a graph with a node [Steve Smith] with two child nodes <authorGraph_01> and <authorGraph_02>. The link from the root node and children is described by the authorNGraphData.relation field.

## Read Network Graph
**GET /api/eperson/epersons/<:uuid>?depth=<depth>?metadata=<metadata>&relationMetadata=<relationMetadata>**

```json
{
  "entityType": "Researcher",
  "metadata": {
    "dc_contributor_author": [
      "Steve Smith"
    ],
    "dc_contributor_editor": [
      "Steve Smith"
    ],
    "dc_relation_orgunit": [
      "Oxford University",
      "Roma Tre"
    ]
  },
  "relations": [
    {
      "type": "coauthor",
      "metadata": {
        "dc_title": [
          "Cluster Analysis"
        ],
        "dc_type": [
          "Item"
        ]
      },
      "target": {
        "entityType": "Publication",
        "metadata": {
          "dc_title": [
            "Cluster Analysis"
          ],
          "dc_type": [
            "Item"
          ]
        },
        "relations": [
          {
            "type": "coauthor",
            "metadata": {
              "dc_title": [
                "Cluster Analysis"
              ],
              "dc_type": [
                "Item"
              ]
            },
            "target": {
              "entityType": "Researcher",
              "metadata": {
                "dc_contributor_author": [
                  "Tom Taylor"
                ],
                "dc_contributor_editor": [
                  "Tom Taylor"
                ],
                "dc_relation_orgunit": [
                  "Oxford University"
                ]
              },
              "relations": [
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Software Research"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Software Research"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [],
                    "iddb": "5f1e17da-8a1b-4640-922c-46ee70aed071"
                  }
                },
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Microeconomics"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Microeconomics"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [
                      {
                        "type": "coauthor",
                        "metadata": {
                          "dc_title": [
                            "Microeconomics"
                          ],
                          "dc_type": [
                            "Item"
                          ]
                        },
                        "target": {
                          "entityType": "Researcher",
                          "metadata": {
                            "dc_contributor_author": [
                              "Daniel Brown"
                            ],
                            "dc_contributor_editor": [
                              "Richard King"
                            ],
                            "dc_relation_orgunit": [
                              "Berkeley University"
                            ]
                          },
                          "relations": [],
                          "iddb": "d5ed4470-8969-4a15-a0c3-5536e91edbf6"
                        }
                      }
                    ],
                    "iddb": "612d472f-a1b9-4a10-a6fe-d26266077ee3"
                  }
                },
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Web Research"
                    ],
                    "dc_type": [
                      "Magazine"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Web Research"
                      ],
                      "dc_type": [
                        "Magazine"
                      ]
                    },
                    "relations": [
                      {
                        "type": "coauthor",
                        "metadata": {
                          "dc_title": [
                            "Web Research"
                          ],
                          "dc_type": [
                            "Magazine"
                          ]
                        },
                        "target": {
                          "entityType": "Researcher",
                          "metadata": {
                            "dc_contributor_author": [
                              "Claire Williams"
                            ],
                            "dc_contributor_editor": [
                              "Claire Williams"
                            ],
                            "dc_relation_orgunit": [
                              "Bocconi",
                              "Sapienza"
                            ]
                          },
                          "relations": [],
                          "iddb": "853630d2-f04f-439d-b397-afbadf9ce80c"
                        }
                      }
                    ],
                    "iddb": "4d68f32e-6122-428c-81a9-6bcf03d1abad"
                  }
                }
              ],
              "iddb": "547a412a-9949-4c37-904c-df82b662b718"
            }
          }
        ],
        "iddb": "e3b73bf3-0517-4528-9a63-ae0ff56b54dc"
      }
    },
    {
      "type": "coauthor",
      "metadata": {
        "dc_title": [
          "Software Research"
        ],
        "dc_type": [
          "Item"
        ]
      },
      "target": {
        "entityType": "Publication",
        "metadata": {
          "dc_title": [
            "Software Research"
          ],
          "dc_type": [
            "Item"
          ]
        },
        "relations": [
          {
            "type": "coauthor",
            "metadata": {
              "dc_title": [
                "Software Research"
              ],
              "dc_type": [
                "Item"
              ]
            },
            "target": {
              "entityType": "Researcher",
              "metadata": {
                "dc_contributor_author": [
                  "Tom Taylor"
                ],
                "dc_contributor_editor": [
                  "Tom Taylor"
                ],
                "dc_relation_orgunit": [
                  "Oxford University"
                ]
              },
              "relations": [
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Cluster Analysis"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Cluster Analysis"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [],
                    "iddb": "e3b73bf3-0517-4528-9a63-ae0ff56b54dc"
                  }
                },
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Microeconomics"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Microeconomics"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [
                      {
                        "type": "coauthor",
                        "metadata": {
                          "dc_title": [
                            "Microeconomics"
                          ],
                          "dc_type": [
                            "Item"
                          ]
                        },
                        "target": {
                          "entityType": "Researcher",
                          "metadata": {
                            "dc_contributor_author": [
                              "Daniel Brown"
                            ],
                            "dc_contributor_editor": [
                              "Richard King"
                            ],
                            "dc_relation_orgunit": [
                              "Berkeley University"
                            ]
                          },
                          "relations": [],
                          "iddb": "d5ed4470-8969-4a15-a0c3-5536e91edbf6"
                        }
                      }
                    ],
                    "iddb": "612d472f-a1b9-4a10-a6fe-d26266077ee3"
                  }
                },
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Web Research"
                    ],
                    "dc_type": [
                      "Magazine"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Web Research"
                      ],
                      "dc_type": [
                        "Magazine"
                      ]
                    },
                    "relations": [
                      {
                        "type": "coauthor",
                        "metadata": {
                          "dc_title": [
                            "Web Research"
                          ],
                          "dc_type": [
                            "Magazine"
                          ]
                        },
                        "target": {
                          "entityType": "Researcher",
                          "metadata": {
                            "dc_contributor_author": [
                              "Claire Williams"
                            ],
                            "dc_contributor_editor": [
                              "Claire Williams"
                            ],
                            "dc_relation_orgunit": [
                              "Bocconi",
                              "Sapienza"
                            ]
                          },
                          "relations": [],
                          "iddb": "853630d2-f04f-439d-b397-afbadf9ce80c"
                        }
                      }
                    ],
                    "iddb": "4d68f32e-6122-428c-81a9-6bcf03d1abad"
                  }
                }
              ],
              "iddb": "547a412a-9949-4c37-904c-df82b662b718"
            }
          }
        ],
        "iddb": "5f1e17da-8a1b-4640-922c-46ee70aed071"
      }
    },
    {
      "type": "coauthor",
      "metadata": {
        "dc_title": [
          "Web Research"
        ],
        "dc_type": [
          "Magazine"
        ]
      },
      "target": {
        "entityType": "Publication",
        "metadata": {
          "dc_title": [
            "Web Research"
          ],
          "dc_type": [
            "Magazine"
          ]
        },
        "relations": [
          {
            "type": "coauthor",
            "metadata": {
              "dc_title": [
                "Web Research"
              ],
              "dc_type": [
                "Magazine"
              ]
            },
            "target": {
              "entityType": "Researcher",
              "metadata": {
                "dc_contributor_author": [
                  "Claire Williams"
                ],
                "dc_contributor_editor": [
                  "Claire Williams"
                ],
                "dc_relation_orgunit": [
                  "Bocconi",
                  "Sapienza"
                ]
              },
              "relations": [],
              "iddb": "853630d2-f04f-439d-b397-afbadf9ce80c"
            }
          },
          {
            "type": "coauthor",
            "metadata": {
              "dc_title": [
                "Web Research"
              ],
              "dc_type": [
                "Magazine"
              ]
            },
            "target": {
              "entityType": "Researcher",
              "metadata": {
                "dc_contributor_author": [
                  "Tom Taylor"
                ],
                "dc_contributor_editor": [
                  "Tom Taylor"
                ],
                "dc_relation_orgunit": [
                  "Oxford University"
                ]
              },
              "relations": [
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Cluster Analysis"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Cluster Analysis"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [],
                    "iddb": "e3b73bf3-0517-4528-9a63-ae0ff56b54dc"
                  }
                },
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Software Research"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Software Research"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [],
                    "iddb": "5f1e17da-8a1b-4640-922c-46ee70aed071"
                  }
                },
                {
                  "type": "coauthor",
                  "metadata": {
                    "dc_title": [
                      "Microeconomics"
                    ],
                    "dc_type": [
                      "Item"
                    ]
                  },
                  "target": {
                    "entityType": "Publication",
                    "metadata": {
                      "dc_title": [
                        "Microeconomics"
                      ],
                      "dc_type": [
                        "Item"
                      ]
                    },
                    "relations": [
                      {
                        "type": "coauthor",
                        "metadata": {
                          "dc_title": [
                            "Microeconomics"
                          ],
                          "dc_type": [
                            "Item"
                          ]
                        },
                        "target": {
                          "entityType": "Researcher",
                          "metadata": {
                            "dc_contributor_author": [
                              "Daniel Brown"
                            ],
                            "dc_contributor_editor": [
                              "Richard King"
                            ],
                            "dc_relation_orgunit": [
                              "Berkeley University"
                            ]
                          },
                          "relations": [],
                          "iddb": "d5ed4470-8969-4a15-a0c3-5536e91edbf6"
                        }
                      }
                    ],
                    "iddb": "612d472f-a1b9-4a10-a6fe-d26266077ee3"
                  }
                }
              ],
              "iddb": "547a412a-9949-4c37-904c-df82b662b718"
            }
          }
        ],
        "iddb": "4d68f32e-6122-428c-81a9-6bcf03d1abad"
      }
    }
  ],
  "iddb": "72ab2970-de17-4797-a307-49c5921ce351"
}
```

The method is used to export the network graph starting from a given node without circular paths.
The structure is based on DSpaceNode and DSpaceRelation json.
The DSpaceNode json describe a node of the network graph with its metadata.
The DSpaceRelation describe a relation from a DSpaceNode and a target node.

The structure of an DSpaceNode json is
```
"entityType": "Researcher",
  "metadata": {
    "dc_contributor_author": [
      "Steve Smith"
    ],
    "dc_contributor_editor": [
      "Steve Smith"
    ],
    "dc_relation_orgunit": [
      "Oxford University",
      "Roma Tre"
    ]
  },
  relation: [
    <DSpaceRelation>
  ],
  "iddb": "72ab2970-de17-4797-a307-49c5921ce351"
}
```

The structure of DSpaceRelation is
```
{
  "type": "coauthor",
  "metadata": {
    "dc_title": [
      "Cluster Analysis"
    ],
    "dc_type": [
      "Item"
    ]
  },
  "target": "<DSpaceNode>"
}
```

## Post Method

No post method are required

## Delete Method

No delete method are required

## Patch operations

No patch operation are required

