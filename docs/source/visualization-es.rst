Visualización Cartográfica
===========================

Gramática Cartográfica
--------------------------

La gramática cartográfica define un conjunto de "reglas generales" para la |ltb| `Visualización <Visualization_>`_ de datos espaciales y la representación correcta de información espacial y temporal en un |ltb| `Mapa <Map_>`_. La gramática cartográfica garantiza que los mapas comuniquen información de forma eficaz al usuario del mapa.

Para obtener una explicación más detallada sobre la gramática cartográfica, visite https://kartoweb.itc.nl/TMT
El **Tutor de mapas temáticos** le ayudará a comprender qué variable visual utilizar según el tipo de datos que desee visualizar. Esto le ayudará a completar las prácticas en este ejercicio.

.. attention:: 
    **Pregunta.**
    Suponga que se le pide que haga un mapa con los siguientes datos (número de fisioterapeutas por cada 100,000 habitantes para cada povincia de los Países Bajos):

    .. image:: _static/img/fysio-data.png
       :align: center

    #. ¿Cuál es la naturaleza de estos datos, ej. calitativa, quantitativa, etc.? 
    #. ¿Qué variables visuales son adecuadas para representar estos datos?
    #. ¿Qué tipo de mapa temático usaría para representar estos datos?

Práctica 1
    Suponga que tiene que diseñar símbolos para un mapa geológico a escala pequeña (:math:`1: 100,000`). Los siguientes tipos de rocas deben estar representados en el mapa:
    
    + roca ígnea
    + roca metamórfica
    + roca sedimentaria consolidada
    + roca sedimentaria no consolidada

    También hay que mapear la morfología del terreno, según la siguiente clasificación:

    + terreno relativamente plano (pendientes 0-7%)
    + terreno ondulado a montañoso (pendientes 7-30%)
    + terreno escarpado (pendientes> 30%)
 
    En el mapa pueden ocurrir todas las combinaciones posibles de tipos de rocas y clases de terreno. Describa cómo representaría toda la información en este mapa: *no tiene que crear el mapa o los símbolos de la leyenda*, en su lugar, describa:
    
    + ¿Qué capa(s) de información pondría en el mapa y qué variable(s) visual(es) deberían usarse para combinar esas capas en un solo mapa?,
    + ¿Qué títulos de leyenda y categorías usarías? y
    + ¿Qué tipo de mapa(s) usaría para representar los datos?

---------------------------------------------------------

Revisión Crítica de Mapas
--------------------------------

Con lo que aprendió en la sección anterior sobre Gramática cartográfica; podrá observar críticamente mapas existentes e identificar sus deficiencias.

Práctica 2
    Observe cuidadosamente los dos mapas a continuación, y use lo que ha aprendido sobre la representación de datos cuantitativos para analizarlos críticamente.

   .. image:: _static/img/alumni-map.png 
      :align: center

   .. image:: _static/img/construction-map.png 
      :align: center

.. attention:: 
    **Pregunta.**
    
    + ¿Cuáles son algunas de las deficiencias en estos mapas?
    + ¿Cómo resolvería tales deficiencias? Dé ejemplos.


Práctica 3
    Busque un mapa (en los periódicos, en la web, en un trabajo de investigación o en un libro) que le parezca interesante. Puede seleccionar un mapa en el que crea que hay algún problema con la visualzación de los datos, o porque es un mapa que le gusta, o que crea que es un mapa bien hecho. Adjunte el mapa en el reporte, y conteste las siguentes preguntas.

.. attention:: 
    **Pregunta.**
   
    + ¿Qué tiene de interesante el mapa que eligió?
    + ¿Cuáles son los defectos y fortalezas del mapa?

---------------------------------------------


Crear un Mapa Topográfico
--------------------------

En esta sección, creará un mapa topográfico a pequeña escala de una parte de Suiza, que incluya la representación del terreno en 3D utilizando sombreado del terreno y tintes de capa. **El mapa deberá ser entregado como parte de la tarea** `Mapa Topografico <https://classroom.google.com/c/NjE1NzAzMTI0MDcw/a/NjE1NzAzMTI0MTYz/details>`_, con un valor de **10 puntos**.

Pare esta tarea seguirá el principio de "buscar, probar y aprender". Eso significa que no se le mostrará cómo hacer las cosas. En su lugar, se le pedirá que realice tareas específicas y  se le proporciona información relevante que le ayudará a completar las tarea. Las habilidades en QGIS que necesitará para este ejercicio son las mismas que aprendió en ejercicios anteriores.

Concéntrese en la producción de un mapa bien diseñado cartográficamente. Será su responsabilidad estudiar lo que se le pide para esta tarea, y buscar ideas y respuestas en el material de referecia que se menciona más adelante. Luego de eso, deberá decidir qué estrategia utilizar para completar la tarea.

.. important:: 
    **Recursos.**
    Necesitará la última versión LTR de `QGIS (Firenze 3.28) <https://qgis.org/downloads/QGIS-OSGeo4W-3.28.9-1.msi>`_, y los  datos `visualization.zip <visualisation_>`_.

Material de Referencia
^^^^^^^^^^^^^^^^^^^^^^^^^

+ Ejercicios anteriores, usando QGIS;
+ El `manual de aprendizaje de QGIS <https://docs.qgis.org/3.28/es/docs/training_manual/index.html>`_ y la `guía de usuario de QGIS <https://docs.qgis.org/3.28/es/docs/user_manual/index.html>`_.
+ el material de lectura y diapositivas sobre visualización cartográfica (disponible en Classroom);
+ El apéndice sobre :ref:`shaded-models`, que contiene introducciones  para crear un modelo de sombras del terreno y el uso de otras herramientas útiles.


Descripción de Datos para éste Mapa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Ésta es una descripción detallada de los  datos para crear el mapa topográfico.

Datos ráster
    ``dem_90m.tif`` parte de un *Modelo de elevación digital*, producido por la NASA durante la misión *Shuttle Radar Topography Mission* (SRTM). Durante una misión de 11 días en febrero de 2000, la NASA obtuvo datos de elevación a una escala casi global para generar la base de datos topográfica digital de alta resolución más completa de la Tierra. La SRTM consistía en un sistema de radar especialmente modificado que volaba a bordo del *tramsportador Endeavour*. Los datos están disponibles gratuitamente en http://www.jpl.nasa.gov/srtm.

    Cada celda tiene un valor que representa la altura en metros. Los datos SRTM se almacenaron originalmente utilizando coordenadas geográficas. Sin embargo, esta versión está en coordenadas (metros) **zona UTM 32N ** y en el **datum WGS84** (EPSG: 32632).

Datos vectoriales
    Todos los datos vectoriales se obtuvieron de “EuroGlobalMap” (EGM), una base de datos paneuropea a pequeña escala. Fueron colectados como parte de una iniciativa de *EuroGeographics*, en cooperación con todos los servicios topográficos europeos. Las capas vectoriales proporcionadas son de la versión 7.0 (septiembre de 2013). Los datos de EGM están destinados a utilizarse en mapas a escalas de aproximadamente :math:`1: 1.000.000`. Los datos de EGM se almacenaron inicialmente utilizando coordenadas geográficas. Sin embargo, esta versión está en coordenadas  **zona UTM 32N** y en el **datum WGS84** (código EPSG 32632). Los datos EGM están abiertos al público y se puede descargar desde http://www.eurogeographics.org/products-and-services/euroglobalmap.

    Para este ejercicio, hemos eliminado muchos de los atributos en los datos originales, y hemos mantenido sólo una pequeña selección. A continuación, se ofrece una descripción de los atributos para cada conjunto de datos:

    + ``builtUpArea.gpkg`` (área urbana): NAMN1 = Nombre en alemán;
    + ``lakes.gpkg`` (lagos): NAMN1 = Nombre en alemán;
    + ``watercourse.gpkg`` (causes de agua): NAMN1 = Nombre en alemán;
    + ``railways.gpkg`` (vías férreas): TYPE (tipo): 31 = secundario, 33 = primario; TUNNEL: 0 = no es parte de un túnel; 1 = parte de un túnel
    + ``ElevP.gpkg`` (punto de elevación): picos y veredas más importantes. Atributos NAMN1 = nombre en alemán; ZV2 = elevación en metros sobre el nivel del mar;
    + ``towns.gpkg`` (poblados) : NAMN1 = nombre en alemán; PPL = población (in 2013);


    Los datos de la carreteras de EGM son notoriamente incompletos y demasiado generales para la escala del mapa que creará. Por lo tanto, incluimos datos de la base de datos *OpenStreetMap*. Extrajimos los datos de las carreteras para las categorías que representan las carreteras principales. Los datos de OSM se almacenaron originalmente utilizando coordenadas geográficas. Sin embargo, esta versión está en coordenadas  **zona UTM 32N** y en el **datum WGS84** (EPSG: 32632). En esta versión solo se mantuvo una pequeña selección de los atributos originales de OSM. La capa de datos se describe a continuación:

    ``osm_roads.gpkg``: **osm_id**: identificador único para cada segmento de carretera; **type** (tipo): motorway (autopista), primary (primaria), secondary (secundaria), o trunk (carretera principal); **tunnel** (túnel): 0 = carretera que no es parte de un túnel; 1 = carreterna en un túnel.

        *Tenga en cuenta que los datos de OSM son muy detallados. Depende de usted decidir si necesita todas las categorías, o si es mejor eliminar o no mostrar algunos tipos de carreteras. Ésto dependerá de los requisitos del usuario del mapa y de las elecciones de simbología que haga para ésta  y otras capas en el mapa.*

Elaboración del Mapa
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Abra el proyecto QGIS ``topographic_map.qgs``, el proyecto contiene todas las capas que necesitará. Elabore un mapa topográfico de una parte de Suiza (el "Berner Oberland", tierras altas de Kanton Bern), que *cumpla con los siguientes requisitos:*

   1. El mapa presentará datos en las categorías de información que se mencionan a continuación. Las visualizaciones deberán ser correctas para el tipo de datos, y también deberán adaptase para cada combinación específica de datos. Las categorías de información que deberán aparece en el mapa son:

      A. **Terreno**. La forma del terreno se visualizará utilizando un modelo de sombreado del terreno y tintes de capa. Consulte el apéndice :ref:`shaded-models` para saber cómo crear dicho modelo. Dé prioridad al diseño de una visualización razonable y legible. Es decir, la visualizacón deberá darle  una impresión clara de la forma de las montañas en este país, al usuario del mapa.
      B. **Infraestructura**: *carreteras y vías ferreas*. El mapa deberá mostrar la numeración de las carreteras/vías ferreas más importantes.
      C. **Ciudades y pueblos**. Deberá incluir los nombres de lugares para al menos las ciudades más grandes.
      D. **Hidrografía**: *lagos y ríos*. Los ríos y lagos más importantes deberán mostrar sus nombres.
      E. Opcionalmente, el mapa deberá incluir datos adicionales que recopile de otras fuentes (por ejemplo, Internet, atlas y otros). Información adicional útil puede ser los *nombres de las cimas de las montañas*, los *sitios turísticos famosos en la región* entre otros.

   2. El mapa deberá  diseñarse para un tamaño de papel *A4 o Carta*, con orientación horizontal. Los límites exteriores del mapa deberán ser rectangulares y deberán coincidir con la extensión del modelo de elevación degital. La proyección de los datos deberá ser Universal Transverse Mercator **(UTM) Zone 32N** y en el  datum **WGS84**. Los datos ya se proporcionan en esta proyección.

   3. El mapa deberá contener toda la información marginal necesaria, por ejemplo: título, leyenda, barra de escala, etc. Además incluya su nombre completo.

   4. El mapa se deberá crear para una impresión en color. Cuando el mapa esté listo, expórtelo como un archivo PDF. Utilice la herramienta **Exportar como PDF** de QGIS.

   5. Entregue una copia en PDF a través de Classroom.

   .. important:: 
      Esta práctica le llevará mucho más tiempo de lo que cree. Antes de entregar el mapa, asegurece de que las reglas de la gramática cartográfica se han aplicado correctamente. De ser necesario, pida a un miembro de su familia, amigos, colegas or compañeros del curso que revisen su mapa y le den consejos de cómo mejorarlo.

.. sectionauthor:: Barend Köbben, André da Silva Mano & Manuel Garcia Alvarez