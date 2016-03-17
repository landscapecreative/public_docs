# Preparing a DWG file for Landscape Creative

### Example DWG Import Assets
- [Ten Property Lot Phase](https://docs.google.com/uc?authuser=0&id=0B3rYq08ASaWWSmRFcVRWSXhycEU&export=download)

### File Versions

Landscape Creative accepts the following `.DWG` file versions. 

- R15 (R2000) Test
- R18 (R2004)
- R21 (R2007)
- R24 (R2010)
- R27 (R2013)

### General Requirements and Considerations

- Y Axis points north
- All blocks including the main drawing must be properly scaled using inches as a unit of measure within block definitions. 
- Line precision is important and required for the successful importation of CAD files. Lines of the same type should form precise enclosures or corner points.
    
### File Layers

The following file layers are required for import into the Landscape Creative system. One file can be one lot, a phase of lots, or an entire community. 

####Required Layers

- `Curb`
    - The perimeter lines of all curbs. 
- `Curb-Block-Curbtop`
    - Curb elevations as blocks with the following attributes:
        - `ELEV`: Relative curb elevation in feet as an integer. 
- `Driveway`
    - The perimeter lines of all driveways.
- `Lot-Block-Highpoint`
    - The lot high point with the following required attributes:
        - `ELEV`: Relative high point elevation in feet as an integer.
- `Lot-Perimeter`
    - The perimeter lines of each lot.  
- `Model-Block`
    - The Block containing all model information including `Model`, `Model-Door`, `Model-Window`, and `Model-Block-Info` 
- `Model`
    - The perimeter lines of each model within the model block.  
- `Model-Door`
    - Single lines on the model perimeter depicting the placement and width of each door.
- `Model-Window`
    - Single lines on the model perimeter depicting the placement and width of each window.
- `Model-Block-Info`
    - A block contained in the center of the model with various required information. The required attributes are:
        - `LOT`: Integer. The lot number. This is combined with the value from street name to create an address for each home buyer account. 
        - `PAD`: Integer. The pad elevation in feet of the house or building model.
        - `PLAN`: Text. The plan number of the model plan that goes on the lot.
        - `FF [optional]`: Integer. The elevation of the plan finished floor.

####Optional Layers
- `Lot-Perimeter-Row`
    - If the street facing lot perimeter is a single continuous line, place it on this layer and it will be joined with the `Lot-Perimeter` layer to form enclosed lots.
- `Enclosure-Blockwall`
    - If there are any divisional block walls in the plan, place the lines on this layer.
- `Surface-Patio`
    - If there are any poured patios on the property, this layer contains the lines that form the patio boundary.
- `Street`
    - The perimeter lines of each street surrounding the property. 
- `Street-Name`
    - A text layer with the name of each street. Each street name must be completely enclosed by a set of lines on the `street` layer.  
    
    