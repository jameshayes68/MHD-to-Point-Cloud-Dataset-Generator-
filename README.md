# MHD-to-Point-Cloud-Dataset-Generator-
MHD is a file format often used for storing 3D medical image data. In many cases the MHD file format is selected over DICOM for freely downloadable datasets (e.g. https://luna16.grand-challenge.org/). It is intended that the notebook provided can be used to open such files and segment them into areas of interest. Specifically, the notebook contains the code that does the following

1. It opens a working directory subfolder of NRRD files, randomly selects an NRRD file within the folder and generates an array 3D array representation
2. Batched K-Means Clustering is applied so as to segment the image based on color or Hounsfield unit. This breaks the image up into anatomical regions of similar opacity. 
3. Based on user input certain regions/clusters are identified as of interest. All other regions are ignored going forward.
4. DBSCAN Clustering is applied to each of the regions/clusters identified as of interest. This breaks anatomical regions of similar opacity up into seperate regions if they are not connected. In addition it also identifies noise or outliers
5. These subregions/clusters are reviewed and the user identifies areas of interest. All other regions are ignored going forward.
6. Any data points classified as noise are reclassified based on the most common lable of their neighbours.
7. The resulting 3D array is converted to an array of xyz coordinates and saved as a csv file within the working directory.
