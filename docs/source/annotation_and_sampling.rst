Annoations and spatial resolution
==================

Consistent tissue annotations
------------ 
We identified a significant gap in the ability to obtain robust tissue annotations across various spatial technologies.  For instance, Visium (by 10X Genomics) is commonly annotated using the "10X Loupe Browser" (https://www.10xgenomics.com/support/software/loupe-browser/latest), which limits annotations to a resolution of 100µm between spots. For annotating platforms such as IBEX (https://www.nature.com/articles/s41596-021-00644-9) or other imaging-based technologies, users may turn to tools like the outstanding Napari (https://napari.org/stable/), where annotations can be made at the pixel level and specific plugins for different spatial technologies are being developed continuously. Nonetheless, the use of external software presents challenges for tissue annotations on cluster infrastructure, which is a common environment for bioinformaticians.
These challenges motivated us to create TissueTag, a straightforward yet powerful solution for interactive tissue annotation within a Jupyter notebook environment (https://github.com/nadavyayon/TissueTag/tree/main). We recommend trying TissueTag for your spatial data analysis needs!


Spatial sampling resolution
---------------
In addition to the above, I believe it is critical to define the spatial sampling frequency of your CCF and keep constant across samples, conditions and technologies. While this might seem basic it is often ignored! Essentially, each image has its own pixel size which depends on the microscope's configuration and the experimenter's choice. In fact, the spatial sampling resolution is independent of the imaging resolution and can even be higher than the pixel resolution. Practically, we will construct an hexagonal point grid (HPG) in space with a set resolution and which all our calculations would be based on. Like any filter, selecting a spital frequency will affect the ability to capture spatially variable patterns. Thus, the researcher should explore different options and estimate to which degree the spatial variance is represented. 

**In this (extreme) example, selecting a low spatial frequency underrepresents the high frequency structures (capsule) but does captures the broad structures (medulla and cortex).**

.. image:: images/0_4_ED4_figure_Organ_Axis_equations_v2_grid_low.jpg
   :width: 60%

Image credit: partially adapted from BioRender
