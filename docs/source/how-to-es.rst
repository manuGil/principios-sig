Cómo Usar este Tutorial
========================
Este sitio web contiene una lista de ejercicios que realizarás como parte del curso en línea *Sistemas de información geográfica 1*. El material fue traducido y adaptado del material original `Principles and Applications of Geographic Information Systems and Earth Observation <https://principles-and-applications-of-rs-and-gis.readthedocs.io/en/latest/>`_, desarrollado por la Universidad de Twente. 

A lo largo de los ejercicios, se le pedirá que realice varias actividades:

+ **Leer material de referencia** para obtener conocimientos teóricos de los conceptos utilizados en los ejercicios. Tenga en cuenta que los ejercicios no siempre proporcionan una explicación completa de los temas del curso. Este tutorial hacen referencia al Living Textbook, una enciclopedia de conceptos sobre Ciencias de Geo-Informacion,  verá un |ltb| `hipervínculo como este <#>`_ en el texto. El material en el Living Textbook esta disponible  únicamene en inglés. Utilize la traducción automática de su buscador (ej. Google Chrome) para hacer el material más accessible. Tome en cuenta que las traducciones automáticas no son perfectas, y siempre existe el riesgo de malinterpretar el significado del texto o de generar confusión. Por esta razón, también se proporcionará material de referencia en español a través de Google Classroom. Consulte al instructor sobre qué material es relevante para cada ejercicio.

+ **Realiza tareas con lápiz y papel** para reforzar tu comprensión. Aunque este es un curso en línea, se le pedirá que realice alguna tarea que requiera escribir cosas o realizar algunos cálculos. Puedes usar calculadoras u hojas de cálculo para computar los resultados pero recuerda que lo fundamental es que aprendas el procedimiento requerido para cada cálculo. Algunos de los procedimientos serán incluidos como parte del examen final.

+ **Realice tareas de software con QGIS** para adquirir habilidades y mejorar su comprensión de temas específicos. Utilizaremos la última versión LTR de `QGIS (Firenze 3.28) <https://qgis.org/downloads/QGIS-OSGeo4W-3.28.9-1.msi>`_. Para la mayoría de las tareas, se proporcionan tutoriales (descripciones o videos) sobre cómo hacer las cosas. Dichos tutoriales serán más detallados en los primeros ejercicios y menos detallados en ejercicios posteriores. El objetivo de este tutorial es que el participante se convierta en un usuario independiente de **QGIS** hacia el final del curso.

+ **Responde preguntas y participa en el Aula Virtual**. Cada ejercicio contiene preguntas que debe responder mientras realiza los ejercicios. Estas preguntas le ayudarán a evaluar su comprensión de un determinado concepto o tema. Por lo tanto, tómese el tiempo para analizarlos y brindar la mejor respuesta que pueda. Durante la sesión del Aula Virtual tendrá la oportunidad de aclarar dudas.

Al abordar estos ejercicios, debe utilizar todos los recursos que tenga a mano. Te explicaremos las cosas lo mejor que podamos, aunque es posible que en algún momento te quedes atascado en una determinada tarea. En esos casos, pondrá a prueba sus habilidades para la resolución de problemas. Esta es una habilidad esencial porque en el futuro es posible que deba aprender otro software de SIG.

Si encuentras problemas  con el software, puedes utilizar los siguientes recursos para encontrar respuestas:

+ El `QGIS manual <https://docs.qgis.org/3.16/es/docs/user_manual/index.html>`_ puede ayudarlo a encontrar respuestas sobre cómo usar las herramientas y las interfaces, y es el primero fuente que debe consultar cuando tenga una pregunta sobre cómo usar QGIS. Si una tarea específica no se explica completamente en el ejercicio; Proporcionaremos un enlace al manual de QGIS o un video tutorial.

+ Si tiene preguntas más avanzadas, por ejemplo, sobre cómo implementar un procedimiento o análisis de datos bastante específico relacionado con SIG y QGIS, entonces `GIS Stack exchange <https://gis.stackexchange.com/>`_ podría ayudarlo con eso.
  
+ También puede suscribirse a la lista de correo de usuarios de QGIS `<https://lists.osgeo.org/mailman/listinfo/qgis-user>`_ La lista de correo contiene un gran archivo de preguntas y respuestas de la comunidad de usuarios de QGIS. También puede publicar sus preguntas y alguien de la comunidad podría responderlas.

+ Assistente AI para obtener explicaciones detalladas sobre los conceptos y el software utilizados en los ejercicios. Por ejemplo, ChatGPT puede ayudarlo a encontrar respuestas a los ejercicios. Puede acceder a ChatGPT a través de `este enlace <https://chat.openai.com>`_.

+ Pregunte a los instructores del curso. Le señalarán materiales y documentos donde puede encontrar respuestas. Sin embargo, no pueden ayudarlo con las tareas y preguntas diseñadas explícitamente para pedirle que encuentre una respuesta por su cuenta. Esas tareas le ayudarán a adquirir habilidades y conocimientos. Por lo tanto, ¡saber cómo resolver problemas por ti mismo es una habilidad que debes cultivar!

.. tip::
   Marque las páginas anteriores en su navegador; de esa manera, puede acceder fácilmente al contenido cuando lo necesite.


Lista de Ejercicios
-------------------------
El contenido del curso se divide en seis sesiones. Cada sesión contiene una serie de ejercicios que se enumeran a continuación:

+----------------------------+-----------------------------------------+
| Sesión                     | Ejercicios                              |
+============================+=========================================+
| Sesión 1                   | * Introducción a QGIS                   |               
|                            | * Modelos de datos espaciales           |
+----------------------------+-----------------------------------------+
| Sesión 2                   | * Adquisición de datos                  |
|                            | * Sistemas de referencia espacial       |
+----------------------------+-----------------------------------------+
| Sesión 3                   | * Análisis de datos vectoriales         |
+----------------------------+-----------------------------------------+
| Sesión 4                   | * Análisis de datos ráster              |
+----------------------------+-----------------------------------------+
| Sesión 5                   | * Visualización cartográfica            |
+----------------------------+-----------------------------------------+
| Sesión 6                   |  ---                                    |
+----------------------------+-----------------------------------------+

Convenciones
---------------
A lo largo de los ejercicios, usamos algunas convenciones para resaltar el contenido que requiere una atención especial. Estos son los siguientes:

.. note:: 
   **QGIS.**
   Esto proporcionará explicaciones adicionales específicas sobre cómo funciona QGIS.

.. note:: 
   **Reflexión.**
   Esto describirá situaciones o preguntas que requieran un profundo nivel de razonamiento. Debería ver este contenido como *acertijos mentales* que le ayudarán a ampliar su comprensión de ciertos temas.  

.. important:: 
   **Recursos.**
   Esto describirá el software y los  datos necesarios para completar un determinado ejercicio. No todos los ejercicios incluyen el uso de datos; por lo tanto, ésta convención aparecerá solo en las secciones que lo necesiten.

.. attention:: 
   **Pregunta.**
   Esto presentará preguntas que tendrá que responder durante los ejercicios e **incluirlas en el reporte de ejercicios despues de cada sesión**. Escriba las respuesta y si tienes dudas pregunta durante las sesiones en el aula virtual. Para preparar el reporte de ejercicios utilice la plantilla que se proporciona a través de Google Classroom.



.. sectionauthor:: Manuel G. Garcia
