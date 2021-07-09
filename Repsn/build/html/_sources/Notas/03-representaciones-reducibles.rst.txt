Representaciones Reducibles
===========================

En este capítulo presentamos algunas funciones que tratan con una representación reducible compleja :math:`R` de un grupo finito :math:`G`.

Constituyentes de Representaciones
----------------------------------

.. _ConstituentsOfRepresentation:

ConstituentsOfRepresentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``ConstituentsOfRepresentation(rep)`` es llamada con con un argumento ``rep``, que una representación de un grupo :math:`G`. Esta función devuelve una lista de representaciones irreductibles de :math:`G` que son constituyentes de ``rep``, y sus correspondientes multiplicidades. Por ejemplo, si ``rep`` es una representación de :math:`G` que proporciona un carácter :math:`X` tal que :math:`X = mY + nZ`, donde :math:`X` y :math:`Z` son caracteres irreducibles de :math:`G`, y :math:`m` y :math:`n` son las multiplicidades correspondientes, entonces ConstituentsOfRepresentation_ devuelve ``[[m, S] , [n, T]]`` donde ``S`` y ``T`` son representaciones irreductibles de :math:`G` que dan :math:`Y` y :math:`Z`, respectivamente. Esta llamada de función puede resultar bastante cara cuando :math:`` es un grupo grande.