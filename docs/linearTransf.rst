.. include:: sub.txt

==========================================
 linearTransf class
==========================================

.. class:: linearTransf(xz=[], dI=[], dJ=[])

   Create a Linear :class:`geomTransf` object, which performs a linear geometric transformation of beam stiffness and resisting force from the basic system to the global-coordinate system.

   ========================   =============================================================
   ``xz`` |listf|             These components are specified in the global-coordinate system X,Y,Z and define a vector that is in a plane parallel to the x-z plane of the local-coordinate system. (required for 3D)
   ``dI`` |listf|             Joint offset values -- offsets specified with respect to the global coordinate system for element-end node i (the number of arguments depends on the dimensions of the current model). (optional)
   ``dJ`` |listf|             Joint offset values -- offsets specified with respect to the global coordinate system for element-end node J (the number of arguments depends on the dimensions of the current model). (optional)
   ========================   =============================================================

   * attributes

     #. :attr:`tagged.tag`

   * methods

     #. :meth:`tagged.__str__`
     #. :meth:`tagged.remove`

   A refresher on Euclidean Geometry and Coordinate Systems:
   A single vector may be defined by two points. It has length, direction, and location in space. When this vector is used to define a coordinate axis, only its direction is important. Now any 2 vectors, Vr and Vs, not parallel, define a plane that is parallel to them both. The cross-product of these vectors define a third vector, Vt, that is perpendicular to both Vr and Vs and hence normal to the plane: Vt = Vr X Vs.

   The element coordinate system is specified as follows:
   The x-axis is a vector given by the two element nodes; The vector vecxz is a vector the user specifies that must not be parallel to the x-axis. The x-axis along with the vecxz Vector define the xz plane. The local y-axis is defined by taking the cross product of the x-axis vector and the vecxz vector (Vy = Vxz X Vx). The local z-axis is then found simply by taking the cross product of the y-axis and x-axis vectors (Vz = Vx X Vy). The section is attached to the element such that the y-z coordinate system used to specify the section corresponds to the y-z axes of the element.


   

   ::

      # 2D transf
      transf = geomTransf.Linear()
      transf = geomTransf.Linear(dI=[dXi,dYi],dJ=[dXj,dYj])

      # 3D transf
      transf = geomTransf.Linear()
      transf = geomTransf.Linear(xz=[x,y,z],dI=[dXi,dYi,dZi],dJ=[dXj,dYj,dZj])



   

