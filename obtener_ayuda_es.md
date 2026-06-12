# Obtener ayuda

[Comuníquese con la comunidad de Slicer o con los socios comerciales](https://slicer.readthedocs.io/en/latest/user_guide/about.html#contact-us) si tiene alguna pregunta, informe de errores o solicitud de mejora, siguiendo las pautas que se describen a continuación.

## Necesito ayuda para usar Slicer

- Puede comenzar escribiendo su pregunta en la búsqueda web de Google. Es muy probable que su pregunta ya se haya formulado y respondido antes, ya que todas las preguntas que se han hecho sobre Slicer están disponibles públicamente e indexadas por Google. Las fuentes de información más actualizadas son el [foro de Slicer](https://discourse.slicer.org) y la [documentación de Slicer en Read the Docs](https://slicer.readthedocs.io/). Google puede encontrar discusiones más antiguas en las antiguas listas de correo y páginas wiki de Slicer, que pueden o no ser exactamente precisas para la versión actual de Slicer, pero que aún pueden ofrecer pistas útiles.

- Haga su mejor esfuerzo por resolver el problema leyendo la [documentación](https://slicer.readthedocs.io), el [portafolio de materiales de capacitación](https://training.slicer.org/) y revisando los registros de errores (en la barra de menú de la aplicación: View->Error log).

- Si aún no tiene claro qué hacer: [haga una pregunta en el foro de Slicer](https://discourse.slicer.org). Además de describir la pregunta específica, es útil que describa el contexto de su pregunta (quién es usted, en qué está trabajando, por qué es importante, cuál es el objetivo general de su proyecto). Conocer más sobre usted y su proyecto aumenta la probabilidad de que alguien se ofrezca a responder la pregunta, y puede obtener una respuesta más relevante.

## Quiero informar de un problema

Constantemente realizamos correcciones y mejoras, por lo tanto, antes de informar de cualquier problema:

1. Confirme que el problema todavía existe en la Versión estable actual de Slicer.

2. Si todavía existe en la Versión estable de Slicer, confirme que el problema todavía existe en la última Versión preliminar de Slicer.

Si le resulta difícil encontrar respuestas usando la función de búsqueda del [foro de Slicer](https://discourse.slicer.org) o mediante búsquedas en internet como Google, pruebe un modelo de lenguaje grande como Microsoft Copilot, OpenAI ChatGPT, Google Gemini, etc.

Si no está seguro de si Slicer se comporta de forma incorrecta o si no lo está usando correctamente, entonces [pregunte al respecto en el foro de Slicer](https://discourse.slicer.org/c/support) (en la categoría `Support`).
Si está *seguro* de que Slicer no funciona como debería, entonces [envíe un informe de error en el rastreador de problemas de Slicer](https://github.com/Slicer/Slicer/issues/new?assignees=&labels=type%3Abug&template=bug_report.md).

En su pregunta o informe, proporcione toda la información que se describe en la [plantilla de informe de errores](https://github.com/Slicer/Slicer/blob/main/.github/ISSUE_TEMPLATE/bug_report.md#summary).

Consejo

No sea anónimo: las personas reales que se esfuerzan por resolver problemas reales tienen más probabilidades de recibir ayuda valiosa. Si cuenta sobre usted y su proyecto, puede recibir más atención y el problema puede resolverse antes.

## Me gustaría solicitar una mejora o una nueva función

Primero busque en el [foro de Slicer](https://discourse.slicer.org) y en el [rastreador de problemas de Slicer](https://github.com/Slicer/Slicer/issues?q=is%3Aissue+is%3Aopen+label%3Atype%3Aenhancement) para ver si alguien ya solicitó esta función. Si encuentra una solicitud muy similar, indíquenos que a usted también le interesa agregando un comentario o un "pulgar arriba" (thumbs-up) a la publicación principal.

Si no encuentra una solicitud de función similar, escriba una publicación en la [categoría de solicitudes de funciones](https://discourse.slicer.org/c/support/feature-requests) para discutirla con los desarrolladores de Slicer y los miembros de la comunidad.

Consejo

Si escribe sobre usted y su proyecto, hay más probabilidades de que se trabaje en su solicitud. Describa qué asistencia puede ofrecer para la implementación (su propio tiempo, financiamiento, etc.).

## Me gustaría informar a la comunidad de Slicer cómo Slicer me ayudó en mi investigación

Envíenos la cita de su artículo publicándola en la [categoría Community del foro de Slicer](https://discourse.slicer.org/c/community/).

Contexto: el financiamiento de Slicer se proporciona a través de mecanismos competitivos, principalmente por el gobierno de los Estados Unidos y, en menor medida, mediante financiamiento de otros gobiernos. La justificación de esos recursos es que Slicer hace posible el trabajo científico. Conocer las publicaciones científicas que Slicer ha hecho posibles es un paso fundamental en este proceso. Dada la naturaleza internacional de la comunidad de Slicer, la nacionalidad de los científicos no es importante. Cada buen artículo cuenta.

## Solución de problemas

### La aplicación Slicer no se inicia

- Es posible que la CPU o las capacidades gráficas de su computadora no cumplan con los [requisitos mínimos del sistema](https://slicer.readthedocs.io/en/latest/user_guide/getting_started.html#system-requirements).

  * Actualizar el controlador de su tarjeta gráfica puede solucionar algunos problemas, pero si eso no ayuda y tiene una computadora antigua, es posible que deba actualizar a una computadora de fabricación más reciente o cambiar a un renderizador por software.
Un renderizador por software es particularmente útil para ejecutar Slicer en una máquina sin pantalla (headless), como una máquina virtual en un proveedor de computación en la nube con una CPU potente pero sin GPU, usando el Protocolo de Escritorio Remoto (RDP).

            Nota

        **Configuración de un renderizador por software en Windows:**

    +             Descargue el controlador Mesa OpenGL desde <https://github.com/pal1000/mesa-dist-win/releases> (versión MSVC: mesa3d-X.Y.Z-release-msvc.7z). Última prueba con la versión <https://github.com/pal1000/mesa-dist-win/releases/tag/22.2.0>

    +             Extraiga el archivo comprimido y copie los archivos de la carpeta x64 en la subcarpeta bin del árbol de instalación de Slicer.

    +             Configure el renderizador estableciendo variables de entorno y luego inicie Slicer:

  
  

```
set GALLIUM_DRIVER=llvmpipe
set MESA_GL_VERSION_OVERRIDE=3.3COMPAT
Slicer.exe

```

        Se ha comprobado que este renderizador por software funciona bien en máquinas virtuales Windows en Microsoft Azure.

- Slicer puede no funcionar si está instalado en una carpeta que tiene caracteres especiales en su nombre. Intente instalar Slicer en una ruta que solo contenga letras latinas y números (a-z, 0-9).

- Es posible que la configuración de su Slicer se haya dañado.

  * Intente iniciar Slicer usando `Slicer.exe --disable-settings` (si esto soluciona el problema, elimine los archivos Slicer.ini y Slicer-.ini de su directorio de configuración de Slicer).    * Cambie el nombre o elimine su directorio de configuración de Slicer (por ejemplo, `c:\Users\<sunombredeusuario>\AppData\Roaming\slicer.org`). Consulte las instrucciones para obtener el directorio de configuración [aquí](https://slicer.readthedocs.io/en/latest/user_guide/settings.html#settings-file-location). Intente iniciar Slicer.

    * Puede haber bibliotecas en conflicto o incompatibles en la ruta de su sistema (lo más probable es que se deba a la instalación de aplicaciones que colocan bibliotecas en una ubicación incorrecta de su sistema). Revise los registros de su sistema para más detalles e informe del problema.

      +                 En Windows:

        - Inicie el Visor de eventos (eventvwr.exe), seleccione Registros de Windows / Aplicación y busque el error de la aplicación. Si hay un problema de carga de una DLL, aparecerá una línea similar a esta: `Faulting module path: <algo>.dll`. Si encontró una línea similar a esta, intente la siguiente solución alternativa: inicie una ventana de comandos. Escriba `set path=` para borrar la variable de ruta. Escriba Slicer.exe para iniciar Slicer. Si Slicer se inicia correctamente, entonces necesita eliminar los elementos innecesarios de la ruta del sistema (o eliminar las bibliotecas instaladas en ubicaciones incorrectas).

        - Si Slicer todavía no funciona, recopile más información e informe del problema:

          * Obtenga información sobre las dependencias de DLL usando la herramienta Dependency Walker:

            +                             Descargue depends.exe desde [aquí](https://www.dependencywalker.com/)

            +                             Ejecute depends.exe usando el lanzador de Slicer: `Slicer.exe --launch path\to\depends.exe "bin\SlicerApp-real.exe"`

            +                             En Dependency Walker: asegúrese de que se muestren las rutas completas de las DLL (haga clic en View / Full paths si solo ve los nombres de las DLL). Use File / Save as… => Comma Separated Values (*.csv) para guardar los registros en un archivo.

          * Habilite el registro de carga de procesos usando la herramienta sxstrace, inicie Slicer y guarde el archivo de registro (consulte las instrucciones [aquí](https://technet.microsoft.com/en-ca/library/hh875651.aspx))

      +                 En Linux:

        - Algunas versiones de Linux requieren compilar su propio kerberos y openssl, como se [describe y se hace seguimiento en este problema](https://github.com/Slicer/Slicer/issues/5663).
