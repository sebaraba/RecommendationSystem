## User Guide

The program can be used with two different functionalities. 
First it can be used to `generate predictions`, and also to `visualise predictions performance`. 
Two separate files encapsulates the two final versions. 

Clone the project on your PC using the following command in the terminal:

`git clone` https://github.com/sebaraba/LinkPrediction.git

The main version of the application will be available on your personal computer. 

## Running the system

In order to run the first functionality of the app you need to open the project's directory
in your terminal and run the following command:

`python recommender.py name-of-the-dataset name-of-the-algorithm threshold`

The first argument stands for the dataset to be used for the predictions.
The only dataset that we provide on github is the: *mock-dataset.csv*. This is just a mock dataset
containing only 48 users and, 580 items and 990 transactions. It is enough for a demonstration of the prototype, but for the
research purposes this dataset is scarce. 

The next argument specifies the algorithm. The current state of the system provides three link predictions algorithms to choose from. 
Just write tone of the following names, as the second argument of the command to use the desired index:

	- `common_neighbours`

	- `resource_allocation`

	- `jaccard_coefficient`

Finaly depending on the algorithm, a range of optimal threshold values for the dataset we provide in this zip file (data.csv) :

	- common neighbour index: because this measure counts common neighbours, a relatively optimal is a number in the range 250 : 450;

	- resource allocation index: because this measure divides equal units of resource to all its neighbours, a relatively optimal
        value is a float in the range 3 : 5.6;

	- jaccard index: because this measure penalises the number of common neighbours by the number of neighbours that are not
        common, a relatively optimal range is float value between: 0.14 : 0.38;


## Running Commands Examples

One specific example of how the first functionality can be run:
Assuming python 3 is the default version installed on the pc:

`python recommender.py data.csv common_neighbours 300`


For the second functionality of the recommender. Namelly the visualisation feature, one user only needs to run the following command:

`python recommenderSystem.py`

## Add New Datasets

Following a GUI each enables users to brows the folders in their computer and select which dataset they want to run. However, at this stage the dataset import function is still pretty modular. What you need to do is to make sure the dataset is in `csv` format and put it in the `data` directory. You just need to adjust the `loadDataSet` method in order to make sure it selects the appropiate **user IDs** and **item IDs** columns from the provided `csv file`.