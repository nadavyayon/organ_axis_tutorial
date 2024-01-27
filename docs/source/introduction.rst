Introduction
=====

Biological tissues are classically subdivided by discrete compartmental niches pre-defined through careful examination by histologists. However, the distributions of cells *within* These discrete structures are determined by orchestrated signalling events during development, differentiation, or migration, following autocrine, paracrine and endocrine signalling.

Common coordinate framework
----- 

A Common Coordinate Framework (CCF) is broadly defined as a set of rules that allows researchers and physicians to develop a common language when discussing a morphological tissue location. One of the best examples of a successful CCF is the Allen mouse brain atlas - https://mouse.brain-map.org/static/atlas. This resource, accompanied by computational tools that allow mapping of any 2D section to this CCF allowed researchers to accumulate knowledge from multiple studies which is essential for scientific progress. 

However, apart from the mouse brain and perhaps a 3D human scans in MRI studies. We lack CCFs for any other organ. 

Thymus morphology and T cell maturation
-----------------
The thymus gland in a multilobular organ that is responsible for thymocyte or T cell maturation. T cells mature through migration within the compartments of the thymus. initially TCR rearrangement and positive selection occurs in the cortex and cells then complete negative selection in the medulla. However, there are no biological membranes that divide these two morphological components.  
Hence, In an attempt to capture a CCF for the thymus, we aimed to  mode the major morphological axis of the thymus - from the edge of the cortex to the "deepest" point of the medulla and give a position along this axis to any spot in the thymus. However, as opposed to the mouse thymus and the mouse brain that "looks" the same between different mice, the thymus is highly plastic and can even change in very quickly during a course of days, for example in response to infection. In addition it is highly repetitive.  

.. image:: T_cell_education.PNG
  :width: 400
  :alt: Alternative text
Image credit DALL-E

Construction of the cortico-medullary axis
--------------
account to what a cell is "sensing" or to position a cell in continuous space. The OrganAxis approach aims to account for both local and global influences within and between structures. By deriving a "position" or a score to how much the cell is influenced by its proximity to structure. In the thymus, Since we assume that these migration events are driven by signalling molecules diffusion, we would fit a nonlinear association that is dependent on the distance from nearby morphological structures. 








