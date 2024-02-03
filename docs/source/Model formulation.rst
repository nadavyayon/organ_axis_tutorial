Model construction
=====

Obtaining consistent tissue annotations
------------ 
We recognized inconsistencies in the possibility of obtaining tissue annotations from various spatial technologies. For example, Visium is often annotated in the 10X Loupe Browser (https://www.10xgenomics.com/support/software/loupe-browser/latest), which restricts annotations to a 100µm spot-to-spot resolution. For the annotation of IBEX and other imaging-based platforms, users might use tools like the excellent Napari (https://napari.org/stable/), where annotations are done at the pixel level. However, this requires additional scripting to ensure annotations are consistent across datasets and can be difficult to interact with on farms. This incompatibility, along with the need for a simple, open-source tool to annotate tissues at any resolution and within the popular Jupyter notebook environment among bioinformaticians, led us to develop TissueTag (https://github.com/nadavyayon/TissueTag/tree/main) and we would suggest you try it out on your spatial transcriptomics (or any other tissue) data!

Definition of the spatial sampling resolution
---------------
Before we can calculate the distance functions for the axis, we first need to define our spatial sampling resolution. While this might seem weird it is not a trivial task! Each image has its own pixel size which depends on the microscope's configuration and the experimenter's choice. However for the CCF calculation to be robust and consistent, we need to define the spatial sampling resolution and keep it identical throughout the study. In fact, the spatial sampling resolution is independent of the imaging resolution. Practically, we will construct an hexagonal grid (HG) in space with a set resolution and which all our calculations would be based on. It is recommended to set the HG resolution to be sufficiently high to capture the morphological variance needed. 

.. image:: images/grid_space_2.PNG
   :width: 35%
image credit: BioRender



Distance function (D) for point (P) and structure (S) 
---------------
Once our grid is set we can define our basic distance function (D) that is the minimal distances of every point P to nearest neighbours (K) in structure S. In the illustration below, we show the how the minimal distance is defined to S1 which contains P and S2 which doesn't contain P. 

Definition:

1) Let p ∈ R^2 be any point on an HG with spacing - r

2) Let S be an assembly of p points inside an anatomical structure,S ∈ {Medulla,Cortex,Capsule….}

3) dS(p) is defined as the euclidean distances between point p, and all points that belong to structure S.

4) DS,p[i] = is the sorted (by minimal value) series of dS(p), where i is the index of DS,p.

   DS,p[i] ≤ DS,p[i+1]  ,∀ i

Example - DS,p[0] is the distance to the nearest point in structure s to point p


.. image:: images/grid_space_3.PNG
   :width: 100%
image credit: Nadav Yayon

Mean distance of KNN points to P
-------------
Aside from the spatial grid resolution, we also need to define how many KNN points to take to calculate the mean distance of point P from S. 
For that we can simply define Equation 1:  µKS(p) = (i=0 to K-1)∑(DS,p[i]/K) 

Constructing the boundary axis and the influence of K and grid resolution
--------------
Next, we can calculate the directional position of a spot from the boundary of two structures by simply subtracting µKS(p) in respect to both structures for a given spot P. 
This difference is then intrnally normalised to produce a sigmoidal-like function. 
In the simplified simulated plot below we can see the influence of KNN or grid density on how space is transformed to the axis position. 



.. image:: images/changing_grid.png
   :width: 50%
image credit: Nadav Yayon


.. image:: images/changing_k.png
   :width: 100%
image credit: Nadav Yayon



.. image:: images/matrix_K_sp.png
   :width: 100%
image credit: Nadav Yayon





