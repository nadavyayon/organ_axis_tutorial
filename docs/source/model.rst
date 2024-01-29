Model construction
=====

Motivation to construct the Cortico-Medullary axis 
---------------
We set to construct a thymus CCF through accounting to the relative position of a cell in continuous space. To overcome the highly variable features of the human thymus, OrganAxis approach aims to account for both local and global influences within and between structures. By deriving a "position" or a score to how much the cell is influenced by its proximity to structure.

Definition of the spatial sampling resolution
---------------
Before we can calculate the distance functions for the axis, we first need to define our spatial sampling resolution. While this might seem weird it is not a trivial task! Each image has its own pixel size which depends on the microscope's configuration and the experimenter's choice. However for the CCF calculation to be robust and consistent, we need to define the spatial sampling resolution and keep it identical throughout the study. In fact, the spatial sampling resolution is independent of the imaging resolution. Practically, we will construct an hexagonal grid (HG) in space with a set resolution and which all our calculations would be based on. It is recommended to set the HG resolution to be sufficiently high to capture the morphological variance needed. 

.. image:: images/grid_space_2.PNG
   :width: 35%


Distance function (D) for point (P) and structure (S) 
---------------
Once our grid is set we can define our basic distance function (D) that is the minimal distances of every point P to nearest nighbours (K) in strtucture S. In the illustration below, we show the how the minimal dustance is defined to S1 which contains P and S2 which doesn't contain P. 

Definition:

1) Let p ∈ R^2 be any point on an HG with spacing - r

2) Let S be an assembly of p points inside an anatomical structure,S ∈ {Medulla,Cortex,Capsule….}

3) dS(p) is defined as the euclidean distances between point p, and all points that belong to structure S.

4) DS,p[i] = is the sorted (by minimal value) series of dS(p), where i is the index of DS,p.

   DS,p[i] ≤ DS,p[i+1]  ,∀ i

Example - DS,p[0] is the distance to the nearest point in structure s to point p


.. image:: images/grid_space_3.PNG
   :width: 100%

Mean distance of KNN points to P
-------------
Aside from the spatial grid resoution, we also need to define how many KNN points to take to calculate the mean distance of point P from S. 
For that we can simply define Equation 1:  µK(p) = (i=0 to K-1)∑(DS,p[i]/K)

Constructing a boundary axis
--------------
Next, we can calculate the normalised distance from of P betwe





