## QGIS PLUGIN 2021-2022
Authors: Abhi Balijepalli, Logan Kleditz, Nuocheng Shen

> This could be available as an extension to the QGIS application.
> Here is the demo for one of the machine learning algorithm, random forest.
> Currently the program can only be run on google colab.
> Here you can upload training data in `.csv` formate for making a random forest model.
> The program will also create visualization to help users understand how to adjust the model. Now the program can provide a complete tree diagram and images of parameters with model accuracy.

### Notes:
- `Random_Forest_main.ipynb` is used to create a random forest model
- `evaluate_.parameters_in_Random_Forest.ipynb` Provide images of parameter and model accuracy changes after creating a model using random data.


### Required Software Packages:
  - google colabe (https://colab.research.google.com/?utm_source=scs-index)

### Libraries Used:
  ```
  google.colab   (https://colab.research.google.com/?utm_source=scs-index)
  pandas         (https://pandas.pydata.org/)
  numpy          (https://numpy.org/)
  sklearn        (https://scikit-learn.org/stable/)
  pydot
  ```

### How to run the project:
  1. Download the folder to the users desired location.
  2. Sign in to google colab (https://colab.research.google.com/?utm_source=scs-index) with Google account.
  3. Click run cell button for first cell.
  4. Click Choose Files
  5. Upload a `.csv` file with train data.
  6. Click run cell button for every cell.
  7. The visualization of the complete tree diagram is in Files named `randomtree.png`

### Unrealized Features:
```diff
-Not tested with real data!
```
When using real data, it is necessary to change the way in data analysis according to the way of recording.
QGIS doesn't seem to support import, need to rewrite the `Random_Forest_main.ipynb` and `evaluate_.parameters_in_Random_Forest.ipynb` into the main program.
