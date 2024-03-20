Introduction
=====

Biological tissues are classically subdivided by discrete compartmental niches predefined through careful examination by histologists. However, the distributions of cells within these discrete structures are determined by orchestrated signalling events during development, differentiation, or migration, following autocrine, paracrine, and endocrine signalling.

Common Coordinate Framework
-----
A Common Coordinate Framework (CCF) is broadly defined as a set of rules (formulas, xyz coordinates or a combination of both) that allows researchers and physicians to map their specimens to a reference space. A CCF provides two key advantages: (1) a common language between researchers studying the same samples, thereby enhancing the accumulation of knowledge across institutes and disciplines; and (2) Extraction of additional information on the spatial subcompartments for improved inference and interpretation. 

 One of the best examples of a highly useful CCF is the Allen Mouse Brain Atlas - https://mouse.brain-map.org/static/atlas. This resource is accompanied by computational tools that allow mapping of any 2D section to the mouse 3D space. As indicated above , this mapping facilitates the breakdown of a vast region (e.g., the Cortex) into subcompartments (e.g., Cortical layers 1, 2, 3, or motor vs. sensory regions). However, apart from the mouse brain example and for 3D human brain scans in MRI studies which have advanced mapping algorithms, we lack CCFs for other organs, especially in humans. I believe the primary reason for this gap is the absence of a suitable tissue model.

In the OrganAxis approach, we aim to establish a first approximation for mapping a 2D tissue to a CCF model to gain more spatial context and develop a common language. While this approach is implemented on the 2D space here, it is not restricted by dimensionality. Moreover, we hope that OrganAxis will be applied to 3D and 4D datasets in the future.   

Thymus morphology and T cell maturation
-----------------
The thymus gland is a multilobular organ responsible for thymocyte (T cell) maturation. T cells mature through migration within the compartments of the thymus; initially, precursor cells migrate from the peri vascular space (PVS) to the Cortex where TCR rearrangement and positive selection (the ability to bind MHC Class I/II molecules) occurs.  Cells then migrate to the medulla to undergo negative selection (for interaction with self peptides) and where cells eventually leave the thymus to become Naive T cells. 
Interestingly, there are no biological membranes that divide these two macro morphological compartments and cells are free to roam space during their journey. However, as opposed to the mouse brain, the thymus is highly plastic and can even change even over the course of days, for example, in response to infection.

|pic1| |pic2|

.. |pic1| image:: images/illustration_T.PNG
   :width: 45%
image credit: BioRender

.. |pic2| image:: images/morphology_paed.PNG
   :width: 35%

Motivation to construct the Cortico-Medullary axis
---------------
We set out to construct a thymus CCF and attempt to capture the relative position of a cell in continuous space. To overcome the highly variable features of the human thymus, the **OrganAxis** approach aims to account for both local and global influences within and between structures. By deriving a score based on a non-linear transformation of Euclidean distance, we can control how much the cell is influenced by its proximity to a structure. In a way, we are trying to mimic what the cell is "seeing" in space and project that environmental feature to a unidimensional axis.

.. image:: images/cell_blind.PNG
   :width: 50%
image credit: DALL-E
