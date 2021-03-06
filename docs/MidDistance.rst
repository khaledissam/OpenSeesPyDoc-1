.. include:: sub.txt

=============================================================
 midDistanceBeamIntegration  class
=============================================================

.. class:: midDistanceBeamIntegration(sec,N)

   Create a MidDistance :class:`beamIntegration` object.
   This option allows user-specified locations of the integration points. The associated integration weights are determined from the midpoints between adjacent integration point locations.
   :math:`w_i=(x_{i+1}-x_{i-1})/2` for :math:`i=2...N-1`, :math:`w_1=(x_1+x_2)/2`, and :math:`w_N=1-(x_{N-1}+x_N)/2`.

   ========================   =============================================================
   ``secs`` |list|            A list previous-defined |section| objects.
   ``locs`` |listf|           Locations of integration points along the element.
   ========================   =============================================================

   * attributes

     #. :attr:`beamIntegration.tag`

   * methods

     #. :meth:`beamIntegration.__str__`


   ::

      locs = [0.0, 0.2, 0.5, 0.8, 1.0]
      secs = [sec1, sec2, sec2, sec2, sec1]
      bi = midDistanceBeamIntegration(secs=secs, locs=locs)


   Places ``N`` integration points along the element, whose locations are defined
   in ``locs`` on the natural domain [0, 1].
   The force-deformation response at each integration
   point is defined by the ``secs``.
   Both the ``locs`` and ``secs`` should be of length N.
   This integration rule can only integrate constant
   functions exactly since the sum of the integration weights is one.

   For the ``locs`` shown above, the associated integration weights
   will be ``[0.15, 0.2, 0.3, 0.2, 0.15]``.





