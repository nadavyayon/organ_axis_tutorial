Annoations and spatial resolution
==================

Consistent tissue annotations
------------ 
We identified a significant gap in the ability to obtain robust tissue annotations across various spatial technologies.  For instance, Visium (by 10X Genomics) is commonly annotated using the "10X Loupe Browser" (https://www.10xgenomics.com/support/software/loupe-browser/latest), which limits annotations to a resolution of 100µm between spots. For annotating platforms such as IBEX (https://www.nature.com/articles/s41596-021-00644-9) or other imaging-based technologies, users may turn to tools like the outstanding Napari (https://napari.org/stable/), where annotations can be made at the pixel level and specific plugins for different spatial technologies are being developed continuously. Nonetheless, the use of external software presents challenges for tissue annotations on cluster infrastructure, which is a common environment for bioinformaticians.
These challenges motivated us to create TissueTag, a straightforward yet powerful solution for interactive tissue annotation within a Jupyter notebook environment (https://github.com/nadavyayon/TissueTag/tree/main). We recommend trying TissueTag for your spatial data analysis needs!


Spatial sampling resolution
---------------
Each spatial method comes with its unique sampling resolution. However, to develop a CCF that enables comparison across the entire study, it is crucial to precisely define the spatial sampling frequency of the tissue and consistently maintain it across all samples.  Though this may seem fundamental, it is frequently overlooked! In fact, the spatial sampling resolution is independent of the imaging resolution and can even be higher than the pixel resolution. In practice, we will create a hexagonal point grid (HPG) with a predetermined resolution, onto which we will map our pixel annotations.  Similar to any filter, choosing a specific spatial resolution will impact the ability to discern spatial frequencies but will enhance noise robustness. Therefore, researchers should investigate various options and determine the extent to which the spatial variability necessary for their research question is captured

**In this (extreme) example, selecting a low spatial frequency underrepresents the high frequency structures (capsule) but does captures the broad structures (medulla and cortex).**

.. image:: images/0_4_ED4_figure_Organ_Axis_equations_v2_grid_low.jpg
   :width: 60%

Image credit: partially adapted from BioRender
