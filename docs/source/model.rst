model
=====

Motivation to construct the Cortico-Medullary axis 
---------------
We set to construct a thymus CCF through accounting to the relative position of a cell in continuous space. To overcome the highly variable features of the human thymus, OrganAxis approach aims to account for both local and global influences within and between structures. By deriving a "position" or a score to how much the cell is influenced by its proximity to structure.

Definition of the spatial sampling resolution
---------------
Before we can calculate the distance functions for the axis, we first need to define our spatial sampling resolution. While this might seem wierd it in not a trivial task! each image has it's own pixel size which depends on the microscope's configuration and the experimenter choise. However for the CCF calculation to be robust and consistent, we need to define the spatial sampling resolution and keep it identical throughut the study. in fact, the spatial sampling resolution is independent than the imageing resolution. Practically, we will construct an hexagonal grid (HG) in space with a set resolution and which all our calculations would be based on. It is recommended to set the HG resolution to be sufficiently high to capture the morphological variance needed 

.. image:: grid_space_2.PNG
   :width: 50%
