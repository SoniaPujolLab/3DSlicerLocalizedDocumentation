# Primeros pasos

Le damos la bienvenida a la comunidad de 3D Slicer. Esta página contiene la información que necesita para comenzar a usar 3D Slicer, incluido cómo instalarlo, cómo usar las funciones básicas y dónde encontrar más información.

## Requisitos del sistema

3D Slicer funciona en cualquier computadora Windows, Mac o Linux lanzada en los últimos 5 años. Las computadoras más antiguas pueden funcionar (dependiendo principalmente de las capacidades gráficas).

Slicer también puede ejecutarse en máquinas virtuales y contenedores docker. Por ejemplo, [3D Slicer + cuaderno Jupyter en un navegador web](https://mybinder.org/v2/gh/Slicer/SlicerNotebooks/master?filepath=SlicerWeb.ipynb) está disponible de forma gratuita a través del servicio Binder (no se necesita instalación; la aplicación puede ejecutarse en cualquier navegador web).

### Versiones de sistema operativo

- Windows: Windows 11 con todas las actualizaciones recomendadas instaladas. Microsoft ya no brinda soporte a Windows 10 (ni a versiones anteriores) y Slicer no se prueba en estas versiones heredadas del sistema operativo, aunque aún podría funcionar.

- macOS: macOS Sonoma (14) o posterior (sistemas basados tanto en Intel como en ARM). Se recomienda la última versión pública.

- Linux: Ubuntu 22.04 o posterior  
Debian 11 o posterior  
Fedora 35 o posterior  
AlmaLinux 8 o posterior. Se recomienda la última versión LTS (soporte a largo plazo).

### Configuración de hardware recomendada

- Memoria: más de 4 GB (se recomiendan 8 o más). Como regla general, tenga 10 veces más memoria que la cantidad de datos que cargue.

- Pantalla: una resolución mínima de 1366 por 768 (se recomienda 1920 por 1080 o superior).

- Gráficos: se recomienda hardware gráfico dedicado (GPU discreta) con memoria propia para una renderización de volumen rápida.
GPU: los gráficos deben admitir como mínimo OpenGL 3.2. Una tarjeta gráfica integrada es suficiente para la visualización básica. Se recomienda una tarjeta gráfica discreta (como una GPU NVidia) para la renderización de volumen 3D interactiva y la renderización rápida de escenas complejas. La memoria de textura de la GPU (VRAM) debe ser mayor que su conjunto de datos más grande (por ejemplo, si trabaja con datos de 2 GB, obtenga una VRAM > 4 GB) y verifique que sus imágenes encajen dentro de las dimensiones máximas de textura del hardware de su GPU. Salvo la renderización, la mayoría de los cálculos se realizan en la CPU, por lo que tener una GPU más rápida generalmente no afectará la velocidad global de la aplicación.

- Algunos cálculos en 3D Slicer son multihilo y se beneficiarán de configuraciones con varios núcleos y varias CPU.

- Dispositivo de interfaz: se recomienda un mouse de tres botones con rueda de desplazamiento. Se admiten lápiz, pantalla multitáctil, panel táctil y tableta gráfica. Se admiten todos los visores de realidad virtual compatibles con OpenVR para la visualización en realidad virtual.

- Conexión a Internet para acceder a extensiones, paquetes de Python, documentación en línea, conjuntos de datos de muestra y tutoriales.

## Instalación de 3D Slicer

Para descargar Slicer, haga clic [aquí](https://download.slicer.org/).

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_download.png)

**Notas:**

- La "Versión preliminar" de 3D Slicer (denominada "Slicer Preview Release") se actualiza a diario (el proceso comienza a las 11:00 p. m., hora del este, y tarda algunas horas en completarse) y representa el desarrollo más reciente, incluidas nuevas funciones y correcciones. No se proporcionan actualizaciones *continuas* de extensiones para las versiones preliminares: las extensiones disponibles para una versión preliminar corresponden a la última versión que estaba disponible en el momento en que se creó esa versión. Para obtener extensiones actualizadas, debe instalarse una nueva versión preliminar.

- La "Versión estable" de 3D Slicer (denominada "Slicer Stable Release") suele actualizarse algunas veces al año y se prueba de forma más rigurosa. Se proporcionan actualizaciones continuas de extensiones para la *última* Versión estable de Slicer, pero no para versiones anteriores. Por ejemplo, si la última Versión estable de Slicer es Slicer-5.2.2 y el usuario tiene instalado Slicer-5.2.1, entonces el usuario ya no recibirá actualizaciones de extensiones. Para comprobar si tiene instaladas las últimas versiones de la aplicación y las extensiones, puede ir al módulo `Welcome` (Bienvenida) y, en la sección `Updates` (Actualizaciones), hacer clic en el botón `Check now` (Comprobar ahora).

- Por lo general, Slicer es sencillo de instalar en todas las plataformas. Es posible instalar varias versiones de la aplicación en la misma cuenta de usuario sin que interfieran entre sí. Si tiene problemas misteriosos con su instalación, puede intentar eliminar los [archivos de configuración de la aplicación](https://slicer.readthedocs.io/en/latest/user_guide/settings.html#settings-file-location).

- Solo hay instaladores de Slicer de 64 bits disponibles para descargar. Los desarrolladores pueden intentar compilar versiones de 32 bits por su cuenta si necesitan ejecutar Slicer en un sistema operativo de 32 bits. Dicho esto, esto debe considerarse con cuidado, ya que muchas tareas de investigación clínica, como el procesamiento de grandes conjuntos de datos volumétricos de TC o RM, requieren más memoria de la que puede manejar un programa de 32 bits.

Una vez descargado, siga las instrucciones a continuación para completar la instalación:

### Windows

- Ejecute el instalador.

  * Limitación actual: la ruta de instalación solo debe contener caracteres en inglés ([imprimibles ASCII](https://en.wikipedia.org/wiki/ASCII#Printable_characters)), porque de lo contrario algunos paquetes de Python podrían no cargarse correctamente (consulte este [problema](https://github.com/Slicer/Slicer/issues/5383) para más detalles).

- Ejecute Slicer desde el menú de inicio de Windows.

- Use "Aplicaciones y características" en la configuración de Windows para eliminar la aplicación.

### Mac

- Abra el paquete de instalación (archivo .dmg).

- Arrastre la aplicación Slicer (Slicer.app) a su carpeta de Aplicaciones (u otra ubicación de su elección).

  * Este paso es necesario porque el contenido de un archivo .dmg se abre como un volumen de solo lectura, y no es posible instalar extensiones ni paquetes de Python en un volumen de solo lectura.

- Elimine la carpeta Slicer.app para desinstalar.

Nota para instalar una Versión preliminar: actualmente, los paquetes de las versiones preliminares no están firmados. Por lo tanto, cuando la aplicación se inicia por primera vez, se muestra el siguiente mensaje: "Slicer… no se puede abrir porque proviene de un desarrollador no identificado". Para resolver este error, localice la aplicación en el Finder, haga clic derecho (clic con dos dedos) y haga clic en `Open` (Abrir). Cuando aparezca `This app can't be opened` (No se puede abrir esta aplicación), pulse cancelar. Vuelva a hacer clic derecho y elija `Open` (Abrir) (sí, debe repetir lo mismo que hizo antes; el resultado será diferente al de la primera vez). Haga clic en el botón `Open` (Abrir) o `Open anyway` (Abrir de todos modos) para iniciar la aplicación. Consulte más explicaciones y técnicas alternativas [aquí](https://support.apple.com/en-my/guide/mac-help/mh40616/mac).

#### Instalación con Homebrew

Slicer puede instalarse con un solo comando de terminal usando el gestor de paquetes [Homebrew](https://brew.sh/):

```
brew install --cask slicer  # para instalar
brew upgrade slicer         # para actualizar
brew uninstall slicer       # para desinstalar

```

Este procedimiento evita el típico proceso de buscar en Google, descargar, montar y arrastrar para instalar aplicaciones en macOS.

Las versiones preliminares pueden instalarse usando [`homebrew-cask-versions`](https://github.com/Homebrew/homebrew-cask-versions):

```
brew tap homebrew/cask-versions     # debe ejecutarse una vez
brew install --cask slicer-preview  # para instalar
brew upgrade slicer-preview         # para actualizar
brew uninstall slicer-preview       # para desinstalar

```

### Linux

- Abra el archivo comprimido tar.gz y copie el directorio a la ubicación de su elección.

- Puede ser necesario instalar paquetes adicionales según la distribución y versión de Linux, como se describe en las subsecciones a continuación.

- Ejecute el archivo ejecutable `Slicer`.

- Elimine el directorio para desinstalar.

**Notas:**

- Se espera que Slicer funcione en la gran mayoría de las distribuciones de Linux de escritorio y servidor. Se requiere que el sistema proporcione al menos GLIBC 2.17 y GLIBCCC 3.4.19. Para más detalles, lea [aquí](https://www.python.org/dev/peps/pep-0599/#the-manylinux2014-policy).

- Obtener argumentos de línea de comandos y salidas de procesos que contienen caracteres no ASCII requiere que el sistema use una configuración regional UTF-8. Si el sistema usa una configuración regional diferente, puede usarse el comando `export LANG="C.UTF-8"` antes de iniciar la aplicación para cambiar a una configuración regional aceptable.

#### Ubuntu 24.04 (Noble Numbat)

```
sudo apt-get install libglu1-mesa libpulse-mainloop-glib0 libnss3 libasound2t64 qt5dxcb-plugin

```

#### Ubuntu 22.04 (Jammy Jellyfish), Debian 12 (bookworm), Debian 11 (bullseye)

```
sudo apt-get install libglu1-mesa libpulse-mainloop-glib0 libnss3 libasound2 qt5dxcb-plugin libsm6

```

Advertencia

Los usuarios de Debian 10.12 pueden encontrar un error al iniciar Slicer:

```
Warning: Ignoring XDG_SESSION_TYPE=wayland on Gnome. Use QT_QPA_PLATFORM=wayland to run on Wayland anyway.
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

Available platform plugins are: xcb.

```

[La solución](https://forum.qt.io/topic/93247/qt-qpa-plugin-could-not-load-the-qt-platform-plugin-xcb-in-even-though-it-was-found/81) es crear un enlace simbólico a `libxcb-util.so` o a `libxcb-util.so.0.0.0`, según cuál biblioteca esté presente. Así, el comando debería ser:

```
sudo ln -s /usr/lib/x86_64-linux-gnu/libxcb-util.so /usr/lib/x86_64-linux-gnu/libxcb-util.so.1

```

o:

```
sudo ln -s /usr/lib/x86_64-linux-gnu/libxcb-util.so.0.0.0 /usr/lib/x86_64-linux-gnu/libxcb-util.so.1

```

#### ArchLinux

Hay paquetes contribuidos por usuarios en [AUR](https://aur.archlinux.org/)

- [3dslicer-bin](https://aur.archlinux.org/packages/3dslicer-bin): este paquete reempaqueta el binario oficial para mayor comodidad. Tenga en cuenta que el Slicer oficial se compila con `Slicer_STORE_SETTINGS_IN_APPLICATION_HOME_DIR=ON`, se instala en `/opt`, donde un usuario sin privilegios de root no tiene permiso de escritura, por lo que el usuario no podrá instalar extensiones ni actualizar la configuración de la aplicación.

- [3dslicer](https://aur.archlinux.org/packages/3dslicer): puede compilar el paquete desde el código fuente usando este archivo `PKGBUILD`, o simplemente instalarlo desde un repositorio no oficial: [repositorio archlinuxcn](https://wiki.archlinux.org/title/Unofficial_user_repositories#archlinuxcn).

- [3dslicer-git](https://aur.archlinux.org/packages/3dslicer-git): igual que [3dslicer](https://aur.archlinux.org/packages/3dslicer) pero usando el código fuente más reciente.

#### Fedora 40, 39, 38, 37, 36, 35

Instale las dependencias:

```
sudo dnf install mesa-libGLU mesa-libGL libnsl libXrender pulseaudio-libs-glib2 nss libXcomposite libXdamage libXrandr ftgl libXcursor libXi libXtst alsa-lib qt5-qtx11extras

```

Advertencia

La biblioteca libcrypto.so.1.1 incluida en la instalación de Slicer es incompatible con las bibliotecas del sistema utilizadas por Fedora 35. La solución, hasta que se actualice, es mover o eliminar los archivos libcrypto incluidos:

```
$SLICER_ROOT/lib/Slicer-5.xx/libcrypto.*

```

Si al hacer doble clic en la aplicación no se inicia, pruebe los siguientes pasos en orden:

1. Verifique los permisos de ejecución de la aplicación

  - Haga clic derecho en la aplicación → *Propiedades* → asegúrese de que **"Es ejecutable como un programa"** esté marcado.

  - O verifíquelo desde una terminal:

  
  

```
ls -la

```
        Debería ver algo como `-rwxr-xr-x` al principio de la línea correspondiente al ejecutable.

            Nota

        Algunos gestores de archivos comprimidos (por ejemplo, ciertas herramientas `unrar`/`unzip`) pueden requerir ejecutar la extracción con `sudo` para restaurar los permisos de archivo correctos.

        Si faltan los permisos de ejecución, agréguelos con:

  
  

```
chmod +x Slicer

```

2. Inicie desde la terminal

  
  

```
./Slicer

```

3. Si obtiene el error

  
  

```
error: Failed to obtain launcher executable name !

```
    intente mover el ejecutable a su carpeta *Software Home* y vuelva a hacer doble clic en la aplicación. Debería iniciarse correctamente desde allí.

## Uso de Slicer

3D Slicer ofrece muchas funciones y brinda a los usuarios gran flexibilidad sobre cómo usarlas. Como resultado, los nuevos usuarios pueden sentirse abrumados por la cantidad de opciones y tener dificultades para descubrir cómo realizar incluso operaciones simples. Esto es normal, y muchos usuarios han superado con éxito esta etapa difícil invirtiendo algo de tiempo en aprender a usar este software.

¿Cómo aprender Slicer?

### Inicio rápido

Puede intentar descubrir cómo funciona la aplicación cargando conjuntos de datos y explorando lo que puede hacer.

#### Cargar datos

Abra 3D Slicer y, usando el panel de Bienvenida, cargue sus propios datos o descargue datos de muestra para explorar. Los datos de muestra suelen ser útiles para probar las funciones de 3D Slicer si no tiene datos propios.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_load_data.png)

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_sample_data.png)

#### Ver datos

La pestaña Jerarquía de sujetos (Subject hierarchy) del módulo Data muestra todos los conjuntos de datos de la escena. Haga clic en el icono del "ojo" para mostrar u ocultar un elemento en todas las vistas.

Puede personalizar las vistas (mostrar el marcador de orientación, la regla, cambiar la orientación, la transparencia) haciendo clic en la chincheta en la esquina superior izquierda del visor. En los visores de cortes, la barra horizontal puede usarse para desplazarse por los cortes o seleccionar un corte.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_view_controllers.png)

#### Procesar datos

3D Slicer se basa en una arquitectura modular. Elija un módulo para procesar o analizar sus datos. Los módulos más importantes son los siguientes (la lista completa está disponible en la sección [Módulos](https://slicer.readthedocs.io/en/latest/user_guide/modules/index.html)):

- *Welcome* (Bienvenida): el módulo predeterminado cuando se inicia 3D Slicer. El panel presenta opciones para cargar datos y personalizar 3D Slicer. Debajo de esas opciones hay menús desplegables que contienen información esencial para usar 3D Slicer.

- [Data](https://slicer.readthedocs.io/en/latest/user_guide/modules/data.html): actúa como un centro de organización de datos. Enumera todos los datos actualmente en la escena y permite operaciones básicas como buscar, renombrar, eliminar y mover.

- [DICOM](https://slicer.readthedocs.io/en/latest/user_guide/modules/dicom.html): importa y exporta objetos DICOM, como imágenes, segmentaciones, conjuntos de estructuras, objetos de radioterapia, etc.

- [Volumes](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumes.html): se usa para cambiar la apariencia de varios tipos de volúmenes.

- [Volume Rendering](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumerendering.html): proporciona visualización interactiva de datos de imagen 3D.

- [Segmentations](https://slicer.readthedocs.io/en/latest/user_guide/modules/segmentations.html): edita las propiedades de visualización e importa/exporta segmentaciones.

- [Segment Editor](https://slicer.readthedocs.io/en/latest/user_guide/modules/segmenteditor.html): segmenta volúmenes 3D usando diversas herramientas manuales, semiautomáticas y automáticas.

- [Markups](https://slicer.readthedocs.io/en/latest/user_guide/modules/markups.html): permite crear y editar marcas asociadas a una escena.

- [Models](https://slicer.readthedocs.io/en/latest/user_guide/modules/models.html): carga y ajusta los parámetros de visualización de los modelos. Permite al usuario cambiar la apariencia de los modelos de superficie 3D y organizarlos.

- [Transforms](https://slicer.readthedocs.io/en/latest/user_guide/modules/transforms.html): este módulo se usa para crear y editar matrices de transformación. Puede establecer estas relaciones moviendo nodos de la lista Transformable a la lista Transformed, o arrastrando los nodos bajo los nodos de Transformación en el módulo Data.

#### Guardar datos

Todos los datos de la escena pueden guardarse a la vez usando el menú `File` (Archivo) -> `Save data` (Guardar datos), o se pueden exportar conjuntos de datos seleccionados desde el módulo `Data` haciendo clic derecho y seleccionando `Export to file...` (Exportar a archivo...) o `Export to DICOM...` (Exportar a DICOM...). Los detalles se describen en la [sección de carga y guardado de datos](https://slicer.readthedocs.io/en/latest/user_guide/data_loading_and_saving.html).

#### Extensiones

3D Slicer admite complementos llamados extensiones. Una extensión puede entenderse como un paquete de distribución que agrupa uno o más módulos de Slicer. Después de instalar una extensión, los módulos asociados se presentarán al usuario como si fueran integrados. Las extensiones pueden descargarse desde el administrador de extensiones para instalar de forma selectiva las funciones que resulten útiles para el usuario final.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_module_list.png)

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_extensions_manager.png)

Para más detalles sobre cómo descargar extensiones, consulte la [documentación del Administrador de extensiones](https://slicer.readthedocs.io/en/latest/user_guide/extensions.html#extensions-manager).
Haga clic [aquí](https://www.slicer.org/wiki/Documentation/Nightly/ModuleExtensionListing/Extensions_by_category) para ver una lista completa de extensiones. Los enlaces de la página brindan documentación de cada extensión.

Slicer es ampliable. Si le interesa personalizar o agregar funcionalidad a Slicer, haga clic [aquí](https://training.slicer.org/#developer-tutorials).

### Tutoriales

Aprenda tanto conceptos básicos como flujos de trabajo altamente especializados a partir de los numerosos tutoriales paso a paso y en video disponibles.

Pruebe el [Tutorial de bienvenida](https://training.slicer.org/#stc-gen-101-welcome-tutorial) y el [Tutorial de carga de datos y visualización 3D](https://training.slicer.org/#stc-vis-102-data-loading-and-3d-visualization) para aprender lo básico.

Para más tutoriales, visite la [página de tutoriales](https://training.slicer.org/).

### Manual del usuario

Explore la sección [Interfaz de usuario](https://slicer.readthedocs.io/en/latest/user_guide/user_interface.html) para encontrar una descripción general rápida de la interfaz de usuario de la aplicación, o la sección [Módulos](https://slicer.readthedocs.io/en/latest/user_guide/modules/index.html) para obtener una descripción detallada de cada módulo.

### Pedir ayuda

3D Slicer existe desde hace muchos años y ya se han formulado y respondido muchas preguntas sobre él. Si tiene alguna pregunta, puede comenzar con una búsqueda en la web; por ejemplo, busque en Google `slicer load jpg` para averiguar cómo importar una pila de imágenes jpg.

La aplicación tiene una comunidad de usuarios grande, muy amable y servicial. Tenemos personas que con gusto le ayudarán con preguntas sencillas, como cómo realizar una tarea específica en Slicer, y contamos con un gran número de expertos en ingeniería y medicina que pueden aconsejarle sobre cómo resolver problemas complejos.

**Si tiene alguna pregunta, vaya al [foro de Slicer](https://discourse.slicer.org) y pregúntenos!**

## Glosario

Los términos usados en los diversos campos de la computación de imágenes médicas y biomédicas y de las imágenes clínicas no siempre son coherentes. Esta sección define términos de uso común en 3D Slicer, especialmente aquellos que pueden tener un significado distinto en otros contextos.

- **Bounds (límites)**: describe el cuadro delimitador de un objeto espacial a lo largo de 3 ejes. En VTK se define mediante 6 valores de punto flotante: `X_min`, `X_max`, `Y_min`, `Y_max`, `Z_min`, `Z_max`.

- **Brillo/contraste**: especifica el mapeo lineal de los valores de vóxel al brillo de un píxel mostrado. El brillo es el desplazamiento lineal y el contraste es el multiplicador. En imágenes médicas, este mapeo lineal se especifica más comúnmente mediante valores de ventana/nivel (window/level).

- **Cell (celda)**: las celdas de datos son elementos topológicos simples de las mallas, como líneas, polígonos, tetraedros, etc.

- **Leyenda de color** (o barra de color, barra escalar): un widget superpuesto en los cortes o vistas 3D que muestra una leyenda de color e indica el significado de los colores.

- **Sistema de coordenadas** (o marco de coordenadas, marco de referencia, espacio): se especifica por la posición del origen, las direcciones de los ejes y la unidad de distancia. Todos los sistemas de coordenadas en 3D Slicer son dextrógiros (de mano derecha).

- **Extension (extensión)** (o extensión de Slicer): una colección de módulos que no viene incluida con la aplicación principal, pero que puede descargarse e instalarse usando el Administrador de extensiones.

- [**Administrador de extensiones**](https://slicer.readthedocs.io/en/latest/user_guide/extensions.html#extensions-manager): un componente de software de Slicer que permite explorar, instalar y desinstalar extensiones del [Catálogo de extensiones (también conocido como la tienda de aplicaciones de Slicer)](https://extensions.slicer.org) directamente desde la aplicación.

- [**Índice de extensiones**](https://github.com/Slicer/ExtensionsIndex): un repositorio que contiene la descripción de cada extensión a partir de la cual se construye el Catálogo de extensiones.

- **Extent (extensión espacial)**: rango de coordenadas enteras a lo largo de 3 ejes. En VTK se define mediante 6 valores, para los ejes IJK: `I_min`, `I_max`, `J_min`, `J_max`, `K_min`, `K_max`. Tanto los valores mínimos como los máximos son inclusivos, por lo que el tamaño de un arreglo es `(I_max - I_min + 1)` x `(J_max - J_min + 1)` x `(K_max - K_min + 1)`.

- **Fiducial (marcador fiducial)**: representa un punto en el espacio 3D. El término proviene de la cirugía guiada por imagen, donde se usan "marcadores fiduciales" para marcar posiciones de puntos.

- **Frame (cuadro)**: un punto temporal en una secuencia de tiempo. Para evitar ambigüedad, este término no se usa para referirse a un corte de un volumen.

- **Geometría**: especifica la ubicación y la forma de un objeto en el espacio 3D. Consulte el término "Volumen" para la definición de la geometría de la imagen.

- **Intensidad de imagen**: normalmente se refiere al valor de un vóxel. El brillo y el color del píxel mostrado se calculan a partir de este valor según la ventana/nivel elegidos y la tabla de búsqueda de color.

- **IJK**: ejes del sistema de coordenadas de vóxeles. Los valores de coordenadas enteros corresponden a las posiciones de los centros de los vóxeles. Los valores IJK suelen usarse como valores de coordenadas para designar un elemento dentro de un arreglo 3D. Por convención de VTK, I indexa la columna, J indexa la fila y K indexa el corte. Tenga en cuenta que numpy usa la convención de ordenamiento opuesta, donde `a[K][J][I]`. A veces esta disposición de memoria se describe como que I es el índice de variación más rápida y K el de variación más lenta.

- **ITK**: [Insight Toolkit](https://itk.org/). Biblioteca de software que Slicer usa para la mayoría de las operaciones de procesamiento de imágenes.

- **Labelmap (mapa de etiquetas)** (o volumen de mapa de etiquetas, nodo de volumen de mapa de etiquetas): nodo de volumen que tiene valores de vóxel discretos (enteros). Normalmente, cada valor corresponde a una estructura o región específica. Esto permite una representación compacta de regiones no superpuestas en un único arreglo 3D. La mayoría del software usa un único mapa de etiquetas para almacenar una segmentación de imagen, pero Slicer usa un nodo de segmentación dedicado, que puede contener múltiples representaciones (varios mapas de etiquetas para permitir almacenar segmentos superpuestos; representación de superficie cerrada para una visualización 3D rápida, etc.).

- **LPS**: sistema de coordenadas anatómicas izquierda-posterior-superior (left-posterior-superior). Es el sistema de coordenadas más usado en la computación de imágenes médicas. Slicer almacena todos los datos en disco en el sistema de coordenadas LPS (y los convierte a/desde RAS al escribir o leer del disco).

- **Markups (marcas)**: objetos geométricos simples y mediciones que el usuario puede colocar en los visores. El [módulo Markups](https://slicer.readthedocs.io/en/latest/user_guide/modules/markups.html) puede usarse para crear dichos objetos. Hay varios tipos, como lista de puntos, línea, curva, plano y ROI.

- **Volumen de origen (source volume)**: los valores de vóxel de este volumen se usan durante la segmentación por aquellos efectos que dependen de la intensidad de un volumen subyacente.

- **MRML**: [Medical Reality Markup Language](https://en.wikipedia.org/wiki/Medical_Reality_Markup_Language): biblioteca de software para el almacenamiento, la visualización y el procesamiento de objetos de información que pueden usarse en aplicaciones médicas. La biblioteca está diseñada para ser reutilizable en diversas aplicaciones de software, pero 3D Slicer es la única aplicación importante que se sabe que la usa.

- **Model (modelo)** (o nodo de modelo): nodo MRML que almacena una malla de superficie (compuesta por celdas 2D como triángulos, polígonos, etc.) o una malla volumétrica (compuesta por celdas 3D como tetraedros, cuñas, etc.).

- **Module (módulo)** (o módulo de Slicer): un módulo de Slicer es un componente de software que consta de una interfaz gráfica de usuario (que se muestra en el panel del módulo cuando este se selecciona), una lógica (que implementa algoritmos que operan sobre nodos MRML) y que puede proporcionar nuevos tipos de nodos MRML, gestores visualizables (responsables de mostrar dichos nodos en las vistas), complementos de entrada/salida (responsables de cargar/guardar nodos MRML en archivos) y otros complementos diversos. Los módulos suelen ser independientes y se comunican entre sí únicamente modificando nodos MRML, pero a veces un módulo usa funciones proporcionadas por otros módulos llamando a métodos de su lógica.

- **Node (nodo)** (o nodo MRML): un objeto de datos en la escena. Un nodo puede representar datos (como una imagen o una malla), describir cómo se muestran (color, opacidad, etc.), almacenarse en disco, las transformaciones espaciales aplicadas sobre ellos, etc. Existe una jerarquía de clases en C++ que define los comportamientos comunes de los nodos, como la propiedad de poder almacenarse en disco o de poder transformarse geométricamente. La estructura de esta jerarquía de clases puede inspeccionarse en el código o en la [documentación de la API](https://apidocs.slicer.org/main/classvtkMRMLStorableNode.html).

- **Marcador de orientación**: marcador en forma de flecha, caja o figura humana para mostrar las direcciones de los ejes en los cortes y las vistas 3D.

- **RAS**: sistema de coordenadas anatómicas derecha-anterior-superior (right-anterior-superior). Sistema de coordenadas usado internamente en Slicer. Puede convertirse a/desde el sistema de coordenadas LPS invirtiendo la dirección de los dos primeros ejes.

- **Reference (referencia)**: no tiene un significado específico, pero normalmente se refiere a una entrada secundaria (objeto de datos, marco de coordenadas, geometría, etc.) para una operación.

- **Región de interés (ROI)**: especifica una región con forma de caja en 3D. Puede usarse para recortar volúmenes, recortar modelos, etc.

- **Registration (registro)**: el proceso de alinear objetos en el espacio. El resultado del registro es una transformación, que transforma el objeto "móvil" para que coincida con el objeto "fijo".

- **Resolución**: tamaño de vóxel de un volumen, normalmente especificado en mm/píxel. Rara vez se usa en la interfaz de usuario porque su significado es algo engañoso: un valor de resolución alto significa un espaciado grande, lo que significa una resolución de imagen baja (gruesa).

- **Ruler (regla)**: puede referirse a: 1. Regla de la vista: la línea que se muestra superpuesta en los visores para servir como referencia de tamaño. 2. Línea de markups: herramienta de medición de distancia.

- **Componente escalar**: un elemento de un vector. El número de componentes escalares es la longitud del vector.

- **Valor escalar**: un número simple. Normalmente de punto flotante.

- **Scene (escena)** (o escena MRML): es la estructura de datos que contiene todos los datos actualmente cargados en la aplicación e información adicional sobre cómo deben mostrarse o usarse. El término proviene de los [gráficos por computadora](https://en.wikipedia.org/wiki/Rendering_(computer_graphics)).

- **Segment (segmento)**: corresponde a una sola estructura en una segmentación. Vea más información en la sección [Segmentación de imágenes](https://slicer.readthedocs.io/en/latest/user_guide/image_segmentation.html).

- **Segmentation (segmentación)** (también conocida como contorneado, anotación; región de interés, conjunto de estructuras, máscara): proceso de delinear estructuras 3D en imágenes. La segmentación también puede referirse al nodo MRML que es el resultado del proceso de segmentación. Un nodo de segmentación normalmente contiene múltiples segmentos (cada segmento corresponde a una estructura 3D). Los nodos de segmentación no son nodos de mapa de etiquetas ni nodos de modelo, pero pueden almacenar múltiples representaciones (mapa de etiquetas binario, superficie cerrada, etc.). Vea más información en la sección [Segmentación de imágenes](https://slicer.readthedocs.io/en/latest/user_guide/image_segmentation.html).

- **Slice (corte)**: intersección de un objeto 3D con un plano.

- **Anotaciones de la vista de corte**: texto en la esquina de los cortes que muestra el nombre y las etiquetas DICOM seleccionadas de los volúmenes mostrados.

- **Spacing (espaciado)**: tamaño de vóxel de un volumen, normalmente especificado en mm/píxel.

- **Transform (transformación)**: puede transformar cualquier objeto 3D de un sistema de coordenadas a otro. El tipo más común es la transformación rígida, que puede cambiar la posición y la orientación de un objeto. Las transformaciones lineales pueden escalar, reflejar y cizallar objetos. Las transformaciones no lineales pueden deformar arbitrariamente el espacio 3D. Para mostrar un volumen en el sistema de coordenadas del mundo, el volumen debe remuestrearse, por lo que se necesita una transformación *desde* el sistema de coordenadas del mundo hacia el volumen (se denomina transformación de remuestreo). Para transformar todos los demás tipos de nodos al sistema de coordenadas del mundo, todos los puntos deben transformarse *hacia* el sistema de coordenadas del mundo (transformación de modelado). Dado que un nodo de transformación debe poder aplicarse a cualquier nodo, los nodos de transformación pueden proporcionar tanto la transformación *desde* como *hacia* el nodo padre (almacenan una y calculan la otra sobre la marcha).

- **Volume (volumen)** (o nodo de volumen, volumen escalar, imagen): nodo MRML que almacena un arreglo 3D de vóxeles. Los índices del arreglo suelen denominarse IJK. El rango de coordenadas IJK se denomina extents. La geometría del volumen se especifica mediante su origen (posición del punto IJK=(0,0,0)), su espaciado (tamaño de un vóxel a lo largo de los ejes I, J, K), las direcciones de los ejes (dirección de los ejes I, J, K en el sistema de coordenadas de referencia) con respecto a un marco de referencia. Las imágenes 2D son volúmenes 3D de un solo corte, con su posición y orientación especificadas en el espacio 3D.

- [**Voxel (vóxel)**](https://en.wikipedia.org/wiki/Voxel): un elemento de un volumen 3D. Tiene forma de prisma rectangular. Las coordenadas de un vóxel corresponden a la posición de su punto central. El valor de un vóxel puede ser un valor escalar simple o un vector.

- **VR**: abreviatura que puede referirse a volume rendering (renderización de volumen) o a virtual reality (realidad virtual). Para evitar ambigüedad, generalmente se recomienda usar el término completo (o definir explícitamente el significado de la abreviatura en el contexto dado).

- **VTK**: [Visualization Toolkit](https://vtk.org/). Biblioteca de software que Slicer usa para la representación y la visualización de datos. Dado que la mayoría de las clases de Slicer derivan de clases de VTK y usan intensamente otras clases de VTK, Slicer adoptó muchas convenciones del estilo y la interfaz de programación de aplicaciones de VTK.

- **Window/level (ventana/nivel)** (o ancho de ventana/nivel de ventana): especifica el mapeo lineal de los valores de vóxel al brillo de un píxel mostrado. La ventana (window) es el tamaño del rango de intensidad que se mapea a todo el rango de intensidad visualizable. El nivel (level) es el valor de vóxel que se mapea al centro de todo el rango de intensidad visualizable.
