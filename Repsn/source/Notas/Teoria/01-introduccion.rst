Introducción
=============

La idea es revisar algunos conceptos de la Teoría de Grupos y de Teoria de Representaciones, que son necesarios para entender el código de este paquete. La mayoría de estos contenidos estám fundamentados en la tesis del autor del Paquete.

De aquí en más, todos los grupos considerados son finitos.

Sea :math:`G` un grupo finito y sea :math:`V` un espacio vectorial de dimensión :math:`n` sobre :math:`\mathbb{C}`.

- :math:`GL(V)` denota el grupo de todas las trasformaciones lineales invertibles de :math:`V` en :math:`V`.

- Si :math:`G` es un subgrupo de :math:`GL(V)`, entonces un subespacio :math:`W` de :math:`V` es un subespacio *invariante* para :math:`G` si :math:`Wx=W` para todo :math:`x\in G`. Decimos que :math:`G` es *irreducible* si sus unicos subespacios invariantes son :math:`V` y :math:`\{0\}`.

- Dada una base de :math:`V` cada transformación lineal :math:`V\to V` se correónde univocamente con una matriz :math:`n\times n` con entradas en :math:`\mathbb{C}`. Esta correspondencia define un isomorfismo de :math:`GL(V)` sobre el grupo :math:`GL(n, \mathbb{C})` de todas las matrices no singulares :math:`n\times n` con entradas en :math:`\mathbb{C}`.

- Si :math:`G` es un subgrupo de :math:`GL(n, \mathbb{C})` entonces :math:`G` es *irreducible* su correspondiente subgrupo isomorfo en :math:`GL(V)` es *irreducible*. 


Definición
------------------

Una representación lineal de :math:`G` es un par :math:`(V, \rho)` tal que :math:`V` un espacio vectorial sobre :math:`\mathbb{C}` y :math:`\rho : G \to GL(V)` es un homomorfismo de grupos.

De manera similar, una representación matricial de :math:`G` en el espacio vectorial :math:`V` es un morfismo :math:`\rho : G\to GL(n, \mathbb{C})` donde :math:`n` es la dimensión de :math:`V` como :math:`\mathbb{C}`-espacio vectorial. :math:`dim_{\mathbb{C}}(V)=n` es el grado de :math:`\rho`.

