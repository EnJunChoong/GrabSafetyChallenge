
# Safety | Grab AI For S.E.A Challenge
<img src="https://i.imgur.com/EDnvnsh.jpg">
<hr>


## INTRODUCTION
This repository is created as a effort to participate in the challenge. Participants are required to upload their work to a repository of their choice, and make it available by the time of submission. 
<hr width = '75%'>


### Dataset
Dataset is downloaded from the <a href="https://www.aiforsea.com/safety">competition webpage</a>:<br> <a href="https://s3-ap-southeast-1.amazonaws.com/grab-aiforsea-dataset/safety.zip">https://s3-ap-southeast-1.amazonaws.com/grab-aiforsea-dataset/safety.zip</a><br>
*Link may not work after competition is closed.*

Features data file contains features below:
<div>
<table style="float: left;" >
<tbody style="align: left"><tr>
<td><strong>Field</strong></td>
<td><strong>Description</strong></td></tr>
<tr><td>bookingID</td>
<td>trip id</td></tr>
<tr><td>Accuracy</td>
<td>accuracy inferred by GPS in meters</td></tr>
<tr><td>Bearing</td>
<td>GPS bearing in degree</td></tr>
<tr><td>acceleration_x</td>
<td>accelerometer reading at x axis (m/s2)</td></tr>
<tr><td>acceleration_y</td>
<td>accelerometer reading at y axis (m/s2)</td></tr>
<tr><td>acceleration_z</td>
<td>accelerometer reading at z axis (m/s2)</td></tr>
<tr><td>gyro_x</td>
<td>gyroscope reading in x axis (rad/s) (m/s2)</td></tr>
<tr><td>gyro_y</td>
<td>gyroscope reading in y axis (rad/s) (m/s2)</td></tr>
<tr><td>gyro z</td>
<td>gyroscope reading in z axis (rad/s) (m/s2)</td></tr>
<tr><td>second</td>
<td>time of the record by number of seconds</td></tr>
<tr><td>Speed</td>
<td>speed measured by GPS in m/s</td></tr>
</tbody>
</table>
</div><br>
<div style = "clear:both;"></div><br><br>

Labels data file contains bookingID and label:
<div>
<table style="float: left;">
<tbody style="align: left"><tr>
<td><strong>Field</strong></td>
<td><strong>Description</strong></td></tr>
<tr><td>bookingID</td>
<td>trip id</td></tr>
<tr><td>label</td>
<td>label = 1 indicate dangerous driving. 0 for false</td></tr>
</tbody>
</table>
</div>

<div style = "clear:both;"></div>
<hr>

## REPOSITORY

<hr width = '75%'>

### Jupyter Notebooks
In the parent folder, you will see three Jupyter Notebook files:<br><br>
**1) ModelTraining.ipynb**<br>
This is the file where competition dataset is loaded , explored feature engineered and modeled. There are explaination and justification on each steps from the start to the end. This is the file to understand the manipulation done on the code leading ultimately to machine learning model output. <br><br>
At the end, a machine learning model is saved to Trained_Model folder as <Trained_Model_LGB.sav>. <br><br>This will be used by competition host in the another Jupyter Notebook File <HoldOutTestValidation.ipynb> for testing on the holdout test set only available to them.

**2) HoldOutTestValidation.ipynb**<br>
This Jupyter Notebook file is created for the ease of the competion host to load the Trained Model, perform all the necessesary cleaning and manipulation on the hold out test set. Then, finally validating the performance of the trained model on the hold out test set. <br><br>
In ExampleTestSet folder, two csv files were created as a mock test dataset to be used in this jupyter notebook to verify the usability. Competition host will use their private holdout testset for validating the performance of the trained model

**3) README.ipynb**<br>
This is the Jupyter Notebook for generating the README.md for the github repository
<hr width = '75%'>

### Folders
There are 2 folders in the repository:<br>
**1)GrabSafetyDataset**<br>
This folder serve as the storage place for competition dataset including 10 features csv files and 1 labels csv file.
Due to the 100mb per file limitation of github repository, all 10 features files are not uploaded. Please download dataset from <a href="https://www.aiforsea.com/safety">competition webpage</a>.

**1) Trained_Model**<br>
This folder contains the saved Model that was trained and outputed in ModelTraining.ipynb

**2) ExampleTestSet**<br>
This folder contains the mock test dataset for verifying usability of the HoldOutTestValidation.ipynb

<hr>

## INSTRUCTION
<hr width = '75%'>

### Run ModelTraining.ipynb
#### Step1 Ensure all dependencies are installed with correct version
Please see below for the required python modules and their respective versions that were used in the Jupyter Notebooks. 

<table style="float: left;">
<tbody style="float: left"><tr>
<td><strong>Modules&nbsp;</strong></td>
<td><strong>Version&nbsp;</strong></td></tr>
<tr><td>numpy&nbsp;</td>
<td>1.16.0&nbsp;</td></tr>
<tr><td>&nbsp;pandas</td>
<td>0.23.4&nbsp;</td></tr>
<tr><td>&nbsp;matplotlib</td>
<td>3.0.2&nbsp;</td></tr>
<tr><td>&nbsp;seaborn</td>
<td>0.9.0&nbsp;</td></tr>
<tr><td>&nbsp;sklearn</td>
<td>0.20.1&nbsp;</td></tr>
<tr><td>tensorflow</td>
<td>2.0.0-alpha0</td></tr>
<tr><td>lightgbm</td>
<td>2.2.3</td></tr>
</tbody>
</table>

<div style = "clear:both;"></div>


#### Step2: Modify read_csv directory accordingly for features and labels csv. 
There should be 10 features csv files and 1 label csv file as provided. <br>
<img src="https://i.imgur.com/OApUYs1.png">

#### Step3: Sit back, Relax and let the code run for a good hour. 


#### Step4: Output and save machine learning model to folder.
Currently, the machine learning model is already available as <Trained_Model_LGB.sav> in the Trained_Model folder. 
But if you wish to output and save the model again, you can do so by following uncommenting the codes in the notebook.
<div><img src="https://i.imgur.com/tWkcS0q.png"></div>

<div style = "clear:both;"></div>
<hr width = '75%'>



###  Run HoldOutTestValidation.ipynb
#### Step1: Modify read_csv directory
<img src="https://i.imgur.com/Lzyw45P.png">

#### Step2: Sit back, Relax and let the code run. Please allow some time for large files

#### Step3: Brain the result (Figure below is an example)
<div><img src="https://i.imgur.com/doidvZq.png" align="left"></div>

<div style = "clear:both;"></div>
<hr>



```python

```
