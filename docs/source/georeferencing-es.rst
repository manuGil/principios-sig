Sistemas de Referencia Espacial
=================================

Superficies de Referencia
----------------------------

Usamos una |ltb| `Superficie de referencia <Reference surface_>`_ (es decir, sistema de referencia) para aproximar la forma de la Tierra. Un datum horizontal (también llamado datum geodésico) es un modelo utilizado para definir ubicaciones sobre la Tierra. Un |ltb| `datum vertical <Vertical datum_>`_ es un modelo utilizado para medir elevaciones, que está relacionado con el |ltb| `Geoide <Geoid_>`_. Las elevaciones suelen estar relacionadas con el nivel medio del mar, y la posición horizontal se mide utilizando un |ltb| `Elipsoide <Ellipsoid_>`_ como referencia.

.. attention:: 
   **Pregunta.**
   En los Países Bajos, la elevación se mide tomando como referencia el nivel del agua en los canales de Amsterdam. Este datum vertical se llama *Normal Amsterdams Peil (NAP)*. Una gran parte de los Países Bajos se inundaría si no tuviéramos dunas o diques, ver:numref:`figsea-level`. De hecho, toda la tierra por debajo de 0 metros NAP sería mar. Los diferentes países miden la altura haciendo referencia a diferentes niveles medios del mar. ¿Por qué no utilizamos una sola medida para todos los países?

   .. _figsea-level:
   .. figure:: _static/img/sea-level-nl.jpg
      :alt: sea level comparison
      :figclass: align-center

      Izquierda: Los Países Bajos comparados con el nivel del mar, según `Jan Arkesteijn <https://nl.wikipedia.org/wiki/Bestand:The_Netherlands_compared_to_sealevel.png>`_. Derecha: la línea costera actual de los Países Bajos.


.. attention::
   **Pregunta.**

   + ¿Por qué utilizamos diferentes superficies de referencia para posicionamiento horizontal y vertical?
   + ¿Defina con sus propias palabras la diferencia entre un datum horizontal local y uno global?
   + ¿Cuál es el datum horizontal para Guatemala?
   + ¿Cómo están relacionados los datums horizontal y vertical?

----------------------------------------------------------

Sistemas coordenados
----------------------

En el mapeo, un |ltb| `sistema de coordenadas <Coordinate system_>`_ se utiliza para determinar de forma precisa la posición de un lugar sobre la superficie de la Tierra.

.. important:: 
   **Recursos.**
   Necesitará la última versión LTR de `QGIS (A Hannover 3.16) <https://qgis.org/en/site/forusers/download.html>`_, más los datos `georeferencing.zip <data_georeferencing_>`_. Cuando descomprima el archivo, encontrará los siguiente:

   + ``DEM10.tif`` (y archivos auxiliares) – un modelo digital de elavación en formato raster;
   + ``Topographical_map_dominica.tif`` – mapa raster (sin georeferencia);
   + ``Topographic_map_hengelo.tif`` – mapa raster (sin georeferencia);
   + ``Control_points.csv`` – table con punto collectados con un GPS;
   + ``Floodzones.gpkg`` – datos vectoriales (polígonos) sobre áreas inundables;
   + ``Highways.gpk`` – capa vectorial de líneas;
   + ``Parish.gpkg`` – capa vectorial de límites administrativos (parish level);
   + ``Rivers.gpkg`` – capa vectorial de ríos.

Práctica 1
   Defina con sus propias palabras la diferencia entre |ltb| `sistemas de coordenadas <Coordinate system_>`_ y |ltb| `sistema de coordenadas planas <Planar coordinate system_>`_. 

El sistema de coordenadas global más utilizado es el |ltb| `Sistema de coordenadas geográficas <Geographic coordinate system_>`_. Consiste en líneas de latitud y longitud geográficas. Las líneas de igual latitud se llaman paralelos y forman círculos en la superficie del elipsoide. Las líneas de igual longitud se denominan meridianos y forman elipses (elipses de meridianos) en el elipsoide.

Los sistemas de coordenadas geográficas utilizan la latitud y la longitud para describir una posición en la superficie de la Tierra. La *Latitud* es cero en el Ecuador y aumenta hacia ambos polos hasta :math:`90° N` o :math:`90° S`. La latitud es positiva en el hemisferio norte y negativa en el hemisferio sur. La *longitud* se mide desde el meridiano de Greenwich, donde es cero, y aumenta hacia el este hasta :math:`180° E`, y hacia el oeste hasta :math:`180° O`. La longitud es positiva hacia el este y negativa hacia el oeste.

Las coordenadas geográficas se expresan normalmente en dos formatos. En *Grados, Minutos, Segundos*  (GMS) o en formato *Decimal*. Sin embargo, desde un punto de vista computacional, se prefiere el formato decimal porque facilita los cálculos en una computadora. Si usa el formato decimal, la computadora lo leerá como un número decimal, pero si usa el formato GMS, lo más probable es que la computadora lo lea como una cadena de texto sin significado numérico o matemático.

Por ejemplo, Enschede (ciudad en los Países Bajos) se ubica en:

   + Latitud: :math:`52°13′05″ N` (formato GMS)       or       :math:`52.21806` (formato decimal)
   + Longitud: :math:`6°53′44″ E` (formato GMS)       or       :math:`6.895556` (formato decimal)


Práctica 2
   Utilice Google Maps para encontrar lo que hay en las siguientes coordenadas.

   ============   =============     =======================
   Latitud        Longitud          ¿Qué hay en este lugar
   ============   =============     =======================
   52°13′05″ N    6°53′44″ O        \
   52°13′05″ S    6°53′44″ E        \
   52°13′05″ S    6°53′44″ O        \
   ============   =============     =======================

Práctica 3
   Abra un nuevo proyecto en QGIS y mapee las ubicaciones contenidas en el archivo ``control_points.csv``. Este archivo contiene coordenadas geográficas capturadas con un dispositivo GPS. Si necesita ayuda consulte la sección  :ref:`spatialising-data`.


   .. attention:: 
      **Pregunta.**
      ¿Cuál fue el sistema de coordenadas geográficas (datum geodésico) utilizado en el archivo ``control_points.xlsx``?


Práctica 4
   Abra cada uno de los datasets restantes en QGIS y revise si cada dataset tiene una referencia espacial o no.

   .. attention::
      **Pregunta.**
      
       #. ¿Hay algún dataset con un sistema de coordenadas geográficas?
       #. ¿Qué sistema de coordenadas geográficas se utilizó?

----------------------------------------------------

Proyecciones de Mapas
-----------------------

Una |ltb| `proyección cartográfica <Map projection_>`_ es una técnica matemáticamente para representar la superficie curva de la Tierra en un mapa plano. Aplanar una superficie esférica es una tarea imperfecta, como puede experimentar usted mismo cuando está pelando una naranja y tratando de aplanar la piel. Para representar la superficie de la Tierra en un mapa, usamos una proyección de mapa. Las proyecciones de mapas se establecen para propósitos específicos y todas tiene distorsiones. Por lo tanto, comprender la |ltb| `clasificación de las proyecciones cartográficas <Projection classification_>`_ es fundamental a la hora de elegir una proyección cartográfica adecuada.

No importa qué proyección de mapa elija, siempre tendrá ciertas distorsiones. Puede experimentar con las distorciones para caso de la proyección de Mercator (ampliamente utilizada) usando este enlace: http://hive.sewanee.edu/pridepj0/286/mercatorMap.html


.. attention:: 
   **Pregunta.**
   
   + Suponga que desea producir un mapa a pequeña escala de Guatemala. El mapa debe mostrar las densidades de población de las diferentes municipios. ¿Qué tipo de proyección de mapa sugeriría (considere la clase de proyección, la propiedad y otros parámetros de proyección)? Esta herramienta interactiva puede ayudarle a seleccionar una proyección de mapa adecuada: http://projectionwizard.org
   + ¿Cuál es la proyección cartográfica oficial para Guatemala?

Práctica 5
   Cargue los datasets vectoriales y ráster que descargó en nuevo proyecto de QGIS y responda las siguientes preguntas:
   
   + ¿Hay datasets que utilicen una proyección cartográfica?
   + ¿Qué sistema de coordenadas geográficas utilizan los datasets que están proyectados?

   Para esta tarea, es posible que desee ver primero el video `usando sistemas de coordenadas <https://vimeo.com/album/4389527/video/201997378>`_.

.. raw:: html

   <div style="padding:56.25% 0 0 0;position:relative;"><iframe width="560" height="315" src="https://www.youtube.com/embed/oFRpGMq5Tbc" title="YouTube video player" frameborder="0" style="position:absolute;top:0;left:0;width:100%;height:100%;" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

\


--------------------------------------

Transformación de Coordenadas
--------------------------------


Los usuarios de información geográfica a menudo necesitan transformar datasets de un sistema de coordenadas en particular a otro. Las |ltb| `Transformaciones de coordenadas <Coordinate transformation_>`_ son necesarias porque algunos análisis requieren unidades de medida planas.
En otros casos, el usuario del mapa tiene requisitos especiales sobre cómo representar datos espaciales en un mapa.

.. attention:: 
   **Pregunta.**
   Quizás haya notado que las siguientes capas tienen diferentes sistemas de coordenadas y datums: *'DEM'*, *'floodzones'*, *'highways'*, *'parish'* y *'rivers'*.
   
    + ¿Qué problemas pueden surgir al dejar estas capas con sus sistemas de coordenadas actuales?
    + Si tuviera que transformar todas las capas a un misto sistema de coordenadas, ¿qué sistema de coordenadas elegiría? ¿Qué criterios determinan la elección de un sitema de coordenadas común? 


Práctica 6
   Después de elegir un sistema de coordenadas proyectadas y un datum para sus datasets, use QGIS para hacer las transformaciones (re-proyecciones). Preste atención a si las capas requieren una transformación de proyección  o una transformación de proyección y datum. **El orden en el que applican las transformaciones es muy importante.**

.. note:: 
   **QGIS.**
   Si necesita ayuda, cosulte el manual de QGIS, sección `proyectando y transformando datos <https://docs.qgis.org/3.16/es/docs/training_manual/vector_analysis/reproject_transform.html>`_.

Práctica 7
   A veces, al visualizar datos en QGIS, algunas de las capas no se alinean entre sí. Esto puede deberse a que una capa tiene definido un sistema de coordenadas **desconocido o incorrecto**. O la capa no está *georreferenciada* (no hace referencia a ningún sistema de coordenadas). ¿Tiene alguna capa que no se alinea con el resto de las capas en su proyecto actual?

-------------------------------------------

Preguntas Adicionales
----------------------

.. attention::
   Abra el  archivo ``topographic_map_hengelo.tif`` que contienen una image de un mapa topográfico.

      A. ¿Está la imagen georreferenciada?
      B. Haga zoom a la leyenda en la parte inferior-central de la pantalla. ¿Cuántos sistemas de coordenadas están representados en el mapa topográfico?
      C. ¿Para cuál de los tres sistemas hay una cuadrícula en el mapa topográfico?

.. sectionauthor:: Richard Knippers, André da Silva Mano & Manuel Garcia Alvarez
