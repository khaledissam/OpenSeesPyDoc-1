.. include:: sub.txt

==========================================
 tri31 class
==========================================

.. class:: tri31(nds, thk, type, mat, pressure=0.0, rho=0.0, b1=0.0, b2=0.0)

   Create a constant strain triangular :class:`element` object, which which uses three nodes and one integration points. A subclass of :class:`element`.

   ========================   =============================================================
   ``nds`` |list|             Three end :class:`node` objects.
   ``thk`` |section|          Element thickness.
   ``type`` |str|             String representing material behavior.
		              The type parameter can be
                              either ``'PlaneStrain'`` or ``'PlaneStress'``.
   ``mat`` |ndmat|            A :class:`NDMaterial` object.
   ``pressure`` |float|       Surface pressure. (optional)
   ``rho`` |float|            Element mass density (per unit volume) from
		              which a lumped element mass matrix
                              is computed. (optional)
   ``b1`` |float|             Constant body forces defined in the domain. (optional)
   ``b2`` |float|             Constant body forces defined in the domain. (optional)
   ========================   =============================================================

.. class:: tri31(ele)

   Convert an :class:`element` to :class:`tri31`.

   ========================   =============================================================
   ``ele`` |element|          A :class:`element` object.
   ========================   =============================================================


   * attributes

     #. :attr:`tagged.tag`
     #. :attr:`element.nds`
     #. :attr:`element.ndf`
     #. :attr:`element.stiff`
     #. :attr:`element.damp`
     #. :attr:`element.mass`
     #. :attr:`element.force`
     #. :attr:`element.dampingForce`
     #. :attr:`element.dynamicForce`
     #. :attr:`tri31.stress`

   * methods

     #. :meth:`tagged.__str__`
     #. :meth:`tagged.remove`
     #. :meth:`element.section`
     #. :meth:`element.uniMat`
     #. :meth:`element.nDMat`

.. attribute:: tri31.stress

   An object attribute (get) |listf|.
   The stresses of tri31.


