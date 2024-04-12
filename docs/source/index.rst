Welcome to OrganAxis documentation!
===================================

**OrganAxis** is a computational approach for the construction of a Common Coordinate Framework (CCF) from a set of spatial landmarks.

**Key features:**

* Derived purely from the reference image. This makes it universally applicable across any spatial platform and at any resolution.
* Straightforward approach that significantly reduces the risk of double-dipping (e.g. it is not derived from high-dimensional gene space).
* Allows multisample “diagonal” integration while preserving continuous spatial information.
* Allows modelling of linear and non-linear spatial associations to account for local and global tissue environments, e.g. cellular neighbourhoods and anatomical structures.
* Hypothesis-driven: Prior knowledge about the tissue in question is needed to derive a biologically robust and meaningful axis.


OrganAxis is implemented to derive the human thymus Cortico-Medullary Axis (CMA) here - https://github.com/Teichlab/thymus_spatial_atlas/tree/main

.. note::

   This project is under active development.

Contents
--------

.. toctree::

   introduction
   annotation_and_sampling
   Model formulation
   Model application


.. image:: images/egg_thymus.PNG
   :width: 50%
image credit: DALL-E


:Authors:
    Nadav Yayon, PhD

:Version: 1.1 of 12/04/2024
:In memory of: `Daniele Muraro <https://www.sanger.ac.uk/person/muraro-daniele/>`_

