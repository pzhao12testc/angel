# Angel's Architecture Design

----

![][1]

The overall design of Angel is simple, clear-cut, easy-to-use, without excessive complications; it focuses on characteristics related to machine learning models and pursues the best performance of high-dimensional models. Angel's architecture design consists of three modules: 

 
In addition to the three modules, there are two important classes that deserve attention, though not shown in the chart:

1. **Client**: The Initiator of Angel Application

	* Start/stop PSServer
	* Start/stop Angel worker
	* Load/save the model
	* Start the specific computating process
	* Obtain application status


2. **Master**: The Guardian of Angel Application

	* Slice and distribute raw data and the parameter matrix 
	* Request computing resources for worker and parameter server from Gaia
	* Coordinate, manage and monitor worker and PSServer activities

With the above design, Angel's overall architecture is comparatively easy to scale up. 

* **PSServer Layer**: provide flexible, multi-framework PS support through PS-Service
* **Model Layer**: provide necessary functions of PS and support targeted optimization for performance
* **Worker Layer**: satisfy needs for algorithm development and innovation based on independent API 

Therefore, the distributed computing engineers can focus on optimization of the core layers, whereas the algorithm engineers and data scientists can focus on the algorithm development and implementation, making full use of the platform, to pursue the best performance and accuracy. 


[1]: ../img/angel_architecture_1.png