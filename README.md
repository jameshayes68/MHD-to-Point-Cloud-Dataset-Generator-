# MHD-to-Point-Cloud-Dataset-Generator-
STL-to-Point-Cloud-Dataset-Generator-
There are a number of freely available datasets of MHD files (for example https://luna16.grand-challenge.org/). These can be useful for creating training datasets for machine vision experimentation. It is intended that the notebook provided can be used to generate such a training dataset from a folder of STL files Specifically, the notebook contains the code that does the following

It opens a working directory subfolder of MHD files, randomly selects a file within the folder and generates an array of the vectors of that STL file
Using the vectors of the STL file a number of randomly generated points over the surface of 3D model are generated
The randomly generated points are rotated by a random number of degrees about a randomly generated axis originating from the origin.
The randomly generated points are scaled such that the 3D model will fit within a cube of defined size
Steps 1 to 4 are repeated. Each time that this process is repeated the x,y & z coordinates of the randomly generated surface samples are appended as a row of an array. Upon completion this array is saved as a csv file within the working directory.
