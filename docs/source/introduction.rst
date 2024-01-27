Introduction
=====

Biological tissues are classically subdivided by discrete compartmental niches pre-defined through careful examination by histologists. However, the distributions of cells *within* these discrete structures are determined by orchestrated signalling events during development, differentiation, or migration, following autocrine, paracrine and endocrine signalling.

Common coordinate framwork
----- 

A Common Coordinate Framework (CCF) is broadly defined as a set of rules that allows reserchers and phisicians to develop a common language when discussing a morpholocial tissue location. One of best  The best examples of a sucessful CCF is the Allen mouse brain atlas - https://mouse.brain-map.org/static/atlas. This reasouce, accopanied by computational tools that allow mappign of any 2D section to this CCF allowed resercehesr to accumulate knowladge from multiple studies which is essintial for sceintific progress. 

However, apart from the mouse brain and perhaps a 3D human scans in MRI studies. We lack CCFs for any other organ. 

Thymus morphology and T cell maturation
-----------------#
The thymus gland in a multilobular organ that is responsible fot thymocyte or T cell maturation. T cells mature throught migration within the compartments of the thymus. initially TCR rearangment and positive selection occurs in the cortex and cells then complete negative selection in the medulla. However, there are no biological membranes that divide these two morphological components.  
Hence, In an attempt to capture a CCF for the thymus, we aimed to  mode the major morpological axis of the thymus - from the edge of the cortex to the "deepest" point of the medulla and give a position along this axis to any spot in the thymus. However, as opposed to the mouse thymus and the mouse brain that "looks" the same between different mice, the thymus is highly plastic and can even change in very quickly during a course of days, for example in response to infection. In adition is is highly repetative.   

account to what a cell is "sensing" or to position a cell in continuous space. The OrganAxis approach aims too account for both local and global influences within and between structures. By deriving a "position" or a score to how much the cell is infuenced by it's proximity to structure. In the thymus, Since we assume that these migration eventsare driven by signaling molucules diffusion, we would fit a non-liear association that is dependent on the distance from nearby morphological structures. 


.. image:: T_cell_education.PNG
  :width: 400
  :alt: Alternative text
Image credit DALL-E




