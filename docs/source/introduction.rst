Introduction
=====
Biological tissues are classically subdivided by discrete macroscopic compartments defined through careful examination by histologists. While these structures allow a rough description of the cellular composition of a tissue and enable inter-compartmental comparisons, they neglect the cellular and molecular heterogeneity within individual compartments. Capturing molecular gradients and intra-compartmental differences is difficult to achieve in a reproducible manner due to sample-dependent variations and the lack of clear reference points beyond histologically distinguishable tissue landmarks. A common coordinate framework can help overcome these issues by enabling direct inter-sample comparisons and integration.

Common Coordinate Framework
-----------------

A Common Coordinate Framework (CCF) is broadly defined as a set of rules that allows researchers and physicians to map their specimens to a reference space. There are different types of CCF2 which vary in their complexity depending on the level of specimen-to-specimen variability in a given system. The simplest case of the CCF is the anatomical coordinate system, which can be applicable to very stereotypical structures such as embryos. More complex coordinate systems (used for systems with high level of variability) include landmark-based systems, which rely on user-defined morphological/histological or molecular features for orientation and involve nonlinear transformations of the mapped image.
The highly useful Allen Mouse Brain Atlas ( https://mouse.brain-map.org/static/atlas) is accompanied by computational tools that allow mapping of any 2D section to the “exact” brain 3D space of a typical mouse. This is reasonable as mice brains have relatively low variability among animals. Mapping a human brain, on the other hand, is challenging due to the enormous variability between individuals. To overcome this limitation, advanced mapping algorithms have to be employed, which use non-linear, and statistical 3D mapping to overcome the large inter-individual variability3. Unfortunately, we lack a CCF for other organs, especially in humans. The primary reason for this gap is most likely the absence of a dedicated CCF model that is accepted by the scientific community as in the case of the human brain.
A CCF provides two key advantages: It establishes a common language between researchers studying the same sample types. Without a common reference, studies are bound to use poorly-defined terminology resulting in highly subjective and ambiguous descriptions of tissue composition, impeding inter-study comparisons. A CFF can thus enhance the accumulation of knowledge across institutes and disciplines. Moreover, a CFF permits extraction of additional information on the spatial subcompartments for detailed analysis and interpretation. This is critical in order to move beyond largely non-quantitative analyses and fully utilise the rapidly growing detection resolution that spatial technologies can now offer.
In the OrganAxis approach described in the subsequent sections, we aim to establish a first approximation for mapping a 2D tissue to a CCF model to gain more spatial context and develop a common language. While this approach is here implemented on the 2D space, it is not restricted by dimensionality and we hope that OrganAxis will be applied to 3D and 4D datasets in the future.   

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
We aimed to construct a thymus CCF model to capture the essential morphological axis within the thymus—from the cortex edge (capsule) to the deepest part of the medulla. This model aims to reveal migration patterns and identify the 'cytokine highways' within the thymus in higher spatial resolution than discrete annotations permit. 
To address the highly variable features of the human thymus, our OrganAxis approach considers both local and global influences within and between discrete structures. By deriving a score (or position) from a non-linear transformation of Euclidean distance, we can adjust the extent to which the score is influenced by its proximity to a specific structure. Essentially, we attempt to capture the cell's environment and map that environmental characteristic onto a one-dimensional axis.



.. image:: images/cell_blind.PNG
   :width: 50%
image credit: DALL-E
