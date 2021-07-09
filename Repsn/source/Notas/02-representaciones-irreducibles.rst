Representaciones Irreducibles
===============================

Sea :math:`G` un grupo finito y :math:`\chi` un carácter ordinario irreductible de :math:`G`. En este capítulo presentamos algunas funciones para construir una representación compleja :math:`R` de :math:`G` que da :math:`\chi`. Procedemos de forma recursiva, reduciendo el problema a subgrupos más pequeños de :math:`G` o caracteres de menor grado hasta que obtenemos un problema que podemos abordar directamente. Las entradas de la mayoría de las funciones son un grupo :math:`G` dado y un carácter irreducible :math:`\chi`. La salida es un mapeo (representación) que asigna a cada generador :math:`x` de :math:`G` una matriz :math:`R(x)`. Podemos usar estas funciones para todos los grupos y todos los caracteres irreducibles :math:`\chi` de grado menor que :math:`100` aunque en principio los mismos métodos pueden extenderse a caracteres de mayor grado.

Los principales métodos de estas funciones que se utilizan para construir representaciones de grupos finitos son Inducción, Extensión, Producto Tensorial y el método de Dixon (para construir representaciones de grupos simples y sus cubiertas) [DA05] y el método de Representación Proyectiva [DD10].

Construir representaciones
---------------------------------

Esta sección presenta la función principal para calcular una representación de un grupo finito :math:`G` que proporciona un carácter irreducible :math:`\chi` de :math:`G`.


.. _IrreducibleAffordingRepresentation:

IrreducibleAffordingRepresentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``IrreducibleAffordingRepresentation( chi )`` llamada con un carácter irreducible ``chi`` de un grupo :math:`G`, esta función devuelve un mapeo (representación) que mapea cada generador de :math:`G` a una matriz :math:`d \ast d`, donde :math:`d` es el grado de ``chi``. El grupo generado por estas matrices (la imagen del mapa) es un grupo de matrices que es isomorfo a :math:`G` módulo el núcleo del mapa. Si :math:`G` es un grupo solucionable, entonces no hay restricción en el grado de ``chi``. En el caso de que :math:`G` no se pueda resolver y el carácter ``chi`` tenga un grado mayor que :math:`100`, la salida tal vez no sea correcta. En este caso, a veces el mapeo de salida no ofrece el carácter dado o no devuelve ningún mapeo.


.. _IsAffordingRepresentation:

IsAffordingRepresentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``IsAffordingRepresentation( chi, rep )``. Si ``chi`` y ``rep`` son un carácter y una representación de un grupo :math:`G`, respectivamente, IsAffordingRepresentation_ devuelve ``true`` si la traza de ``rep(x)`` es igual a ``chi(x)`` para todos los elementos :math:`x` en :math:`G`.


Podemos obtener el tamaño de la imagen de esta representación por ``Size( Image( rep ) )`` y calcular el valor de un elemento arbitrario :math:`x` en :math:`G` por ``x ^ rep``.


Inducción
---------------------------------


.. _InducedSubgroupRepresentation:

InducedSubgroupRepresentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``InducedSubgroupRepresentation( G, rep )`` calcula una representación de :math:`G` inducida a partir de la representación ``rep`` de un subgrupo :math:`H` de :math:`G`. Si ``rep`` tiene un grado :math:`d`, entonces el grado de la representación de salida es :math:`d \ast | G: H |`.

Extensión
---------------------------------

En esta sección presentamos algunas funciones para extender una representación de un subgrupo a todo el grupo.

.. _ExtendedRepresentation:

ExtendedRepresentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``ExtendedRepresentation( chi, rep )`` actúa de la siguiente manera: supongamos que :math:`H` es un subgrupo de un grupo :math:`G` y ``chi`` es un carácter irreducible de :math:`G`, de modo que la restricción de ``chi`` a :math:`H`, digamos ``phi``, es irreducible. Si rep:math:`H` es una representación irreductible de :math:`H` que proporciona ``phi``, entonces ExtendedRepresentation_ extiende la representación ``rep`` de :math:`H` a una representación de :math:`G` que proporciona ``chi``. Esta llamada a la función puede resultar bastante cara cuando el representante de representación tiene un alto grado.


.. _ExtendedRepresentationNormal:

ExtendedRepresentationNormal
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.La función ``ExtendedRepresentationNormal(chi, rep)`` actúa de la siguiente manera: supongamos que :math:`H` es un subgrupo normal de un grupo :math:`G` y ``chi`` es un carácter irreducible de :math:`G`, de modo que la restricción de ``chi`` a :math:`H`, digamos ``phi``, es irreducible. Si ``rep`` es una representación irreducible de :math:`H` que proporciona ``phi``, ExtendedRepresentationNormal_ extiende la representación ``rep`` de :math:`H` a una representación de :math:`G` que proporciona ``chi``. Esta función es más eficaz que ExtendedRepresentation_.


Subgrupos Caracter
---------------------------------

Si :math:`\chi` es un carácter irreducible de un grupo :math:`G` y :math:`H` es un subgrupo de :math:`G` tal que la restricción de :math:`\chi` a :math:`H` tiene un constituyente lineal con multiplicidad uno, entonces llamamos a :math:`H` un subgrupo de caracteres relativo a :math:`\chi` o un :math:`\chi`-subgrupo.

.. _CharacterSubgroupRepresentation:

CharacterSubgroupRepresentation (para un caracter)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``CharacterSubgroupRepresentation( chi )`` o ``CharacterSubgroupRepresentation( chi, H )`` devuelve una representación que proporciona ``chi`` al encontrar un subgrupo de ``chi`` y utilizar el método descrito en [Dix93]. Si el segundo argumento es un ``chi``-subgrupo, entonces devuelve una representación que proporciona ``chi`` sin buscar un ``chi``-subgrupo. En este caso, se indica un error si no existe ningún ``chi``-subgrupo.

.. _IsCharacterSubgroup:

IsCharacterSubgroup
~~~~~~~~~~~~~~~~~~~

La función ``IsCharacterSubgroup( chi, H )`` devuelve ``true`` si :math:`H` es un  ``chi``-subgrupo y ``false`` en caso contrario.


.. _AllCharacterPSubgroups:

AllCharacterPSubgroups
~~~~~~~~~~~~~~~~~~~~~~

La función ``AllCharacterPSubgroups(G, chi)`` devuelve una lista de todos los subgrupos :math:`p` de ``G`` que son subgrupos ``chi``. Los subgrupos se eligen hasta la conjugación en :math:`G`.

.. _AllCharacterStandardSubgroups:

AllCharacterStandardSubgroups
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``AllCharacterStandardSubgroups( G, chi )`` devuelve una lista que contiene subgrupos bien descritos de ``G`` que son subgrupos ``chi``. Esta lista puede contener subgrupos de Sylow y sus subgrupos derivados, normalizadores y centralizadores en ``G``.

.. _AllCharacterSubgroups:

AllCharacterSubgroups
~~~~~~~~~~~~~~~~~~~~~

La función ``AllCharacterSubgroups( G, chi )`` devuelve una lista de todos los subgrupos ``chi`` de ``G`` entre la red de subgrupos. Esta llamada de función puede resultar bastante cara para grupos más grandes. La llamada es cara, en particular, si aún no se conoce la red de subgrupos del grupo dado.

Equivalent Representation
---------------------------------

.. _EquivalentRepresentation:

EquivalentRepresentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función ``EquivalentRepresentation( rep )`` calcula una representación equivalente a una representación irreducible rep transformando rep en una nueva base haciendo girar un vector (es decir, obteniendo los otros vectores base como imágenes debajo del primero bajo palabras en los generadores). Si la representación de entrada, ``rep``, es reducible, EquivalentRepresentation_ no devuelve ningún mapeo. En este caso, consulte la sección 3.