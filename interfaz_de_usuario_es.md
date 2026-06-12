# Interfaz de usuario

## Descripción general de la aplicación

Slicer almacena todos los datos cargados en un repositorio de datos, llamado la "escena" (o escena de Slicer o escena MRML). Cada conjunto de datos, como un volumen de imagen, un modelo de superficie o un conjunto de puntos, se representa en la escena como un "nodo".

Slicer ofrece una gran cantidad de "módulos", cada uno de los cuales implementa un conjunto específico de funciones para crear o manipular datos en la escena. Por lo general, los módulos no interactúan entre sí directamente: todos operan sobre los nodos de datos de la escena. El paquete de Slicer contiene más de 100 módulos integrados, y pueden instalarse módulos adicionales usando el Administrador de extensiones.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_main_window_rev02.png)

### Panel del módulo

Este panel (ubicado de forma predeterminada en el lado izquierdo de la ventana principal de la aplicación) muestra todas las opciones y funciones que el módulo actual ofrece al usuario. El módulo actual puede seleccionarse usando la barra de herramientas de **Selección de módulo**.

#### Sonda de datos (Data Probe)

La Sonda de datos se encuentra en la parte inferior del panel del módulo. Muestra información sobre el contenido de la vista en la posición del puntero del mouse:

- Información de la vista de corte (se muestra cuando el mouse está sobre una vista de corte):

  * Nombre de la vista de corte: `Red`, `Green`, `Yellow`, etc.

  * Posición anatómica: tres valores de coordenadas, con el prefijo `R`/`L` (derecha/izquierda), `A`/`P` (anterior/posterior), `S`/`I` (superior/inferior). El origen, la posición (0,0,0), fue elegido por el técnico de imagen cuando se creó la imagen. Por ejemplo, `(R 17.6, P 35.3, S 12.1)` para una imagen clínica significa que la posición actual está a 17.6 mm a la derecha del origen, 35.3 mm hacia posterior y 12.1 mm superior respecto del origen.

  * Orientación de la vista: `Axial`, `Sagittal`, `Coronal` para las orientaciones anatómicas estándar, y `Reformat` para cualquier otra orientación.

  * Espaciado de cortes: distancia entre los cortes en esta orientación. Para una imagen clínica, `Sp: 2.5` significa que los cortes están a 2.5 mm de distancia entre sí.

- Información de la capa de volumen: tres líneas, una por cada capa de volumen

  * Tipo de capa: `L` (etiqueta), `F` (primer plano), `B` (fondo).

  * Nombre del volumen, o `None` si no hay ningún volumen seleccionado para esa capa.

  * Coordenadas de vóxel (IJK) del volumen.

  * Valor del vóxel. Para los volúmenes de etiquetas, también se muestra el nombre de la etiqueta correspondiente al valor del vóxel.

- Información de segmentación: para cada segmentación visible en esa posición

  * Tipo de capa: `S` (segmentación)

  * Nombre de la segmentación.

  * Nombres de los segmentos. Se enumeran varios nombres de segmentos si se muestran varios segmentos en esa posición (los segmentos se superponen).

### Vistas

Slicer muestra los datos en diversas vistas. El usuario puede elegir entre varios diseños predefinidos, que pueden contener vistas de corte, 3D, de gráfico y de tabla.

La barra de herramientas de Diseño (Layout) ofrece un menú desplegable de diseños útiles para muchos tipos de estudios. Cuando Slicer se cierra normalmente, el diseño seleccionado se guarda y se restaura la próxima vez que se inicia la aplicación.

### Menú de la aplicación

- **File** (Archivo): funciones para cargar una escena previamente guardada o conjuntos de datos individuales de diversos tipos, y para descargar conjuntos de datos de muestra desde internet. Aquí también se ofrece una opción para guardar escenas y datos. **Add Data** (Agregar datos) permite cargar datos desde archivos. Se recomienda el módulo **DICOM** para importar datos de archivos DICOM y cargar los datos DICOM importados. **Save** (Guardar) abre la ventana "Save Data" (Guardar datos), que ofrece una variedad de opciones para guardar todos los datos o los conjuntos de datos seleccionados.

- **Edit** (Editar): contiene una opción para mostrar la Configuración de la aplicación (Application Settings), que permite a los usuarios personalizar la apariencia y el comportamiento de Slicer, como los módulos que se muestran en la barra de herramientas, el tamaño de fuente de la aplicación, la ubicación del directorio temporal y la ubicación de módulos adicionales de Slicer que se incluirán.

- **View** (Ver): funciones para mostrar/ocultar ventanas y widgets adicionales, como el **Administrador de extensiones** para instalar extensiones desde la tienda de aplicaciones de Slicer, el **Registro de errores** (Error Log) para comprobar si la aplicación encontró algún posible error, la **Consola de Python** para obtener una consola de Python con la que interactuar con los datos o módulos cargados, **mostrar/ocultar barras de herramientas** o **cambiar el diseño de la vista**.

- **Help** (Ayuda): contiene enlaces a documentación, guías y sitios de la comunidad. **Report a Bug** (Informar de un error) proporciona instrucciones para informar de errores y un acceso cómodo a los mensajes de registro. También hay enlaces para buscar **Publicaciones de Slicer** (Slicer Publications) y aprender **Cómo citar** (How to Cite) Slicer.

### Barra de herramientas

La barra de herramientas proporciona acceso rápido a las funciones de uso frecuente. Los paneles individuales de la barra de herramientas pueden mostrarse/ocultarse usando el menú: sección View / Toolbars.

La barra de herramientas de **Selección de módulo** se usa para seleccionar el "módulo" actualmente activo. La barra de herramientas ofrece opciones para buscar nombres de módulos (`Ctrl` + `f` o haciendo clic en el icono de la lupa) o para seleccionar desde un menú. El **botón desplegable del historial de módulos** muestra la lista de módulos usados recientemente. Los **botones de flecha** pueden usarse para retroceder o volver a un módulo usado anteriormente.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_module_toolbar.png)

La barra de herramientas de **Módulos favoritos** contiene una lista de los módulos más usados. La lista puede personalizarse usando el menú: Edit / Application settings / Modules / Favorite Modules. Arrastre y suelte módulos desde la lista de Módulos a la lista de Módulos favoritos para agregar un módulo.

### Barra de estado

Este panel puede mostrar el estado de la aplicación, como la operación actual en curso. Al hacer clic en los pequeños iconos **X** se muestra la ventana del Registro de errores.

## Revisar los datos cargados

Los datos disponibles en Slicer pueden revisarse en el módulo Data, que se encuentra en la barra de herramientas o en la lista de módulos ![](https://slicer.readthedocs.io/en/latest/_images/SubjectHierarchy.png). Puede encontrar más detalles sobre el módulo en la [wiki de Slicer](https://www.slicer.org/wiki/Documentation/Nightly/Modules/Data).

La pestaña predeterminada Jerarquía de sujetos (Subject hierarchy) del módulo Data puede mostrar los conjuntos de datos en una jerarquía de árbol, organizados como paciente/estudio/serie, como es típico en DICOM, o en cualquier otra estructura de carpetas:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/data_loading_and_saving_subject_hier.png)

La vista de Jerarquía de sujetos contiene numerosas funciones integradas para todos los tipos de datos. Se puede acceder a estas funciones haciendo clic derecho sobre el nodo en el árbol. La lista de acciones difiere según el tipo de dato, por lo que es útil explorar las opciones.

Los datos de imágenes médicas se presentan en diversas formas y representaciones, lo que puede confundir a quienes recién comienzan en el campo. El siguiente diagrama ofrece una breve descripción de los tipos de datos más típicos que se encuentran al usar Slicer, especialmente en un flujo de trabajo que involucra segmentación.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/data_loading_and_saving_formats.png)

### Seleccionar los datos mostrados

La pestaña Jerarquía de sujetos del módulo Data muestra todos los conjuntos de datos de la escena. Haga clic en el icono del "ojo" para mostrar u ocultar un elemento en todas las vistas. Arrastre y suelte un elemento en una vista para mostrarlo en esa vista.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/drag_to_view.gif)

Se pueden seleccionar varios elementos en el árbol de jerarquía de sujetos usando Ctrl-clic-izquierdo o Shift-clic-izquierdo y arrastrarlos todos a la vez a la vista seleccionada. Si se arrastran dos volúmenes a una vista al mismo tiempo, ambos se mostrarán mezclados entre sí.

Si una vista se muestra solo en vistas seleccionadas, puede hacer clic derecho sobre el elemento y seleccionar "Show in all views" (Mostrar en todas las vistas) para mostrarlo rápidamente en todas las vistas.

Si el enlace de vistas está habilitado para una vista de corte, al arrastrar un volumen a cualquiera de las vistas se mostrará el volumen en todas las vistas de ese grupo.

Las opciones de visualización pueden ajustarse haciendo clic derecho en el icono del ojo en la columna de visualización del árbol. Tenga en cuenta que estas opciones son diferentes de las que se ofrecen al hacer clic derecho en la columna "Node" (Nodo) o "Transform" (Transformación) del árbol.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_sh_display_menu.png)

Para los volúmenes, las opciones de visualización incluyen:

- Restablecer el campo de visión al mostrar (Reset field of view on show): si está habilitado, al mostrar un volumen se ajustan las vistas para mostrar el volumen en el centro, llenando el campo de visión.

- Restablecer la orientación de la vista al mostrar (Reset view orientation on show): si está habilitado, al mostrar un volumen se alinean las vistas de corte con los ejes del volumen.

## Interactuar con las vistas

### Referencia cruzada de vistas

Mantener presionada la tecla `Shift` mientras se mueve el mouse en cualquier vista de corte o 3D hará que la mira (Crosshair) se mueva a la posición seleccionada en todas las vistas. De forma predeterminada, cuando la mira se mueve en cualquier vista, todas las vistas de corte se desplazan a la misma posición RAS indicada por el mouse. Esta función es útil durante la inspección.

Para mostrar/ocultar la posición de la mira, haga clic en el icono de la mira ![](https://slicer.readthedocs.io/en/latest/_images/SlicesCrosshair.png).

Para personalizar el comportamiento y la apariencia de la mira, haga clic en el botón de "flecha hacia abajo" en el lado derecho del icono de la mira.

### Modos del mouse

Slicer tiene varios modos del mouse: **Transform** (Transformar; que permite operaciones interactivas de rotación, traslación y zoom), **Window/Level** (Ventana/Nivel; para ajustar el brillo/contraste de los volúmenes de imagen) y **Place** (Colocar; que permite colocar objetos de forma interactiva en las vistas de corte y 3D).

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_mousemode_toolbar.png)

Los iconos de la barra de herramientas que cambian entre estos modos del mouse se muestran arriba, de izquierda a derecha, respectivamente. Colocar lista de puntos (Place Point List) es la opción de colocación predeterminada, como se muestra arriba; también hay opciones para colocar otros nodos, como widgets de Regla (Ruler) y de Región de interés (Region of Interest), disponibles en el menú desplegable de Modo de colocación (Place Mode).

Nota

El modo Transform es el modo de interacción predeterminado. De forma predeterminada, el modo Place persiste durante una operación de "colocación" después de seleccionar el icono de Modo de colocación, y luego el modo vuelve a Transform. El modo Place puede hacerse persistente (útil para colocar varios puntos de control) marcando la casilla Persistent (Persistente) que se muestra en el extremo derecho de la barra de herramientas de Modo del mouse.

#### Ajustar la ventana/nivel de la imagen

Las imágenes médicas suelen contener miles de niveles de gris, pero las pantallas de computadora normales solo pueden mostrar 256 niveles de gris, y el ojo humano también tiene limitaciones en cuanto a la diferencia mínima de contraste que puede notar (consulte [Kimpe 2007](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3043920/) para información más específica). Por lo tanto, las imágenes médicas se muestran con brillo/contraste ajustable (ventana/nivel).

De forma predeterminada, 3D Slicer usa la configuración de ventana/nivel especificada en el archivo DICOM. Si no está disponible, la ventana/nivel se ajusta para contener todo el rango de intensidad de la imagen (excepto el 0.1 % superior/inferior, calculado mediante percentiles, para no permitir que una cola muy delgada de la distribución de intensidad reduzca demasiado el contraste de la imagen).

La ventana/nivel puede ajustarse manualmente en cualquier momento haciendo clic en el botón "Adjust window/level" (Ajustar ventana/nivel) de la barra de herramientas y luego haciendo clic izquierdo y arrastrando en cualquiera de los visores de corte. Se puede calcular la ventana/nivel óptima para un área elegida haciendo clic izquierdo y arrastrando mientras se mantiene presionada la tecla `Ctrl`.

[![](https://img.youtube.com/vi/u1B0F1KcVsk/0.jpg)](https://youtu.be/u1B0F1KcVsk "Video de demostración de cómo ajustar la ventana/nivel de la imagen")

Hay opciones adicionales de ventana/nivel, preajustes, histograma de intensidad y ajustes automáticos disponibles en la sección Display (Visualización) del módulo [Volumes](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumes.html). Los preajustes también están disponibles en el menú contextual de las vistas de corte. Puede restablecer la configuración de ventana/nivel calculada automáticamente usando el menú contextual o usando `Ctrl` + `doble clic izquierdo` en la vista de corte.

### Vista 3D

Muestra una vista 3D renderizada de la escena junto con referencias visuales para especificar la orientación y la escala.

Ejes de orientación predeterminados: A = anterior, P = posterior, R = derecha, L = izquierda, S = superior e I = inferior.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_3d_view_controls_2025_03_09.png)

Controles de la vista 3D: la barra azul que cruza cualquier vista 3D muestra un icono de chincheta a su izquierda. Cuando el mouse pasa sobre este icono, se muestra un panel para configurar la vista 3D. El panel se oculta cuando el mouse se aleja. Para mostrar este panel de forma permanente, simplemente haga clic en el icono de la chincheta.

- **Centrar la vista 3D** (cuadrado pequeño) centra el corte sobre el contenido actualmente visible de la vista 3D y todos los volúmenes cargados (incluso los volúmenes que no son visibles). El campo de visión (factor de zoom) no se ajusta, por lo que puede ser necesario acercar/alejar para ver todos los objetos. Para restablecer el centro y el campo de visión al mismo tiempo, haga clic en la vista 3D y presione la tecla `r`.

- **Maximizar la vista** / **Restaurar el diseño de la vista** maximiza temporalmente la vista seleccionada / restaura el diseño completo de las vistas.

- **Dirección del punto de vista** cambia la orientación de la vista entre direcciones estándar. Al hacer clic en el botón **L**eft (izquierda), **R**ight (derecha), **A**nterior, **P**osterior, **S**uperior, **I**nferior, el contenido 3D se verá desde esa dirección.

- El botón **Enlace de vista** (View link) sincroniza las propiedades entre las vistas 3D (posición y dirección del punto de vista, regla, marcador de orientación, etc.).

- Alternar el modo de renderizado **Ortográfico/perspectiva**. El modo ortográfico (proyección paralela) es útil para evaluar el tamaño, porque el tamaño del objeto mostrado no depende de la distancia al punto de vista. El modo perspectiva ofrece una mejor percepción de la profundidad, porque los objetos que están más cerca se ven más grandes.

- **Regla** (Ruler) controla la visualización de la regla. Solo está disponible en el modo de renderizado ortográfico.

- **Visualización estereoscópica** (Stereo viewing) habilita la visualización estereoscópica. Los modos rojo/azul y anáglifo solo requieren unas económicas gafas con cristales de color rojo/azul. Otros modos requieren hardware de pantalla 3D especial. Tenga en cuenta que la [extensión SlicerVirtualReality](https://www.slicervr.org/) ofrece una experiencia superior de visualización e interacción estereoscópica, con visualización 3D totalmente inmersiva con un solo clic de un botón, e interacción rica con los objetos de la escena usando controladores 3D.

- Más opciones (…)

  * **Usar depth peeling** debe estar habilitado para un renderizado correcto de las superficies semitransparentes (en modelos, marcas, etc.). Puede hacer que las actualizaciones del renderizado sean un poco más lentas y producir artefactos cuando se usa el renderizado de volumen en la vista.

  * **Mostrar/ocultar cuadros por segundo (FPS)** muestra la velocidad de renderizado en la esquina de la vista.

- **Marcador de orientación** controla la visualización de la figura humana, el cubo, etc. en la esquina inferior derecha.

- **Opciones de visibilidad** controla la visibilidad del color de fondo de la vista y de los componentes mostrados.

- **Spin** (Girar) hace que la vista gire continuamente.

- **Rock** (Balancear) hace que la vista se balancee continuamente de izquierda a derecha.

- **Acercar/alejar** (Zoom in/out) acerca/aleja ligeramente la vista. Botones cómodos para pantallas táctiles.

- El **Bloqueo de inclinación** (Tilt Lock) puede activarse/desactivarse usando el atajo de teclado `Ctrl` + `b`. En el modo de bloqueo de inclinación, la rotación de la vista 3D se restringe al eje de azimut (dirección izquierda-derecha) al deshabilitar la rotación alrededor del eje de elevación (dirección arriba-abajo).

#### Sombras ambientales

- Visibilidad de las sombras: si está habilitada, se muestran sombras ambientales para mejorar la percepción de la profundidad

  * Escala de tamaño (Size scale; predeterminado: 0): tamaño de los detalles que se enfatizarán con las sombras. Los valores más bajos enfatizan las irregularidades de la superficie (protuberancias y depresiones). Una escala de tamaño más alta hace que las regiones más grandes que están mucho más lejos se vean mucho más oscuras. El valor óptimo puede determinarse ajustando el valor a partir del valor más alto, de forma gradual, hasta que las regiones que están detrás de los objetos se vean más oscuras. Los valores muy altos (1.5 a 3.0) pueden hacer que toda la imagen se vea más oscura, por lo que es importante bajar de este rango, normalmente hasta alrededor de 0.5 a 1.5.

  * Escala de intensidad (Intensity scale; predeterminado: 1): intensidad del oscurecimiento por las sombras. Aumente el valor para hacer las sombras más oscuras.

  * Desplazamiento de intensidad (Intensity shift; predeterminado: 0): cantidad mínima de oclusión requerida para un oscurecimiento visible por las sombras. Normalmente solo es necesario aumentar este valor si se aumenta la escala de intensidad, lo que hace que toda la imagen se vea algo más oscura. En este caso, aumentar el desplazamiento de intensidad puede compensar el oscurecimiento general.

  * Umbral de opacidad del volumen (Volume opacity threshold; del 0 % al 100 %; predeterminado: 25 %): este valor solo afecta el renderizado de volumen. Los vóxeles que tengan una opacidad superior a este valor proyectarán sombras. Elegir un valor demasiado bajo produce artefactos oscuros en las regiones que tienen una opacidad muy baja. Elegir un valor demasiado alto produce artefactos cerca de las regiones opacas que tienen un valor de opacidad algo más bajo.

Ejemplos: ![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_ambient_shadows.png)

Nota

La configuración predeterminada de las sombras ambientales puede elegirse en el menú de la aplicación (Edit / Application Settings / Views / 3D viewer defaults).

### Vista de corte

Se proporcionan tres vistas de corte predeterminadas (con barras de colores Rojo, Amarillo y Verde) en las que pueden mostrarse cortes 2D Axiales, Sagitales, Coronales u Oblicuos de las imágenes de volumen. Las vistas de corte genéricas adicionales tienen una barra de color gris y un número de identificación en su esquina superior izquierda.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_slice_view_controls.png)

Controles de la vista de corte: la barra de color que cruza cualquier vista de corte muestra un icono de chincheta a su izquierda (**Mostrar controles de la vista**). Cuando el mouse pasa sobre este icono, se muestra un panel para configurar la vista de corte. El panel se oculta cuando el mouse se aleja. Para mostrar este panel de forma permanente, simplemente haga clic en el icono de la chincheta. Para más opciones, haga clic en el icono de doble flecha (**Mostrar todas las opciones**).

El módulo View Controllers (Controladores de vista) ofrece una forma alternativa de mostrar estos controladores en el Panel del módulo.

- **Restablecer el campo de visión** (cuadrado pequeño) centra el corte sobre el volumen de fondo actual.

- El botón del "ojo" **Mostrar en 3D** (Show in 3D) de la fila superior puede mostrar el corte actual en las vistas 3D. El menú desplegable del botón contiene opciones avanzadas para personalizar cómo se renderiza este corte: "…match volume" significa que las propiedades se toman del volumen completo, mientras que "…match 2D" significa que las propiedades se copian de la vista de corte actual (por ejemplo, copia la posición de zoom y desplazamiento). Normalmente, estas diferencias son sutiles y la configuración puede dejarse en sus valores predeterminados.

- **Orientación del corte** (Slice orientation) le permite elegir la orientación de esta vista de corte.

- **Reformat** permite la manipulación interactiva de la orientación del corte.

- El **control deslizante de desplazamiento del corte** (Slice offset slider) permite recorrer el volumen en cortes. El tamaño del paso se establece de forma predeterminada según el espaciado del volumen de fondo, pero puede modificarse haciendo clic en el botón "Spacing and field of view" (Espaciado y campo de visión). La etiqueta junto al valor de desplazamiento (por ejemplo, `S`, `L`, `A`, `IL`, `IRP`) refleja la dirección normal del corte. Si el control deslizante de desplazamiento se mueve hacia la derecha, el corte se mueve en esa dirección normal. Si la dirección normal del corte no está alineada con un eje, la etiqueta contiene una combinación de direcciones, con el orden de los ejes reflejando el predominio del eje. Por ejemplo, si la normal del plano apunta hacia anterior y ligeramente a la izquierda, la etiqueta es `AL`, mientras que si la normal del plano apunta principalmente a la izquierda y ligeramente hacia anterior, la etiqueta es `LA`.

- El **modo de fusión** (Blending mode) especifica cómo se mezclan las capas de primer plano y de fondo.

- **Espaciado y campo de visión** (Spacing and field of view): el espaciado define el incremento del control deslizante de desplazamiento del corte. El campo de visión establece el nivel de zoom del corte.

- **Rotar al plano del volumen** (Rotate to volume plane) cambia la orientación del corte para que coincida con la orientación de adquisición más cercana del volumen mostrado.

- **Marcador de orientación** controla la visualización de la figura humana, el cubo, etc. en la esquina inferior derecha.

- **Regla** (Ruler) controla la visualización de la regla en la vista de corte.

- El botón **Enlace de vista** (View link) sincroniza las propiedades de las vistas del mismo grupo de vistas, como la selección de volúmenes de primer plano/fondo/etiqueta, la opacidad de los volúmenes de primer plano/etiqueta y el factor de zoom.

  * Para las vistas paralelas (es decir, que están configuradas con la misma orientación, como `axial`), la posición del centro de la vista también se sincroniza.

  * Un clic prolongado en el botón expone la opción **hot-linked** (enlace en caliente), que controla cuándo se sincronizan las propiedades (de inmediato o cuando se suelta el botón del mouse).

  * Un grupo de vistas normalmente consta de 3 vistas ortogonales (por ejemplo, en la vista `Four-Up`, las vistas `R`, `G`, `Y` están en el mismo grupo). En los diseños que contienen varios tripletes de vistas de corte, cada triplete forma un grupo separado (por ejemplo, en el diseño `Three over three` hay dos grupos de vistas: un grupo es `R`, `G`, `Y` y el otro grupo es `R+`, `G+`, `Y+`).

- Los botones del "ojo" de **Visibilidad de capa** (Layer visibility) y los selectores numéricos de **Opacidad de capa** (Layer opacity) controlan la visibilidad de las segmentaciones y los volúmenes en la vista de corte.

- El control deslizante de **Opacidad del volumen de primer plano** (Foreground volume opacity) permite hacer una transición gradual entre los volúmenes de primer plano y de fondo.

- La **Interpolación** (Interpolation) permite mostrar los valores de los vóxeles sin interpolación. Se recomienda mantener la interpolación habilitada y deshabilitarla solo para pruebas y resolución de problemas.

- Los **selectores de nodos** (Node selectors) se usan para elegir qué volúmenes de fondo, primer plano y mapa de etiquetas y qué segmentaciones se muestran en esta vista de corte. Nota: pueden mostrarse varias segmentaciones en una vista de corte, pero los controles de la vista de corte solo permiten ajustar la visibilidad del nodo de segmentación actualmente seleccionado.

Eliminado en la versión 5.10:

- Se eliminó la función **Lightbox** para seleccionar una vista en mosaico (también conocida como hoja de contactos). En su lugar, puede usarse la opción *Lightbox image columns* (Columnas de imágenes de Lightbox) que ofrece el módulo [Screen Capture](https://slicer.readthedocs.io/en/latest/user_guide/modules/screencapture.html).

## Atajos de mouse y teclado

### Combinaciones de teclas alternativas para macOS

Al usar atajos en macOS, reemplace las siguientes teclas con su versión correspondiente de macOS.

| Tecla  | Tecla de macOS         |
| ------ | ---------------------- |
| `Ctrl` | `Command` / `⌘`        |
| `Alt`  | `Option` / `⌥` / `Alt` |

### Atajos genéricos

| Atajo                           | Operación                                                                  |
| ------------------------------- | -------------------------------------------------------------------------- |
| `Ctrl` + `f`                    | buscar un módulo por nombre (presione `Enter` para seleccionar)            |
| `Ctrl` + `o`                    | agregar datos desde un archivo                                             |
| `Ctrl` + `s`                    | guardar datos en archivos                                                  |
| `Ctrl` + `w`                    | cerrar la escena                                                           |
| `Ctrl` + `0`                    | mostrar el Registro de errores                                            |
| `Ctrl` + `1`                    | mostrar la Ayuda de la aplicación                                         |
| `Ctrl` + `2`                    | mostrar la Configuración de la aplicación                                 |
| `Ctrl` + `3` / `Ctrl` + `` ` `` | mostrar/ocultar la Consola de Python                                      |
| `Ctrl` + `4`                    | mostrar el Administrador de extensiones                                   |
| `Ctrl` + `5`                    | mostrar/ocultar el Panel del módulo                                       |
| `Ctrl` + `h`                    | abrir el módulo de inicio predeterminado (configurable en la Configuración de la aplicación) |

### Vistas de corte

Los siguientes atajos están disponibles cuando una vista de corte está activa. Para activar una vista, haga clic dentro de ella: si no desea cambiar nada en la vista, simplemente actívela y luego haga `clic derecho` sin mover el mouse. Tenga en cuenta que simplemente pasar el mouse por encima de una vista de corte no la activará.

| Atajo                                  | Operación                                                                                                                           |
| -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `clic derecho` + `arrastrar arriba/abajo` | acercar/alejar la imagen (`Alt` opcional, útil durante la colocación de puntos)                                                  |
| `Ctrl` + `rueda del mouse`             | acercar/alejar la imagen                                                                                                          |
| `clic central` + `arrastrar`           | desplazar (trasladar) la vista (`Alt` opcional, útil durante la colocación de puntos)                                            |
| `Shift` + `clic izquierdo` + `arrastrar` | desplazar (trasladar) la vista (`Alt` opcional, útil durante la colocación de puntos)                                          |
| `flecha izquierda` / `flecha derecha`  | ir al corte anterior/siguiente                                                                                                   |
| `b` / `f`                              | ir al corte anterior/siguiente                                                                                                   |
| `Shift` + `mover el mouse`             | mover la mira en todas las vistas                                                                                               |
| `Ctrl` + `Alt` + `clic izquierdo` + `arrastrar` | rotar la intersección de cortes de las otras vistas (las `Intersecciones de cortes` deben estar habilitadas en la barra de herramientas de `Selección de mira`) |
| `v`                                    | alternar la visibilidad del corte en la vista 3D                                                                               |
| `r`                                    | restablecer el zoom y el desplazamiento a los valores predeterminados                                                          |
| `g`                                    | alternar la segmentación o el volumen de mapa de etiquetas                                                                     |
| `t`                                    | alternar la visibilidad del volumen de primer plano                                                                            |
| `[` / `]`                              | usar el volumen anterior/siguiente como fondo                                                                                  |
| `{` / `}`                              | usar el volumen anterior/siguiente como primer plano                                                                           |
| `doble clic izquierdo`                 | maximizar la vista/restaurar el diseño de la vista                                                                             |

### Vistas 3D

Los siguientes atajos están disponibles cuando una vista 3D está activa. Para activar una vista, haga clic dentro de ella: si no desea cambiar nada en la vista, simplemente actívela y luego haga `clic derecho` sin mover el mouse. Tenga en cuenta que simplemente pasar el mouse por encima de una vista de corte no la activará.

| Atajo                                            | Operación                                                                  |
| ------------------------------------------------ | -------------------------------------------------------------------------- |
| `Shift` + `mover el mouse`                       | mover la mira en todas las vistas                                          |
| `clic izquierdo` + `arrastrar`                   | rotar la vista (`Alt` opcional, útil durante la colocación de puntos)      |
| `flecha izquierda` / `flecha derecha`            | rotar la vista                                                            |
| `flecha arriba` / `flecha abajo`                 | rotar la vista                                                            |
| `Fin` o `Teclado numérico 1`                     | rotar para ver desde anterior                                            |
| `Shift` + `Fin` o `Shift` + `Teclado numérico 1` | rotar para ver desde posterior                                          |
| `Av Pág` o `Teclado numérico 3`                  | rotar para ver desde el lado izquierdo                                   |
| `Shift` + `Av Pág` o `Shift` + `Teclado numérico 3` | rotar para ver desde el lado derecho                                 |
| `Inicio` o `Teclado numérico 7`                  | rotar para ver desde superior                                           |
| `Shift` + `Inicio` o `Shift` + `Teclado numérico 7` | rotar para ver desde inferior                                        |
| `Ctrl` + `clic izquierdo` + `arrastrar`          | rotar la vista en sentido horario/antihorario                           |
| `clic derecho` + `arrastrar arriba/abajo`        | acercar/alejar la vista (`Alt` opcional, útil durante la colocación de puntos) |
| `Ctrl` + `rueda del mouse`                       | acercar/alejar la vista                                                  |
| `Ctrl` + `b`                                     | alternar el bloqueo de inclinación                                      |
| `+` / `-`                                        | acercar/alejar la vista                                                  |
| `clic central` + `arrastrar`                     | desplazar (trasladar) la vista (`Alt` opcional, útil durante la colocación de puntos) |
| `Shift` + `clic izquierdo` + `arrastrar`         | desplazar (trasladar) la vista (`Alt` opcional, útil durante la colocación de puntos) |
| `Shift` + `flecha izquierda` / `Shift` + `flecha derecha` | desplazar (trasladar) la vista                                 |
| `Shift` + `flecha arriba` / `Shift` + `flecha abajo` | desplazar (trasladar) la vista                                      |
| `Shift` + `Teclado numérico 2` / `Shift` + `Teclado numérico 4` | desplazar (trasladar) la vista                            |
| `Shift` + `Teclado numérico 6` / `Shift` + `Teclado numérico 8` | desplazar (trasladar) la vista                            |
| `Teclado numérico 0` o `Insert`                  | restablecer el zoom y el desplazamiento, rotar a la vista estándar más cercana |
| `doble clic izquierdo`                           | maximizar la vista/restaurar el diseño de la vista                      |


Nota

Simulación si los atajos no están disponibles en su dispositivo:

- Mouse de un botón: en lugar de `clic derecho`, haga `Ctrl` + `clic`

- Trackpad: en lugar de `clic derecho`, haga `clic con dos dedos`

### Consola de Python

Los siguientes atajos están disponibles en la consola de Python.

| Atajo                          | Operación                                                                          |
| ------------------------------ | ---------------------------------------------------------------------------------- |
| `Tab`                          | autocompletar                                                                      |
| `flecha arriba` / `flecha abajo` | historial de comandos                                                            |
| `Esc`                          | borrar la selección, volver a la línea de comandos actual, borrar la línea de comandos actual |
| `Ctrl` + `g`                   | ejecutar un script de Python desde un archivo                                      |
| `Ctrl` + `v`                   | pegar un script de Python desde el portapapeles y ejecutarlo                       |


Tenga en cuenta que, cuando el código se pega en una línea vacía, todo el código del portapapeles se ejecuta *de una sola vez*. Si la línea de comandos actual no está vacía, el código del portapapeles se pega en la consola y se ejecuta *línea por línea*. Cuando el código se ejecuta línea por línea, el comportamiento es diferente, ya que una línea de entrada vacía cierra inmediatamente el bloque actual, y la salida se imprime después de ejecutar cada línea.
