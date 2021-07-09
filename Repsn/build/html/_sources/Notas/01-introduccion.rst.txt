Introducción
=============

¿Para que sirve el paquete Repsn?
---------------------------------

El paquete ``Repsn`` sirve para **calcular representaciones matriciales en característica cero de grupos finitos**.

¿Cúales son sus principales funciones?
---------------------------------------------------

La mayoría de las funciones en ``Repsn`` se han escrito de acuerdo con el algoritmo descrito en la tesis doctoral del autor [DA03] y [DD10] (ver [DA05]).

La lista de funciones son:

- ``AlphaRepsn``
- ``LinearConstituentWithMultiplicityOne``
- :ref:`IsCharacterSubgroup`
- ``CharacterSubgroupLinearConstituent``
- ``MatrixRepsn``
- ``CharacterSylowSubgroup``
- ``RepresentationMatrixGenerators``
- ``CharacterSubgroup``
- :ref:`CharacterSubgroupRepresentation`
- :ref:`InducedSubgroupRepresentation`
- ``ModuleBasis``
- :ref:`ExtendedRepresentation`
- :ref:`ExtendedRepresentationNormal`
- ``AddToSubgpList``
- ``MinimalNormalSubgps``
- ``ReducedSubgroupCharacter``
- :ref:`EquivalentRepresentation`
- ``PSubgroups``
- ``StandardSubgroups``
- :ref:`AllCharacterStandardSubgroups`
- :ref:`AllCharacterPSubgroups`
- :ref:`AllCharacterSubgroups`
- ``CoversOfAlternatingGroupsRepresentation``
- ``CoversOfU43Representation``
- ``CoversOfO73Representation``
- ``CoversOfU62Representation``
- ``PerfectAbelianSocleRepresentation``
- ``PerfectRepresentation`` 
- :ref:`IrreducibleAffordingRepresentation`
- :ref:`IsAffordingRepresentation`
- ``DiagonalBlockMatrix``
- :ref:`ConstituentsOfRepresentation`
- ``EquivalentBlockRepresentation``
- ``IsReducibleRepresentation``

Nueva en ``REPSN 3.0.1``

- ``ProjectiveReps``
- ``GeneratorsProjective``
- ``FilteringCharacters``
- ``IrrRepsNotPrime``
- ``GallagherRepsn``
- ``SocleMoreComponents``


- Para construir representaciones de grupos simples y sus cubrimientos usamos el algoritmo descrito en [Dix93]. 

- Para utilizar este algoritmo para construir una representación de un grupo :math:`G` que proporcione un carácter irreducible :math:`\chi` de :math:`G`, necesitamos tener un subgrupo :math:`H` de :math:`G` tal que la restricción de :math:`\chi` a :math:`H` tenga un constituyente lineal con multiplicidad uno. En este caso decimos que :math:`H` es un subgrupo de caracteres relativo a :math:`\chi` (o un subgrupo :math:`\chi`). Un :math:`\chi`-subgrupo para cada carácter irreducible :math:`\chi` de grado menor que :math:`100` de grupos simples y sus cubiertas se enumeran en [DA06] y [DA07].


Todas las funciones de ``Repsn`` están escritas completamente en el lenguaje **GAP**. Se demuestra en [DA05] y [DD10] que el algoritmo es correcto para cualquier grupo con un carácter de grado menor que :math:`100`. De hecho, si el grupo tiene solución, no hay restricción en el grado del carácter. En la práctica el programa es bastante rápido cuando la titulación es pequeña, pero puede ser muy lento cuando es necesario llamar a alguno de los subprogramas que extienden representaciones irreductibles. En el último caso, el número de operaciones de elementos necesarios para ampliar una representación de grado :math:`d` es proporcional a :math:`d^{6}`.

Acerca de su implementación
---------------------------------------------------

``Repsn`` se implementa en el lenguaje **GAP** y se ejecuta en cualquier sistema que admita **GAP 4**. El paquete ``Repsn`` se carga en la sesión actual de **GAP** con el comando

.. code-block::

    gap> LoadPackage( "repsn", "0", false ); 

tal como se indica en la Sección "Loading a GAP Package" en el Manual de Referencia de **GAP**.

Para informar cualquier error u otro problema que se pueda encontrar a través del rastreador de problemas de ``Repsn``, podemos hacerlo `aquí <https://github.com/gap-packages/repsn/issues>`_.