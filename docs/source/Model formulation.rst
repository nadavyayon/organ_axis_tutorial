Model definition
=====
1. Consistent Tissue Annotations
------------ 
We recognized inconsistencies in the possibility of obtaining robust tissue annotations from various spatial technologies. For example, Visium (10X Genomics) is often annotated in the "10X Loupe Browser" (https://www.10xgenomics.com/support/software/loupe-browser/latest), which restricts annotations to a 100µm spot-to-spot resolution. For annotation of IBEX (https://www.nature.com/articles/s41596-021-00644-9) and other imaging-based platforms, users might use tools like the excellent Napari (https://napari.org/stable/), where annotations are done at the pixel level, although specific plugins are constantly developed for various spatial technologies. However, this can be difficult to interact with on cluster infrastructure which bioinformaticians routinely use. This incompatibility, along with the need for a simple, open-source tool to annotate tissues at a well defined resolution and within the popular Jupyter notebook environment, led us to develop **TissueTag** (https://github.com/nadavyayon/TissueTag/tree/main) and we would suggest you try it out on your spatial data!

2. Definition of the spatial sampling resolution
---------------
In addition to the above, I believe it is critical to define the spatial sampling frequency of your CCF and keep constant across samples, conditions and technologies. While this might seem basic it is often ignored! Essentially, each image has its own pixel size which depends on the microscope's configuration and the experimenter's choice. In fact, the spatial sampling resolution is independent of the imaging resolution and can even be higher than the pixel resolution. Practically, we will construct an hexagonal point grid (HPG) in space with a set resolution and which all our calculations would be based on. Like any filter, selecting a spital frequency will affect the ability to capture spatially variable patterns. Thus, the researcher should explore different options and estimate to which degree the spatial variance is represented. 

**In this (extreme) example, selecting a low spatial frequency underrepresents the high frequency structures (capsule) but does captures the broad structures (medulla and cortex).**

.. image:: images/0_4_ED4_figure_Organ_Axis_equations_v2_grid_low.jpg
   :width: 60%
Image credit: partially adapted from BioRender

3. Definition of distance function (D), spatial location (P), and structure (S) 
---------------
Once our grid is set we can define our basic distance function (D) that is the minimal distances of every point P to nearest neighbours (K) in structure S. In the illustration below, we show how the minimal distance is defined to S1 which contains P and S2 which doesn't contain P. 

.. image:: images/D_definition.png
   :width: 100%

.. image:: images/grid_space_3.PNG
   :width: 75%

4. Mean distance of KNN points to P
-------------
From D, we can now calculate the mean distance of point P from S for a set of K nearest neighbours
For that we can simply define: 

.. image:: images//mu_equasion.png
   :width: 100%

5. Constructing the boundary-centered axis
--------------
Next, we can calculate the directional position of a point P from the boundary of two structures by the normalized difference of µKS1(p) and µKS2(p). 

.. image:: images//H_function.png
   :width: 100%

6. Exploration and intuition from simulations of K and grid resolution on axis function
--------------

To study the influence of K or grid density on how space is transformed to the axis position, we generated simulated data of a grid and random spots in space within that grid. For simplicity, we are evaluating the relationship between the linear position along Y and the axis function H

**Changing the K nearest neighbours and keeping the grid constant:** Noise is reduced while H is "flattened" with K. In K=30 we can start seeing edge effects where the score is diminished by lack of near grid spots.  

.. image:: images/supp_axis_params_knn_simulations-04.png
   :width: 100%

**Changing the grid spacing and keeping K constant:** At low grid density relative to K, the dependency of H is more gradual and edge effects are visible. In the highest grid density H behaves as a full sigmoid and transitions if faster around the border.  

.. image:: images/supp_axis_params_knn_simulations-01.png
   :width: 100%

**Changing both grid spacing and K in a matrix** 

.. image:: images/supp_axis_params_knn_simulations-02.png
   :width: 100%







