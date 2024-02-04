Full model assembly and binning
======

Now that we have set our base function H that defines the relative position between 2 structures and assigned a relative score, we can concatenate two of these functions in order to account for multiple structures. 
In addition, since the position functions are directional we can decide how one would affect the other. These questions should be derived based on the specific biological question. 
In our case, we wanted to derive a CCF for the human thymus, thus we constructed our axis from the outer capsule of the cortex -> to the cortex -> to the cortico-medullary junction - > and finally to the depth of the medulla. 

For this we have derived the following formula where w1 and w2 factor in the influence of each component on the general score for point p.

.. image:: images/cma_definition.png
   :width: 100%

To act as a true CCF, we must develop a common jargon between the scientific community. And since it's not very intuitive or informative to address "thymus CMA position 0.5 to 0.6", we further bin the axis by layers that refer to anatomically informed positions. 
Here, we demonstrate this concept on a simplified representation of the thymus going from the leftmost broad anatomical annotations, to the continuous axis and the right-most binned axis. 
Bottom row shows the implementation of the CMA and binned axis on IBEX since cell segmentation data (scale bar is 500 microns) of a paediatric thymus.  

.. image:: images/full_model_illustration.PNG
   :width: 100%
 



