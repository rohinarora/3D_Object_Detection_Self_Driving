* 13 min video in https://medium.com/lyftlevel5/lyft-level-5-self-driving-dataset-competition-now-open-97493e9f154a

* LIDAR
  - detects smoke, dust etc. Things which don't hinder the car, but show up as obstacles
  - car at 100m away has very small point cloud; car 10m away has very clear point cloud. NN should be robust to take care of both cases

* Camera
  - Human labelled image data itself might have errors

* Image data and Lidar data must be aligned/Sensor fusion data must be time synchronized.

* Out of petabytes of collected data, only a fraction is useful. And this useful data needs to be hand labelled. Keeping in mind we don't bring in any class imbalances etc. For eg. Cars are way more frequent than say - birds

* Ability to query into the dataset is extremely helpful. "powerful data engineering pipelines"
![](./images/1.png)
![](./images/2.png)
![](./images/3.png)
Once you query, you can feed exactly that image/video into the model and check how it performs/retrain it on certain type of data



* Many traditional approaches have been replaced by DL in self driving pipeline.
* [2D object detection has been widely "democratized", and significant progress has been made (RCNN). This is in large part due to the recent widespread availability of labeled 2D-object annotations and the willingness of the research community to share models and code that deliver high performance. The same has not yet occurred in 3D object detection. Today, there are multiple competing technologies for 3D object detection. For instance some that use convolutions, versus some that don’t (e.g. Point Net), versus some that use continuous convolutions. Each of these approaches come with different tradeoffs resulting in no clear technology winner. This, in part, may be due to the lack of high-quality datasets in this domain](https://medium.com/lyftlevel5/lyft-level-5-self-driving-dataset-competition-now-open-97493e9f154a)
* ![](./images/4.png)
* Point cloud DL is fairly unexplored till now
* ![](./images/5.png)
* There isn't even consensus on whats the best point cloud representation
* ![](./images/6.png)
* Combining point cloud with map can be interesting
* ![](./images/7.png)
* Nice paper-
* ![](./images/8.png)

* ![](./images/9.png)
* When rain comes in, camera may not do well; and need to rely on LIDAR
* ![](./images/10.png)
* When there is sudden clutter on road; camera may not capture it 100 meters in advance, having LIDAR helps here
* ![](./images/11.png)
* In the below case, object occludes camera view, and region behind the object is unknown. Having camera data might help here
![](./images/12.png)
* It's common to have multiple NN working together; as a pipeline today. How to combine "uncertainties" of multiple NN is an open problem.
![](./images/13.png)
* Auto ML for self driving cars is interesting
![](./images/14.png)
