## QGIS PLUGIN 2021-2022
Authors: Abhi Balijepalli, Logan Kleditz, Nuocheng Shen

>This is the actual plugin that will interface with the QGIS app, this can be added to the plugin folder of your app.  
You can use the `data` tab to decide which layer is your data, training, and make an `shp ROI file` and select the directory where you want the results. 
The algorithms tab can be used to decide which algorithms to `run`.
The `run` button will run the selected algorithm with the selected data.

### Notes:
- `readmleroisours.py` is our rendition of the Maximum likelihood algorithm from Mason in the year prior.
- `reed_canary_project.py` is the script that runs the different dialogue boxes that make up the UI and do some internal logic
- `reed_canary_project_dialog.py` add your new UI files to this script to use any new UI files in the main script


### Required Software Packages:
  - QGIS 3.16
  - Python v 3.9.5 (should come installed with QGIS, but make sure it is downloaded and in the path directory if on Windows)
  - Required Libraries are installed with the QGIS installation package, nothing more should be required
### Libraries Used:
  ```
  qgis.gui
  qgis.PyQt *
  qgis
  PyQt5
  PIL
  numpy
  os
  osgeo
  Collections
  sys
  time
  random
  ```

### How to run the project:
  1. Download the folder to the users desired location
  2. Place the downloaded content into the `QGIS\QGIS3\profiles\default\python\plugins` folder
  3. Launch QGIS, the `plugin` button should appear at the top bar of the application window.
  4. The plugin does not load desired layers into QGIS, you will have to manually do this from the file explorer on the left side of the application window.
  5. From here you just need to select your desired data `layer (.tif)`, `training data layer (.shp)`, and then make a new `.shp` that allows you to draw roi circles. 
  > These circles are what will be used to “classify” data, 
      and is used in the maximum-likelihood algorithm. You cannot have class 0, only class 1-N.
  6. Select the directory you wish output to be saved to. This requires you to have something in the file name box due to QGIS’ limitation, this will not name a new file, and is just a quirk of the application.
  7. Once all data is selected, select OK and select the algorithm button. From here you can select your desired algorithm, but only the maximum-likelihood algorithm is somewhat functional. 
  8. Select RUN to begin running the algorithm.

### Unrealized Features:
Maximum-likelihood **does not work as intended**, it is not the ML algorithm, it is a strange image classification algorithm that is masquerading as the ML algorithm.

It requires each wavelength of light to be in a separate file, but this is not how most mulit-spectral `.tif` files are. 

So there needs to be a massive overhaul of the algorithm to make the algorithm work with a single data `.tif` file that has multiple bands of light on it. 

Also it currently only works for 4 specific wavelengths of light, this needs to be changed to allow for any wavelengths of light.