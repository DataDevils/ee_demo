# Quickstart to Google Earth Engine



## What is Earth Engine?

* Access to enormous archive of remotely sensed imagery
* Analytical environment to process imagery (interface + horsepower)



## Access to EE

- Getting an account: https://signup.earthengine.google.com/
- The JavaScript interface: https://developers.google.com/earth-engine/playground
- The Python API:
  - Google's instructions: https://developers.google.com/earth-engine/python_install
  -  [Instructions for Installation on Jupyter](Python-API-Install.md)



## Intro to JS interface

- Link: https://code.earthengine.google.com/
- The interface: 
- ![Components](https://developers.google.com/earth-engine/images/Playground_diagram_v3_crop.png)
- [Help](https://developers.google.com/earth-engine/), [Reference](https://developers.google.com/earth-engine/api_docs) & [Tutorials](https://developers.google.com/earth-engine/tutorials)
- **Connect** to Examples repository: 
  - https://code.earthengine.google.com/?accept_repo=EE101-B
- **Create** your own repository: `New` >`Repository`
  - Yes these are Git repositories! (Stored on Google's server)



## Diving in!

### 1 - Landsat Composite

- **Copy** `1 - Landsat Composite ` to your repository (by click and drag) and open it

- **<u>Run** script and interact</u>

  - Zoom map
  - Change Image symbology (Change bands to 5-4-3; stretch to 98%)
  - Move the map around: calculations on the fly

- <u>Examine script</u>

  - Objects: 
    - Geometry feature (vector)
    - Image collection (raster stack)
  - Filters:
    - Date
    - Location
  - Reducer algorithm: Simple Composite (specific to Landsat)
  - Map Layer

- <u>Modify script</u>:

  - Search for information on your image collection:

    - Paste `LANDSAT/LC8_L1T` into the search box...
    - [Result](https://code.earthengine.google.com/dataset/LANDSAT/LC8_L1T) shows info:
      - Revisit interval...
      - Bands & resolution
      - Image Collection ID
      - That it's *deprecated*! (More info: https://developers.google.com/earth-engine/landsat)
      - Side note: {TOA, surface reflectance, cloud score, simple composites}

  - Edit the default bands to 5 4 3 and rename the layer:

    `Map.addLayer(composite, {bands: ["B5", "B4", "B3"], min:0, max: 0.3}, "False Color")`

  - Add a new point geometry feature:

    Insert  `var geometry = ee.Geometry.Point([-78.861902,35.8760964])` before  `var landsat`...



### Adding images to your workspace

- Search for Elevation; View info for [*GTED2010: Global Multi-resolution Terrain Elevation Data 2010*](https://code.earthengine.google.com/dataset/USGS/GMTED2010)

  - What is it's resolution? (what is an ArcSecond?)
  - What is its Image ID? (Note, it's an *Image* ID, not an *Image Collection* ID)

- Click `Import` and note changes in your script:

  `var image:  Image "GMTED2010: ...`

- Rename the variable from `image` to `GMTED`

- View the image in your display

  - Add `Map.addLayer(GMTED,{},"Elevation")`

- Edit the data stretch:

  - `Map.addLayer(GMTED,{'min':30, 'max':200},"Elevation")`

- EXERCISE: 

  - Add and view the US National Elevation Dataset in your workspace
  - Alter your code to show Landsat's Band 10, stretching it from 250 to 300

- Add image by its Image ID (GlobCover: Global Land Cover)

  - Search for Land Cover, view info for [GlobCover](https://code.earthengine.google.com/dataset/ESA/GLOBCOVER_L4_200901_200912_V2_3), get the Image ID (`ESA/GLOBCOVER_L4_200901_200912_V2_3 `)
  - `var globcov = ee.Image(ESA/GLOBCOVER_L4_200901_200912_V2_3)`



### Image Collections & filters

- Filtering on time
- Filtering on location
- Filtering bands
- Reducers



### Image analysis

- Derived images



### Feature Extraction

- JavaScript
- Python

