# Acerca de 3D Slicer

## ¿Qué es 3D Slicer?

- Una aplicación de software para la visualización y el análisis de conjuntos de datos de computación de imágenes médicas. Se admiten todos los tipos de datos de uso común, como imágenes, segmentaciones, superficies, anotaciones, transformaciones, etc., en 2D, 3D y 4D. La visualización está disponible en el escritorio y en realidad virtual. El análisis incluye segmentación, registro y diversas cuantificaciones.

- Una plataforma de software de investigación, que permite a los investigadores desarrollar y evaluar rápidamente nuevos métodos y distribuirlos a usuarios clínicos. Todas las funciones están disponibles y son ampliables en Python y C++. Se proporciona un entorno completo de Python en el que se puede instalar cualquier paquete de Python y combinarlo con las funciones integradas. Slicer cuenta con una consola de Python integrada y puede actuar como kernel de cuadernos Jupyter con capacidades de renderizado 3D remoto.

- Una plataforma de desarrollo de productos, que permite a las empresas prototipar y lanzar rápidamente productos a los usuarios. Los desarrolladores pueden concentrarse en desarrollar nuevos métodos y no necesitan dedicar tiempo a volver a desarrollar funciones básicas de importación/exportación de datos, visualización e interacción. La aplicación está diseñada para ser altamente personalizable (con marca propia, interfaz de usuario simplificada, etc.). 3D Slicer es completamente gratuito y no hay restricciones sobre cómo se usa: corresponde al distribuidor del software asegurarse de que la aplicación desarrollada sea adecuada para el uso previsto.

**Nota:** No hay restricción de uso, pero Slicer **NO** está aprobado para uso clínico y la aplicación distribuida está destinada a uso de investigación. Los permisos y el cumplimiento de las normas aplicables son responsabilidad del usuario. Para más detalles sobre la licencia, consulte [aquí](https://www.slicer.org/wiki/License).

Aspectos destacados:

- Software gratuito y de [código abierto](https://en.wikipedia.org/wiki/Open_source) disponible en múltiples sistemas operativos: Linux, macOS y Windows.

- Multiórgano: de la cabeza a los pies.

- Compatibilidad con imágenes multimodalidad, incluyendo resonancia magnética (RM), tomografía computarizada (TC), ecografía (US), medicina nuclear y microscopía.

- Interfaz en tiempo real para dispositivos médicos, como sistemas de navegación quirúrgica, sistemas de imagen, dispositivos robóticos y sensores.

- Altamente ampliable: los usuarios pueden agregar fácilmente más capacidades instalando módulos adicionales desde el Administrador de extensiones, ejecutando scripts personalizados de Python en la consola de Python integrada, ejecutando cualquier programa ejecutable desde la interfaz de usuario de la aplicación, o implementando módulos personalizados en Python o C++.

- Una comunidad de usuarios grande y activa.

## Licencia

El software 3D Slicer se distribuye bajo una licencia de código abierto de estilo BSD que es ampliamente compatible con la Definición de Código Abierto de [The Open Source Initiative](https://opensource.org/) y no contiene restricciones sobre los usos legales del software.

Para usar Slicer, lea el [Acuerdo de Licencia de Software de 3D Slicer](https://github.com/Slicer/Slicer/blob/main/License.txt) antes de descargar cualquier versión binaria de Slicer.

### Notas históricas sobre la licencia

La Licencia de Slicer fue redactada en 2005 por abogados que trabajaban para el Brigham and Women's Hospital (BWH), un hospital universitario afiliado a la Facultad de Medicina de Harvard, con el fin de ser de estilo BSD pero con algunas disposiciones adicionales relacionadas con el software médico. Es específica del BWH, por lo que no es directamente reutilizable, pero podría servir como plantilla para proyectos con objetivos similares.

Se redactó en parte porque el BWH era el contratista principal de un consorcio de desarrollo financiado por los NIH ([NA-MIC](https://www.na-mic.org/)) y quería que todas las contribuciones de código fueran compatibles con el uso final en productos médicos del mundo real (es decir, dispositivos médicos comerciales aprobados por la FDA, que son casi universalmente de código cerrado incluso cuando se basan en software abierto). El cumplimiento de la Licencia de Slicer era obligatorio para los subcontratistas, un grupo que incluía a GE Research, Kitware y varias universidades (MIT, UNC…) que revisaron y aceptaron esta licencia.

La licencia ha estado en uso continuo desde 2005 para el paquete de software 3D Slicer ([slicer.org](http://slicer.org)) que, hasta 2021, se había descargado más de un millón de veces y había sido citado en cerca de 12 000 publicaciones académicas (<https://www.slicer.org/wiki/Main_Page/SlicerCommunity>). Parte del código también se utiliza ahora en varios productos médicos para los cuales las empresas involucradas han revisado y aceptado esta licencia.

### Términos de la licencia y sus motivos

Estos son algunos de los puntos clave que el BWH incluyó además de los términos BSD para adaptar la licencia al caso de un gran hospital que distribuye software médico de código abierto.

Para usar y redistribuir 3D Slicer:

- La licencia indica que el código está "diseñado para investigación" y que "LAS APLICACIONES CLÍNICAS NO SE RECOMIENDAN NI SE ACONSEJAN", para dejar muy claro que cualquier uso clínico comercial del código es responsabilidad exclusiva del usuario y no del BWH ni de los demás desarrolladores. Esto es una cláusula de exención de responsabilidad y no una restricción legal.

Para realizar cambios o agregar cualquier código fuente o dato a 3D Slicer:

- Los colaboradores otorgan explícitamente derechos libres de regalías si contribuyen con código cubierto por una patente que controlan (es decir, para evitar las patentes ocultas o "submarinas").

- No se permite código GPL ni otro código copyleft, porque eso podría hacer complicado y arriesgado mezclar el código de Slicer con propiedad intelectual privada, que suele estar presente en productos médicos regulados.

- Los colaboradores afirman que han anonimizado cualquier dato de pacientes que aporten, para evitar problemas con la HIPAA o normativas relacionadas.

### Situación en comparación con otras licencias de código abierto

A junio de 2021, la Licencia de Slicer se había utilizado durante más de 15 años sin incidentes. En mayo de 2021, un usuario del foro Discourse [sugirió](https://discourse.slicer.org/t/apply-for-osi-open-source-license-status/17791) enviar la licencia al [proceso de revisión de licencias de la OSI](https://opensource.org/approval). Tras cierta discusión y al no recibir objeciones, el liderazgo de la comunidad decidió [enviar la licencia para su revisión](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/2021-May/thread.html). Aunque el proceso de la OSI no es jurídicamente vinculante, la discusión podría dar a los posibles usuarios de Slicer una perspectiva sobre cómo se comparan las disposiciones de la licencia con otras licencias de uso común.
La discusión concluyó que incluir el acuerdo de contribución dentro de la licencia hace que la OSI no pueda aprobarla, y que el requisito de usar el software con fines legales podría no ser coherente con la [Definición de Código Abierto](https://opensource.org/osd). Por lo demás, los términos de la licencia no parecen ser controvertidos. Las partes interesadas deben revisar la [discusión completa](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/2021-June/thread.html#5166) para más detalles.

## Cómo citar

### 3D Slicer como plataforma

Para reconocer a 3D Slicer como plataforma, cite el [sitio web de Slicer](https://www.slicer.org/) y las siguientes publicaciones cuando publique trabajos que utilicen o incorporen 3D Slicer:

**Fedorov A., Beichel R., Kalpathy-Cramer J., Finet J., Fillion-Robin J-C., Pujol S., Bauer C., Jennings D., Fennessy F.M., Sonka M., Buatti J., Aylward S.R., Miller J.V., Pieper S., Kikinis R. [3D Slicer as an Image Computing Platform for the Quantitative Imaging Network](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3466397/pdf/nihms383480.pdf). Magnetic Resonance Imaging. 2012 Nov;30(9):1323-41. PMID: 22770690. PMCID: PMC3466397.**

## El nombre y el logotipo de 3D Slicer

3D Slicer y el logotipo son marcas registradas del Brigham and Women's Hospital (BWH) y no pueden utilizarse sin permiso. Dicho permiso se concede ampliamente para usos académicos o comerciales, como documentar el uso de Slicer en su proyecto o promover el uso de Slicer por parte de otros. Utilice los colores originales del logotipo de Slicer y no altere su forma ni su texto. No está permitido usar Slicer para dar a entender que el BWH o la comunidad de Slicer respaldan su producto o proyecto sin autorización. Para otros usos, comuníquese con Ron Kikinis ([kikinis@bwh.harvard.edu](mailto:kikinis%40bwh.harvard.edu)) y Steve Pieper ([pieper@bwh.harvard.edu](mailto:pieper%40bwh.harvard.edu)).

### Módulos individuales

Para reconocer módulos individuales: cada módulo tiene una pestaña de agradecimientos en la sección superior. Allí se puede encontrar información sobre los colaboradores y la fuente de financiación:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/acknowledgement_ack_tab.png)

Por lo general, se puede encontrar información adicional (incluida información sobre las publicaciones subyacentes) en las páginas del manual accesibles a través de la pestaña de ayuda en la sección superior:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/acknowledgement_help_tab.png)

## Agradecimientos

Slicer es posible gracias a las contribuciones de una comunidad internacional de científicos de multitud de campos, incluidos la ingeniería y la biomedicina. Las siguientes secciones dan crédito a algunos de los principales colaboradores del esfuerzo central de 3D Slicer. Cada extensión de 3D Slicer tiene una página de agradecimientos independiente con información específica de esa extensión.

El apoyo continuo a Slicer depende de USTED.

Por favor, dé una estrella al repositorio de Slicer en GitHub. Es una forma sencilla de mostrar agradecimiento y puede ayudarnos a calificar para servicios útiles que solo están disponibles para proyectos abiertos ampliamente reconocidos.
No olvide citar nuestras publicaciones, porque eso nos ayuda a obtener nuevo financiamiento mediante subvenciones.
Si Slicer le resulta útil, como a la comunidad, le invitamos a participar. ¡No necesita ser programador para ayudar!

### Principales colaboradores

- Ron Kikinis: Investigador principal

- Steve Pieper: Arquitecto jefe

- Jean-Christophe Fillion-Robin: Desarrollador principal

- Nicole Aucoin

- Stephen Aylward

- Andrey Fedorov

- Noby Hata

- Hans Johnson

- Tina Kapur

- Gabor Fichtinger

- Andras Lasso

- Csaba Pinter

- Jim Miller

- Sonia Pujol: Directora de Capacitación

- Junichi Tokuda

- Lauren O'Donnell

- Andinet Enquobahrie

- Beatriz Paniagua

*Los colaboradores no son únicamente desarrolladores, sino también personas que ayudan a asegurar financiamiento y a impulsar el avance de la plataforma.*

### Grupos que contribuyen de manera importante a la ingeniería central de Slicer

- SPL: Ron Kikinis, Nicole Aucoin, Lauren O'Donnell, Andrey Fedorov, Isaiah Norton, Sonia Pujol, Noby Hata, Junichi Tokuda

- Isomics: Steve Pieper, Alex Yarmarkovich

- Kitware: Jean-Christophe Fillion-Robin, Julien Finet, Will Schroeder, Stephen Aylward, Andinet Enquobahrie, Beatriz Paniagua, Matt McCormick, Johan Andruejol, Max Smolens, Alexis Girault, Sam Horvath

- Universidad de Iowa: Hans Johnson

- GE: Jim Miller

- Perk Lab, Queen's University: Andras Lasso, Tamas Ungi, Csaba Pinter, Gabor Fichtinger

- Instituto Astronómico Kapteyn, Universidad de Groninga: Davide Punzo

### Fuentes de financiación

Muchas de las actividades en torno al esfuerzo de Slicer son posibles gracias al financiamiento de fuentes públicas y privadas. Los Institutos Nacionales de Salud de los EE. UU. (NIH) son un contribuyente importante a través de una variedad de subvenciones y contratos competitivos. Las fuentes de financiación que contribuyen al desarrollo del núcleo de Slicer o de sus extensiones incluyen (ordenadas por fecha de finalización):

| Número de subvención | Descripción | Investigadores principales (PIs) | Fecha de inicio | Fecha de finalización | Título |
| --- | --- | --- | --- | --- | --- |
| CHOP | Programa Frontier de CHOP | Matthew Jolley | 2024-07-01 | a la fecha | Los Programas Frontier del Children's Hospital of Philadelphia realizan investigación visionaria que se traduce en atención de vanguardia |
| NSF/DBI 2301405 | MorphoCloud y MorphoDepot | Murat Maga | 2024-03-01 | 2028-02-28 | MorphoCloud: una plataforma de código abierto basada en la nube para la investigación, la enseñanza y la colaboración en morfología digital 3D y más |
| NSF/OAC 2118240 | Extensión de fotogrametría | Murat Maga | 2021-09-15 | 2026-08-31 | Imageomics: una nueva frontera de información biológica impulsada por aprendizaje automático guiado por conocimiento |
| AV 993932 | SlicerHeart para ventrículo único | Matthew Jolley | 2023-03-01 | 2026-02-28 | Modelado computacional de la reparación de la válvula auriculoventricular en pacientes con ventrículo único y canal auriculoventricular |
| NIH P01HD104435 | Segmentaciones multiórgano de embriones de ratón (MEMOS), extensión ANTsPy, terminologías | Murat Maga | 2021-01-11 | 2025-12-31 | Análisis cuantitativo 3D de modelos murinos de defectos congénitos estructurales mediante anatomía computacional |
| [NIH 1R01HL153166-01](https://projectreporter.nih.gov/project_info_description.cfm?aid=10029738&icde=51006191) | Modelado computacional de la válvula tricúspide en HLHS | Matthew Jolley | 2021-06-30 | 2025-06-30 | Modelado computacional de la válvula tricúspide en el síndrome del corazón izquierdo hipoplásico |
| NIH R03OD032627 | Kit de análisis de correspondencia densa (DeCA) | Murat Maga | 2021-09-22 | 2023-09-21 | Fenotipado profundo de datos 3D para la selección de genes candidatos a partir de estudios Kids First |
| [CZI EOSS 4](https://chanzuckerberg.com/eoss/proposals/3d-slicer-in-my-language-internationalization-and-usability-improvements/) | Internacionalización y usabilidad de Slicer | Pujol, Sonia | 2021-09-01 | 2023-09-01 | 3D Slicer en mi idioma: mejoras de internacionalización y usabilidad |
| [NIH 4P41EB015902](https://projectreporter.nih.gov/project_info_description.cfm?aid=9115586&icde=31485398&ddparam=&ddvalue=&ddsub=&cr=3&csb=default&cs=ASC) | Centro de Análisis de Neuroimagen | Ron Kikinis | 2013-08-01 | 2023-08-31 | Aplicación de Slicer a la neurocirugía guiada por imagen y otras aplicaciones mediante computación dirigida y bases de datos de navegación por imagen |
| CANARIE RS3-036 | SlicerAIGT | Fichtinger, Gabor | 2020-10-01 | 2023-03-31 | Desarrollar software de investigación gratuito y de código abierto para terapia guiada por imagen impulsada por IA en la plataforma Slicer |
| [NIH R01MH112748](https://reporter.nih.gov/search/-oPV-FDakki3bPslkjMUwg/project-details/10053340) | Herramientas de segmentación cerebral de alta precisión | Bouix, Sylvain | 2017-12-01 | 2022-10-31 | Atlas integrales y de alta resolución de la morfología del cerebro humano |
| NSF/DBI 1759883 | Extensión SlicerMorph, infraestructura de Markups | Murat Maga | 2018-08-01 | 2022-07-31 | Una plataforma integrada para la recuperación, visualización y análisis de morfología 3D a partir de colecciones biológicas digitales |
| [NIH R44DK115332](https://www.sbir.gov/sbirsearch/detail/1683213) | Biopsia renal | Enquobahrie, Andinet A. | 2019-08-13 | 2021-07-31 | Simulador virtual avanzado para el entrenamiento de biopsia renal guiada por ecografía en tiempo real |
| ICEX 0202101723 | Colaboración SlicerVR | Juan Ruiz Alzola | 2021-01-16 | 2021-12-31 | Sistema Virtual Colaborativo de Aplicaciones Médicas |
| [NIH R01EB025212](https://govtribe.com/award/federal-grant-award/project-grant-r01eb025212) | Anotación de software | Enquobahrie, Andinet A. | 2019-07-02 | 2021-03-31 | Software para la anotación e intercambio práctico de anatomía virtual |
| CANARIE RS319 | SlicerIGT | Fichtinger, Gabor | 2019-10-01 | 2020-09-30 | Infraestructura canadiense de software de investigación |
| CANARIE RS214 | SlicerRT | Fichtinger, Gabor | 2017-07-01 | 2020-09-30 | Infraestructura canadiense de software de investigación |
| CHOP | SlicerHeart | Matthew Jolley | 2015-08-15 | 2020-08-15 | Modelado de válvulas cardíacas pediátricas, Children's Hospital of Philadelphia |
| [MAC/1.1b/098](https://mt4sd.ulpgc.es/en/macbioidi-project/) | MACBIOLDI | Juan Ruiz Alzola | 2017-01-01 | 2020-09-30 | Tecnología médica para el desarrollo sostenible (MedTec4SusDev) |
| [NIH 2P41EB015898](https://projectreporter.nih.gov/project_info_details.cfm?aid=8855115&icde=27026518) | DiffusionMRI | Tempany, Clare M | 2004-04-01 | 2020-06-30 | Centro de Terapia Guiada por Imagen |
| [NIH 5P41EB015898](https://projectreporter.nih.gov/project_info_description.cfm?aid=9125821&icde=31485478&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC) | Centro Nacional de Terapia Guiada por Imagen | Clare Tempany | 2004-04-01 | 2020-06-30 | Uso de Slicer en una amplia gama de investigaciones de terapia guiada por imagen para el cáncer de próstata, la neurocirugía y la navegación por imagen |
| [NIH 1R01EB021391](https://projectreporter.nih.gov/project_info_description.cfm?aid=9123966&icde=31459429&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC) | Shape | Paniagua, Beatriz | 2016-09-19 | 2020-06-30 | Caja de herramientas de análisis de forma para proyectos de computación de imágenes médicas |
| [NIH U24CA194354](https://projectreporter.nih.gov/project_info_description.cfm?aid=8875289&icde=27050248) | Slicer-Radiomics-U24 | Aerts, Hugo | 2015-04-01 | 2020-03-31 | Sistema cuantitativo de radiómica para decodificar el fenotipo tumoral |
| [NIH 1U01CA190234](https://projectreporter.nih.gov/project_info_description.cfm?aid=8799943&icde=27026470) | Slicer-Radiomics-U01 | Aerts, Hugo | 2015-01-01 | 2019-12-01 | Biomarcadores de genotipo y fenotipo de imagen en el cáncer de pulmón |
| [NIH 5U24CA180924](https://projectreporter.nih.gov/project_info_details.cfm?aid=9127923&icde=31460433&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC) | Análisis de datos moleculares mapeados espacialmente | Joel Saltz | 2014-09-01 | 2019-08-31 | Herramientas para analizar la morfología y los datos moleculares mapeados espacialmente |
| [NIH 5R01CA184354](https://projectreporter.nih.gov/project_info_description.cfm?aid=8828624&icde=27036841&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | NIRFAST (Dartmouth) | Davis, Scott C. | 2014-04-01 | 2019-02-28 | Tomografía de fluorescencia por RM para cuantificar la concentración de receptores tumorales in vivo |
| [NIH R43DE027595](https://projectreporter.nih.gov/project_info_description.cfm?aid=9465772&icde=36620728&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC&pball=) | VROrthognathic | Paniagua, Beatriz | 2017-09-07 | 2018-09-06 | Entrenador de realidad virtual de alta fidelidad para cirugía ortognática |
| [NIH 1R21DE025306](https://projectreporter.nih.gov/project_info_description.cfm?aid=9111256&icde=31459429&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | CMF | Paniagua, Beatriz | 2016-09-01 | 2018-08-31 | Biomarcadores de textura de la artritis para el hueso subcondral en la articulación temporomandibular |
| [NIH 1U01NS082086](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462842&icde=27164806&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_SHAPEANALSS | Gerig, Guido | 2012-09-28 | 2018-08-31 | Análisis de forma 4D para modelar trayectorias de cambio espaciotemporal en la enfermedad de Huntington |
| [NIH U24 CA180918](https://projectreporter.nih.gov/project_info_description.cfm?aid=8911287&icde=27026906) | [QIICR](https://qiicr.org) | Ron Kikinis, Andrey Fedorov | 2013-09-04 | 2018-08-31 | Informática cuantitativa de imágenes para la investigación del cáncer (QIICR) |
| [NIH 5R01NS055903](https://projectreporter.nih.gov/project_info_description.cfm?aid=8900362&icde=27164764&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_KIDS | Nopoulos, Peggy | 2009-03-01 | 2018-07-31 | Crecimiento y desarrollo del cuerpo estriado en la enfermedad de Huntington |
| [NIH 1U01CA199459](https://projectreporter.nih.gov/project_info_description.cfm?aid=8971083&icde=27026834) | SlicerDMRI Diffusion MRI | O'Donnell, Lauren Jean | 2015-09-22 | 2018-07-31 | Tecnología de RM por difusión de código abierto para la investigación del cáncer cerebral |
| [NIH 5R01EB020667-02](https://projectreporter.nih.gov/project_info_description.cfm?aid=9100712&icde=34329960) | OpenIGTLink | Tokuda, Junichi | 2015-07-01 | 2018-06-30 | OpenIGTLink: una interfaz de comunicación en red para intervenciones guiadas por imagen de ciclo cerrado |
| [NIH 5P41EB015902](https://projectreporter.nih.gov/project_info_description.cfm?aid=8890837&icde=27036647&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | DiffusionMRI | Kikinis, Ron | 2013-08-01 | 2018-05-31 | Centro de Análisis de Neuroimagen (NAC) |
| [NIH 2R42HD081712](https://projectreporter.nih.gov/project_info_description.cfm?aid=9141675&icde=31459353&ddparam=&ddvalue=&ddsub=&cr=5&csb=default&cs=ASC) | Craneosinostosis | Linguraru, Marius George | 2016-05-01 | 2018-04-30 | Sistema de planificación guiada por imagen para la corrección del cráneo en niños con craneosinostosis: Fase II |
| [NIH R01CA160902](https://projectreporter.nih.gov/project_info_description.cfm?aid=8817256&icde=27036729&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | DWI | Maier, Stephan E | 2012-04-01 | 2018-02-28 | Avance y validación de la RM por difusión y espectroscópica de próstata |
| [NIH 1R01DE024450](https://projectreporter.nih.gov/project_info_description.cfm?aid=8576556&icde=18353487) | CMF | Cevidanes, Lucia | 2013-09-10 | 2017-08-31 | Cuantificación de cambios óseos 3D en la osteoartritis de la articulación temporomandibular |
| [NIH 2R42CA167907](https://projectreporter.nih.gov/project_info_description.cfm?aid=8979242&icde=27036988&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Fantoma de calibración PET/CT | Kinahan, Paul E | 2012-05-01 | 2017-07-31 | Métodos calibrados para la obtención de imágenes cuantitativas PET/CT, Fase II |
| [NIH R42CA167907](https://projectreporter.nih.gov/project_info_description.cfm?aid=8979242&icde=27036988&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Fantoma de calibración PET/CT | Kinahan, Paul E. | 2012-05-01 | 2017-07-01 | Métodos calibrados para la obtención de imágenes cuantitativas PET/CT, Fase II |
| NA | HD_TRACKON | Tabrizi, Sarah | 2012-01-01 | 2016-12-31 | TRACK-ON HD |
| CCO ACRU | SlicerRT | Fichtinger, Gabor | 2011-01-01 | 2016-12-31 | Unidad de Investigación Aplicada del Cáncer de Cancer Care Ontario, Canadá |
| CCO OCAIRO | SlicerRT | Jaffray, David | 2011-01-01 | 2016-12-31 | Consorcio de Ontario para Intervenciones Adaptativas en Oncología Radioterápica, Canadá |
| NA | HD_TRAJECTORY | Kim, Eun Young | 2014-11-01 | 2016-10-31 | Desarrollo de una canalización de segmentación robusta que permita la estimación coherente de trayectorias en individuos con gen HD positivo en múltiples sitios de RM longitudinal |
| [NIH 1R41HD081712](https://projectreporter.nih.gov/project_info_description.cfm?aid=8778815&icde=27036063&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASCIMAGE-GUIDED) | Craneosinostosis | Linguraru, Marius George | 2014-09-26 | 2016-08-31 | Sistema de planificación guiada por imagen para la corrección del cráneo en niños con craneosinostosis |
| [NIH 5R01NS040068](https://projectreporter.nih.gov/project_info_description.cfm?aid=8338456&icde=27164778&ddparam=&ddvalue=&ddsub=&cr=4&csb=default&cs=ASC) | HD_PREDICT | Paulsen, Jane | 2000-08-01 | 2016-08-31 | Predictores neurobiológicos de la enfermedad de Huntington (PREDICT-HD) |
| [NIH 3R42CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=8863934&icde=27037113&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Biopsia con aguja guiada por PET-CT | Cleary, Kevin R. | 2012-09-01 | 2016-08-01 | Mejora de la biopsia de lesiones hepáticas en la sala de TC mediante la fusión con imágenes PET |
| [NIH 1R43DE024334](https://projectreporter.nih.gov/project_info_description.cfm?aid=8710950&icde=27036891) | OrthognathicTrac | Enquobahrie, Andinet A. | 2014-08-05 | 2016-07-31 | Guía por imagen en tiempo real para mejorar la cirugía ortognática |
| [NIH 1R01EB014947](https://projectreporter.nih.gov/project_info_description.cfm?aid=8272742&icde=13552329) | PediatricRadiologicDecisionSupport | Murphy, Shawn N | 2012-08-01 | 2016-07-31 | Apoyo a la decisión radiológica pediátrica habilitado por Mi2B2 |
| [NIH 5R01CA111288](https://projectreporter.nih.gov/project_info_description.cfm?aid=8906771&icde=27026518) | ProstateBRP | Tempany, Clare M. | 2004-12-01 | 2016-07-01 | Tecnologías habilitadoras para intervenciones de próstata guiadas por RM |
| [NIH 5U01CA151261](https://projectreporter.nih.gov/project_info_description.cfm?aid=8707214&icde=27026645) | ProstateQIN | Fennessy, Fiona | 2010-09-01 | 2016-07-01 | RM cuantitativa del cáncer de próstata como biomarcador y guía para el tratamiento |
| [NIH 1U01NS082074](https://projectreporter.nih.gov/project_info_description.cfm?aid=8596213&icde=27164895&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_GENETICS | Calhoun/Turner | 2013-07-01 | 2016-06-30 | Imagen y genética en la enfermedad de Huntington |
| [NIH 1U01NS083173](https://projectreporter.nih.gov/project_info_description.cfm?aid=8529927&icde=27164835&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_PET | Feigin, Andrew | 2013-07-01 | 2016-06-30 | Imagen de redes cerebrales: un nuevo biomarcador para la enfermedad de Huntington preclínica |
| [NIH 1R01CA170665](https://projectreporter.nih.gov/project_info_description.cfm?aid=8384153&icde=27037397&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Dayton, Paul A. | 2012-09-01 | 2016-06-01 | Detección de microtumores mediante la cuantificación de anomalías vasculares inducidas por tumores |
| [NIH 1U01NS083223](https://projectreporter.nih.gov/project_info_description.cfm?aid=8652000&icde=27164795&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_WHITEMATTER | Westin, Carl-Fredrik | 2014-01-01 | 2015-12-31 | Caracterización de la sustancia blanca en la enfermedad de Huntington mediante RM por difusión |
| CCO RC | SlicerRT | Fichtinger, Gabor | 2010-01-01 | 2015-12-31 | Cátedra de Investigación de Cancer Care Ontario, Canadá |
| [NIH 1U01NS082083](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462829&icde=27164863&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_FMRI_DWI | Rao, Stephen Mark | 2012-09-26 | 2015-08-31 | Conectividad funcional en la enfermedad de Huntington premanifiesta |
| [NIH R41CA196565](https://projectreporter.nih.gov/project_info_description.cfm?aid=8905274&icde=27036277&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Registro de próstata de Duke | Palmeri, Mark L. y McCormick, Matthew M. | 2015-04-01 | 2015-04-01 | Evaluación del cáncer de próstata mediante imagen de elasticidad ARFI 3D integrada y RM multiparamétrica |
| [NIH 1R43EB016621](https://projectreporter.nih.gov/project_info_description.cfm?aid=8472102&icde=27037328&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Aylward, Stephen R. | 2013-05-01 | 2015-04-01 | Soporte y automatización rápidos de procedimientos en campo |
| [NIH 1R41NS081792](https://projectreporter.nih.gov/project_info_description.cfm?aid=8453963&icde=27037364&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Aylward, Stephen R. | 2013-01-01 | 2014-12-01 | Sistema de evaluación multimodalidad basado en imagen para lesiones cerebrales traumáticas |
| [NIH 2R42CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=8390856&icde=27037039&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Biopsia con aguja guiada por PET-CT | Cleary, Kevin R. | 2012-09-01 | 2014-08-01 | Mejora de la biopsia de lesiones hepáticas en la sala de TC mediante la fusión con imágenes PET |
| [NIH 1R43CA165621](https://projectreporter.nih.gov/project_info_description.cfm?aid=8252988&icde=27037450&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Aylward, Stephen R | 2012-12-01 | 2014-08-01 | Análisis ecográfico cuantitativo de la morfología vascular para la evaluación del cáncer |
| [NIH 5U01NS082085](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462830&icde=27164813&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_SUBCORTICAL_SHAPE | Miller, Michael y Ross, Christopher | 2012-09-26 | 2014-07-31 | Análisis de forma de los ganglios basales y circuitos en la enfermedad de Huntington |
| [NIH 5U54EB005149](https://projectreporter.nih.gov/project_info_description.cfm?aid=8501010&icde=27164945&ddparam=&ddvalue=&ddsub=&cr=5&csb=default&cs=ASC) | HD_DWI | Kikinis, Ron | 2010-09-30 | 2014-06-30 | Alianza Nacional para la Computación de Imágenes Médicas |
| [NIH 5R01NS054893](https://projectreporter.nih.gov/project_info_description.cfm?aid=8077226&icde=27164732&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_FMRI | Paulsen, Jane | 2007-05-15 | 2013-04-30 | Cambios cognitivos y funcionales del cerebro en la enfermedad de Huntington preclínica (HD) |
| [NIH R41CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=7999618&icde=27037084&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Biopsia con aguja guiada por PET-CT | Cleary, Kevin R. | 2010-07-01 | 2012-06-01 | Mejora de la biopsia de lesiones hepáticas en la sala de TC mediante la fusión con imágenes PET |

## Uso comercial

Invitamos a las entidades comerciales a utilizar 3D Slicer.

### La licencia de Slicer permite el uso comercial

- 3D Slicer es un software gratuito y de código abierto distribuido bajo una licencia de estilo BSD.

- La licencia no impone restricciones sobre el uso del software.

- 3D Slicer NO está aprobado por la FDA. Es responsabilidad del usuario asegurar el cumplimiento de las normas y regulaciones aplicables.

- Para más detalles, consulte el Acuerdo de Licencia de Software de 3D Slicer.

### Socios comerciales

- [Ebatinca SL](https://ebatinca.com/) es una empresa tecnológica internacional ubicada en Las Palmas, España, enfocada en tecnología para el desarrollo sostenible. Áreas principales: navegación y entrenamiento por ecografía, RV colaborativa, apoyo a la investigación y soluciones personalizadas basadas en Slicer.

- [Isomics](https://isomics.com/) utiliza 3D Slicer en una variedad de colaboraciones de investigación académica y comercial en campos como la planificación y guía para neurocirugía, la imagen cuantitativa para ensayos clínicos y la informática de imágenes clínicas.

- [Kitware](https://www.kitware.com/opensource/slicer.html) se centra en resolver los desafíos científicos más complejos del mundo mediante soluciones de software personalizadas. La empresa tiene una larga trayectoria de contribución a plataformas de código abierto que sirven de base para muchas aplicaciones de visualización médica y procesamiento de datos. Kitware ayuda a sus clientes a desarrollar productos comerciales basados en 3D Slicer y ha utilizado la plataforma para prototipar rápidamente soluciones en prácticamente todos los aspectos de la imagen médica.

*Listados en orden alfabético.*

### Productos basados en 3D Slicer

Muchas empresas prefieren no revelar qué componentes de software utilizan en sus productos, por lo que aquí solo podemos enumerar algunos productos comerciales que se basan en 3D Slicer:

- Allen Institute for Brain Science: el Allen Institute for Brain Science está desarrollando Cell Locator, una aplicación de escritorio para alinear manualmente muestras con espacios 3D anotados. Vea más información en este [blog de Kitware](https://blog.kitware.com/cell-locator-a-3d-slicer-based-desktop-application-that-manually-aligns-specimens-to-annotated-3d-spaces-developed-for-the-allen-institute-for-brain-science/).

- [Dent.AI Medical Imaging](https://thedent.ai) está desarrollando un sistema de planificación de cirugía oral impulsado por IA que genera modelos virtuales realistas de pacientes a partir de datos de CBCT y escaneo intraoral para apoyar la colocación de implantes navegada y los procedimientos de reconstrucción ósea.

- [EBATINCA](https://ebatinca.com) está desarrollando StaRT, una plataforma interactiva para la simulación y la educación en radioterapia, que ofrece flujos de trabajo clínicos realistas y ejercicios basados en casos diseñados para estudiantes y profesionales clínicos de todo el mundo. Vea más información en [el sitio web del producto](https://ebatinca.com/productos/start).

- [Polarean, Inc.](https://polarean.com/): XENOVIEW VDP de Polarean es un software aprobado por la FDA y construido sobre 3D Slicer para la visualización y evaluación de la ventilación pulmonar. Vea más información en este [blog de Kitware](https://www.kitware.com/kitware-supports-development-and-launch-of-fda-cleared-mr-image-processingsoftware-for-lung-ventilation-imaging/).

- Imagen y dosimetría radiofarmacéutica: RPTDose, una aplicación basada en 3D Slicer que agiliza e integra técnicas de análisis de imagen cuantitativa y estimación de dosis para guiar y optimizar el uso de agentes de terapia radiofarmacéutica en ensayos clínicos. Vea más información en este [blog de Kitware](https://blog.kitware.com/kitware-customer-highlight-radiopharmaceutical-imaging-and-dosimetry-llc-rapid/).

- [SonoVol](https://sonovol.com/) desarrolló un sistema de imagen por ecografía de cuerpo entero para animales pequeños. Esta empresa emergente surgió de la investigación en el Departamento de Ingeniería Biomédica de la Universidad de Carolina del Norte en Chapel Hill. Su equipo ahora forma parte de Revvity, Inc. Vea más información en este [blog de Kitware](https://blog.kitware.com/kitware-customer-highlight-sonovol/) y en su [sitio web del producto](https://www.perkinelmer.com/category/ultrasound-imaging).

- Xoran Technologies: plataforma guiada por imagen para cirugía de estimulación cerebral profunda. Vea más información en este [blog de Kitware](https://blog.kitware.com/xoran-technologies-and-kitware-collaborate-on-image-guided-platform-for-deep-brain-stimulation-surgery/).

- [Xstrahl](https://www.xstrahl.com/) está desarrollando una plataforma de investigación en radiación de animales pequeños (SARRP) que utiliza 3D Slicer como su aplicación frontal para la colocación de haces de radioterapia y el control del sistema. Vea más información en este [blog de Kitware](https://blog.kitware.com/kitware-customer-highlight-muriplan-from-xstrahl-a-3d-slicer-based-radiotherapy-treatment-planning-system/).

*Listados en orden alfabético.*

## Gobernanza

Esta sección presenta los principios rectores y el marco de toma de decisiones del proyecto Slicer, incluido el Código de Conducta y el modelo de gobernanza que describen cómo se toman las decisiones y quién es responsable de mantener la salud del proyecto.

### Código de Conducta

La comunidad de Slicer se compromete a fomentar un entorno acogedor, respetuoso e inclusivo. Los detalles se describen en el Código de Conducta a continuación.

#### Nuestro compromiso

Como miembros, colaboradores y líderes, nos comprometemos a hacer de la participación en nuestra comunidad una experiencia libre de acoso para todas las personas, sin importar su edad, complexión corporal, discapacidad visible o invisible, etnia, características sexuales, identidad y expresión de género, nivel de experiencia, educación, nivel socioeconómico, nacionalidad, apariencia personal, raza, casta, color, religión, o identidad y orientación sexual.

Nos comprometemos a actuar e interactuar de maneras que contribuyan a una comunidad abierta, acogedora, diversa, inclusiva y sana.

#### Nuestros estándares

Ejemplos de comportamiento que contribuye a un entorno positivo para nuestra comunidad incluyen:

- Demostrar empatía y amabilidad hacia las demás personas

- Ser respetuoso con las opiniones, puntos de vista y experiencias diferentes

- Dar y aceptar con elegancia la retroalimentación constructiva

- Aceptar la responsabilidad y disculparse con quienes se ven afectados por nuestros errores, y aprender de la experiencia

- Centrarse en lo que es mejor no solo para nosotros como individuos, sino para la comunidad en su conjunto

Ejemplos de comportamiento inaceptable incluyen:

- El uso de lenguaje o imágenes sexualizadas, y la atención o insinuaciones sexuales de cualquier tipo

- El trolling, los comentarios insultantes o despectivos, y los ataques personales o políticos

- El acoso público o privado

- La publicación de información privada de otras personas, como una dirección física o de correo electrónico, sin su permiso explícito

- Otra conducta que razonablemente pueda considerarse inapropiada en un entorno profesional

#### Responsabilidades de aplicación

Los líderes de la comunidad son responsables de aclarar y hacer cumplir nuestros estándares de comportamiento aceptable, y tomarán medidas correctivas apropiadas y justas en respuesta a cualquier comportamiento que consideren inapropiado, amenazante, ofensivo o dañino.

Los líderes de la comunidad tienen el derecho y la responsabilidad de eliminar, editar o rechazar comentarios, commits, código, ediciones de wiki, issues y otras contribuciones que no se alineen con este Código de Conducta, y comunicarán las razones de las decisiones de moderación cuando sea apropiado.

#### Alcance

Este Código de Conducta se aplica en todos los espacios de la comunidad, y también se aplica cuando una persona representa oficialmente a la comunidad en espacios públicos. Ejemplos de representación de nuestra comunidad incluyen el uso de una dirección de correo electrónico oficial, publicar a través de una cuenta oficial de redes sociales, o actuar como representante designado en un evento en línea o presencial.

#### Aplicación

Los casos de comportamiento abusivo, acosador o de cualquier otra forma inaceptable pueden denunciarse a los líderes de la comunidad enumerados [aquí](https://github.com/Slicer/Slicer/blob/master/GOVERNANCE.md#benevolent-dictators-for-life) mediante un mensaje privado en el [foro de Slicer](https://discourse.slicer.org). Todas las quejas serán revisadas e investigadas de manera pronta y justa.

Todos los líderes de la comunidad están obligados a respetar la privacidad y la seguridad de quien denuncia cualquier incidente.

#### Atribución

Este Código de Conducta está adaptado del [Contributor Covenant](https://www.contributor-covenant.org), versión 2.1, disponible en <https://www.contributor-covenant.org/version/2/1/code_of_conduct.html>.

Las Directrices de Impacto en la Comunidad se inspiraron en la [escala de aplicación del código de conducta de Mozilla](https://github.com/mozilla/diversity).

Para respuestas a preguntas frecuentes sobre este código de conducta, consulte las preguntas frecuentes en <https://www.contributor-covenant.org/faq>. Hay traducciones disponibles en <https://www.contributor-covenant.org/translations>.

#### Modificaciones

Para conocer el historial de actualizaciones y revisiones de este documento, consulte <https://github.com/Slicer/Slicer/commits/main/CODE_OF_CONDUCT.md>.

### Proceso de toma de decisiones

1. Dado el tema de interés, inicie la discusión en el [foro de Slicer](https://discourse.slicer.org).

2. Identifique un pequeño círculo de miembros de la comunidad interesados en estudiar el tema con mayor profundidad.

3. Lleve la discusión fuera de la lista general, trabaje en el análisis de opciones y alternativas, y resuma los hallazgos en la wiki o algo similar. Las páginas de [Labs](https://www.slicer.org/wiki/Documentation/Labs) suelen ser un buen espacio para dicho resumen.

4. Anuncie en el [foro de Slicer](https://discourse.slicer.org) la discusión en profundidad del tema para el [hangout de la comunidad de Slicer](https://discourse.slicer.org/c/community/hangout), y anime a cualquier persona interesada en opinar sobre el tema a unirse a la discusión. Si hay alguien interesado en participar en la discusión pero no puede asistir a la reunión por un conflicto de horario, debe notificar a los líderes del proyecto correspondiente e identificar un horario adecuado para todos.

5. Con suerte, se alcanza el consenso en el hangout y se procede con el plan acordado.

*La versión inicial de estas directrices se estableció durante la [semana de proyectos de invierno de 2017](https://www.na-mic.org/Wiki/index.php/2017_Winter_Project_Week/UpdatingCommunityForums).*

### Dictadores benevolentes vitalicios

Los [dictadores benevolentes](#dictadores-benevolentes-vitalicios) pueden integrar cambios para mantener la salud de la plataforma y ayudar a interpretar o resolver conflictos relacionados con las directrices de contribución.

Actualmente incluyen a:

- Jean-Christophe Fillion-Robin

- Andras Lasso

- Steve Pieper

*Ordenados alfabéticamente por apellido.*

La comunidad de Slicer es inclusiva y da la bienvenida a cualquier persona que desee trabajar para convertirse en desarrollador principal y, luego, en BDFL (dictador benevolente vitalicio). Esto ocurre con mucho trabajo y la aprobación de los BDFL existentes.

## Contáctenos

Se recomienda publicar cualquier pregunta, informe de errores o solicitud de mejora en el [foro de Slicer](https://discourse.slicer.org).

Nuestro rastreador de problemas en línea está disponible [aquí](https://issues.slicer.org).

Para consultoría comercial/confidencial, contacte a uno de los [socios comerciales](#socios-comerciales).
