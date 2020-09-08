Instalación de Poppler y Teseract
=================================

En esta sección se presenta como instalar las librerías ``Poppler`` y ``Pytesseract`` de Python requeridas para poder ejecutar de manera satisfactoria las funciones :py:meth:`lectura.Lector.archivo_a_texto`, :py:meth:`lectura.Lector.leer_pdf` y :py:meth:`lectura.leer_texto` del módulo :py:meth:`lectura` utilizando el OCR (Reconocimiento óptico de caracteres, OCR por sus siglas en ingles) de la librería ConTexto.

.. note::
    Los usuarios necesitaran contar con uno de los siguientes sistemas operativos, Windows 7, 8, 8.1 o 10 y contar con permisos de administrador, adicionalmente tener instalado la versión de Python 3.6 o una versión superior.

    La guía presentada a continuación se desarrolló utilizando la versión de Python 3.8.5 sobre el sistema operativo de Windows 10.


Instalación de Poppler
----------------------

.. _WinRAR: https://www.winrar.es/
.. _7zip: https://www.7-zip.org/

#. Descargar el ultimo archivo binario de poppler desde http://blog.alivate.com.au/poppler-windows/
#. Extraer el archivo dentro del disco local 'C:' en la carpeta de archivos de programa 'C:\\Program Files'. Para esto debe tener instalado un programa que permita descomprimir archivos (como `WinRAR`_ o `7zip`_), ya que el archivo binario se descarga en formato comprimido.
#. Agregar 'C:\\Program Files\\poppler-0.68.0_x86\\bin' al path del sistema haciendo lo siguiente:

   * En el explorador de archivos hacer clic derecho sobre “Este equipo” y luego clic en propiedades.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen01.png
       :align: center
       :alt: 
       :figclass: align-center

   * Hacer clic en la opción configuración avanzada de sistema ubicada en la parte superior izquierda.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen02.png
       :align: center
       :alt: 
       :figclass: align-center

   * Se abrirá una nueva ventana con las propiedades del sistema, aquí se debe hacer clic en la opción de variables de entorno.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen03.png
       :align: center
       :alt: 
       :figclass: align-center

   * En la sección de variables de sistema se debe hacer doble clic en la variable path.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen04.png
       :align: center
       :alt: 
       :figclass: align-center

   * Se abrirá una nueva ventana de edición de las variables de entorno, al hacer clic en el botón nuevo se podrá ingresar la ruta de la carpeta bin que está dentro del archivo que se extrajo previamente.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen05.png
       :align: center
       :alt: 
       :figclass: align-center

   * Se debe copiar la ruta donde se encuentra la carpeta bin de poppler, la ruta debería ser 'C:\\Program Files\\poppler-0.68.0\\bin' si el archivo binario de poppler se extrajo en archivos de programa.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen06.png
       :align: center
       :alt: 
       :figclass: align-center

   * Finalmente se agrega la ruta 'C:\\Program Files\\poppler-0.68.0\\bin' en la ventana de edición de variables de entorno y se hace clic en aceptar para cerrar todas las ventanas.
   
   .. figure:: _static/image/instalacion_poppler_teseract/Imagen07.png
       :align: center
       :alt: 
       :figclass: align-center


Instalación de Teseract
-----------------------

#. Desde https://github.com/UB-Mannheim/tesseract/wiki se debe descargar la versión más reciente de tesseract, aquí se descargara un archivo ejecutable (.exe) el cual se debe instalar haciendo doble clic sobre el archivo descargado y siguiendo las instrucciones de instalación.
#. Añadir otros idiomas al reconocimiento óptico de caracteres (OCR).

   * Para añadir otros idiomas al OCR se deben descargar los archivos de entrenamiento del idioma deseado, los cuales están disponibles en:  https://github.com/tesseract-ocr/tessdata . (Para el desarrollo de este manual se hará el ejemplo con el idioma español.)

       Para el idioma español se descargarán los archivos **spa.traineddata** y **spa_old.traineddata** los cuales están disponibles en los siguientes enlaces:

       * https://github.com/tesseract-ocr/tessdata/blob/master/spa.traineddata
       * https://github.com/tesseract-ocr/tessdata/blob/master/spa_old.traineddata

   Los archivos descargados se deben copiar y pegar en la carpeta tessdata que se encuentra en la carpeta tesseract-OCR que se creó al instalar el archivo .exe de tesseract. La ruta podría verse como 'C:\\Program Files\\Tesseract-OCR\\tessdata' que fue la ruta que se creó al momento de hacer el desarrollo de este manual.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen08.png
       :align: center
       :alt: 
       :figclass: align-center

#. Abrir la ventana de variables de entorno de la misma forma que se hizo para la :ref:`Instalación de Poppler`, y hacer doble clic en la variable path, para abrir el editor de las variables de entorno.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen09.png
       :align: center
       :alt: 
       :figclass: align-center

#. En el editor de las variables de entorno se debe hacer clic cobre el botón nuevo y colocar la ruta que se creó al momento de hacer la instalación de tessereact, la ruta podría verse como 'C:\\Program Files\\Tesseract-OCR'. Hacer clic en Aceptar.

   .. figure:: _static/image/instalacion_poppler_teseract/Imagen10.png
       :align: center
       :alt: 
       :figclass: align-center

#. En la terminal de Python se debe Instalar pytesseract mediante el uso del gestor de paquetes ``pip``

   .. code-block:: console

       pip install pytesseract

