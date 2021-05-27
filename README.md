#http://www.cvlibs.net/datasets/kitti/raw_data.php
We have downloaded Kitti sequence file.

# Object_detection_DBSCAN
As a first step we have to install the dependent libraries using pip or conda under conda environment.


-----------------------------------------------------------------------------------------------------------

#from cuml.cluster import DBSCAN
Especially this package runs under GPU which helps to reduce the runtime of DBSCAN.
We have import Rapids.0.18 api
Conda cmd :conda install -c rapidsai -c nvidia -c numba -c conda-forge cudf=0.19 python=3.7 cudatoolkit=10.1
#https://github.com/rapidsai/cudf
#https://github.com/rapidsai/cuml 

----------------------------------------------------------------------------------------------------------------------

**SEGMENTATION - lINEAR REGRESSION ( RANSAC - RANDOM SAMPLE CONSENSUS )**

from sklearn import linear_model

#https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.RANSACRegressor.html

To separate the ground plane(Inliers) and outliers. Which helps to reduce the computation time for further process.
![in_out](https://user-images.githubusercontent.com/84854222/119775054-b2ffea80-bee0-11eb-829f-51f3488bf8af.png)


----------------------------------------------------------------------------------------------------------------------


**CLUSTERING - DBSCAN ( DENSITY BASED CLUSTERING AND NOISE )**


#https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html

From the separated outliers we have move the data into Sklearn DBSCAN/CUML DBSCAN( Mentioned in above refer content )
to cluster the individual objects based on the given minpoints and Eps(radius) value.


![splitted cluster1](https://user-images.githubusercontent.com/84854222/119775076-ba26f880-bee0-11eb-9371-eb86186b17d8.png)

----------------------------------------------------------------------------------------------------------------------

**VISUALIZATION - MATPLOTLIB**

#https://matplotlib.org/

From the clustered object we have to plot the bounding box on top of the each clustered object.
Finding the min,max for the each axis(XYZ). 



----------------------------------------------------------------------------------------------------------------------

****FLASK API ****

#https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask

For the each frames we have save it in the system and Overrides the each file where hosted it on the web page using various ports(http://127.0.0.1:2222/)
![Screenshot (20)](https://user-images.githubusercontent.com/84854222/119775119-cca13200-bee0-11eb-96e5-3551c4745a02.png)


----------------------------------------------------------------------------------------------------------------------








