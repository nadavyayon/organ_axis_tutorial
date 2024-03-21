Model
=====
1. Definition of distance function (D), spatial location (P), and structure (S) 
---------------
After establishing our grid based on the sampling resolution r (the distance between spots), we can define our fundamental distance function (D). This function calculates the minimal distances from every point P to its K nearest neighbours within a structure (S). The figure below demonstrates how we determine the minimal distance to structures S1, which includes P, and S2, which does not include P.


.. image:: images/Capture_1.PNG
   :width: 100%

.. image:: images/grid_space_3.PNG
   :width: 75%

2. Mean distance of KNN points to P
-------------
With D defined, we proceed to calculate the mean distance from point P to structure S across a set of K nearest neighbours. To achieve this, we introduce μ, the mean of minimal distances, where K represents the count of nearest neighbours. 
For that we can define: 

.. image:: images//mu_equasion.png
   :width: 100%

3. Inferring the normalised relative distance to a boundary
--------------
Subsequently, we can compute the relative (directional) position of any point P with respect to the boundary dividing two structures. This is done through the normalised difference between μS1 and μS2. Function H describes a sigmoid in space, scaling between -1 and 1, with 0 marking the boundary between structures S1 and S2. 

.. image:: images//H_function.png
   :width: 100%

Exploration and intuition from simulations of K and grid resolution on axis function
--------------

To investigate how the number of nearest neighbors (K) or the grid density (r) influences the transformation of space into axis positions, we conducted simulations using a grid with randomly placed spots within that grid. Our analysis primarily focuses on the relationship between the linear position along the Y-axis and the axis function H, distinguishing between two structures.

Changing the K nearest neighbours and keeping the grid constant: With a KNN of 2, H exhibits a "jagged" appearance, likely due to the predominance of values reflecting the simulated grid square pattern. In addition H exhibits a more step-like function shape. Both of these effects are due to the increased influence of the local environment over the global position. In high K=30, H is "flattened" and the values are more continuous but we can start seeing edge effects where the score is diminished by lack of sufficient grid spots at the edges, effectively increasing the average distance to the nearest K spots. 

.. image:: images/supp_axis_params_knn_simulations-04.png
   :width: 100%

**Changing the grid spacing and keeping K constant:** At low grid density relative to K, the dependency of H is more gradual and edge effects are visible. In the highest grid density H behaves as a full sigmoid and transitions if faster around the border.  

.. image:: images/supp_axis_params_knn_simulations-01.png
   :width: 100%

**Changing both grid spacing and K in a matrix** 

.. image:: images/supp_axis_params_knn_simulations-02.png
   :width: 100%







