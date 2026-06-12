# Acerca de 3D Slicer

> Traducción al español (Latinoamérica) de [About 3D Slicer](https://slicer.readthedocs.io/en/latest/user_guide/about.html)

## ¿Qué es 3D Slicer?

- Una aplicación de software para la visualización y el análisis de conjuntos de datos de imágenes médicas computacionales. Se admiten todos los conjuntos de datos de uso común, como imágenes, segmentaciones, superficies, anotaciones, transformaciones, etc., en 2D, 3D y 4D. La visualización está disponible en computadoras de escritorio y en realidad virtual. El análisis incluye segmentación, registro y diversas cuantificaciones.

- Una plataforma de software de investigación, que permite a los investigadores desarrollar y evaluar rápidamente nuevos métodos y distribuirlos a usuarios clínicos. Todas las funciones están disponibles y son extensibles en Python y C++. Se proporciona un entorno completo de Python en el que se puede instalar cualquier paquete de Python y combinarlo con las funciones integradas. Slicer cuenta con una consola de Python integrada y puede funcionar como kernel de notebooks Jupyter con capacidades de renderizado 3D remoto.

- Una plataforma de desarrollo de productos, que permite a las empresas crear prototipos y lanzar productos rápidamente a los usuarios. Los desarrolladores pueden concentrarse en desarrollar nuevos métodos sin necesidad de dedicar tiempo a volver a programar funciones básicas de importación/exportación de datos, visualización e interacción. La aplicación está diseñada para ser altamente personalizable (con marca propia, interfaz de usuario simplificada, etc.). 3D Slicer es completamente gratuito y no existen restricciones sobre su uso; es responsabilidad del distribuidor del software garantizar que la aplicación desarrollada sea adecuada para el uso previsto.

**Nota:** No hay restricciones de uso, pero Slicer **NO** está aprobado para uso clínico y la aplicación distribuida está destinada a uso en investigación. Los permisos y el cumplimiento de las normas aplicables son responsabilidad del usuario. Para más detalles sobre la licencia, consulte [aquí](https://www.slicer.org/wiki/License).

Aspectos destacados:

- Software gratuito y de [código abierto](https://es.wikipedia.org/wiki/C%C3%B3digo_abierto), disponible en múltiples sistemas operativos: Linux, macOS y Windows.

- Multiórgano: de la cabeza a los pies.

- Compatibilidad con imágenes multimodales, incluyendo resonancia magnética (MRI), tomografía computarizada (CT), ultrasonido (US), medicina nuclear y microscopía.

- Interfaz en tiempo real para dispositivos médicos, como sistemas de navegación quirúrgica, sistemas de imágenes, dispositivos robóticos y sensores.

- Altamente extensible: los usuarios pueden agregar fácilmente más capacidades instalando módulos adicionales desde el administrador de extensiones (Extensions manager), ejecutando scripts de Python personalizados en la consola de Python integrada, ejecutando cualquier programa desde la interfaz de usuario de la aplicación, o implementando módulos personalizados en Python o C++.

- Una comunidad de usuarios grande y activa.

## Licencia

El software 3D Slicer se distribuye bajo una licencia de código abierto de estilo BSD que es ampliamente compatible con la Definición de Código Abierto de [The Open Source Initiative](https://opensource.org/) y no contiene restricciones sobre los usos legales del software.

Para usar Slicer, lea el [Acuerdo de Licencia de Software de 3D Slicer](https://github.com/Slicer/Slicer/blob/main/License.txt) antes de descargar cualquier versión binaria de Slicer.

### Notas históricas sobre la licencia

La Licencia de Slicer fue redactada en 2005 por abogados que trabajaban para el Brigham and Women's Hospital (BWH), un hospital afiliado a la enseñanza de la Escuela de Medicina de Harvard, con el objetivo de que fuera similar a la BSD pero con algunas disposiciones adicionales relacionadas con el software médico. Es específica para el BWH, por lo que no es directamente reutilizable, pero podría servir como plantilla para proyectos con objetivos similares.

Se redactó en parte porque el BWH era el contratista principal de un consorcio de desarrollo financiado por los NIH ([NA-MIC](https://www.na-mic.org/)) y quería que todas las contribuciones de código fueran compatibles con su uso final en productos médicos del mundo real (es decir, dispositivos médicos comerciales aprobados por la FDA, que son casi universalmente de código cerrado aunque se construyan sobre software abierto). El cumplimiento de la Licencia de Slicer era obligatorio para los subcontratistas, un grupo que incluía a GE Research, Kitware y varias universidades (MIT, UNC…), quienes revisaron y aceptaron esta licencia.

La licencia ha estado en uso continuo desde 2005 para el paquete de software 3D Slicer ([slicer.org](http://slicer.org)), que hasta 2021 se ha descargado más de un millón de veces y ha sido referenciado en aproximadamente 12,000 publicaciones académicas (<https://www.slicer.org/wiki/Main_Page/SlicerCommunity>). Parte del código también se utiliza actualmente en varios productos médicos para los cuales esta licencia ha sido revisada y aceptada por las empresas involucradas.

### Términos de la licencia y sus razones

Estos son algunos de los puntos clave que el BWH incluyó además de los términos BSD para adecuar la licencia al caso de un gran hospital que distribuye software médico de código abierto.

Para usar y redistribuir 3D Slicer:

- La licencia establece que el código está "diseñado para investigación" y que "LAS APLICACIONES CLÍNICAS NO SE RECOMIENDAN NI SE ACONSEJAN", para dejar muy en claro que cualquier uso clínico comercial del código es responsabilidad exclusiva del usuario y no del BWH ni de los demás desarrolladores. Esto es un descargo de responsabilidad, no una restricción legal.

Para realizar cambios o agregar cualquier código fuente o datos a 3D Slicer:

- Los contribuyentes otorgan explícitamente derechos libres de regalías si aportan código cubierto por una patente que controlan (es decir, para evitar "patentes submarinas").

- No se permite código GPL ni otro código con copyleft, porque eso podría hacer complicado y riesgoso mezclar el código de Slicer con propiedad intelectual privada, que suele estar presente en productos médicos regulados.

- Los contribuyentes afirman que han anonimizado (desidentificado) cualquier dato de pacientes que aporten, para evitar problemas con la HIPAA o regulaciones relacionadas.

### Estado en comparación con otras licencias de código abierto

Hasta junio de 2021, la Licencia de Slicer se ha utilizado durante más de 15 años sin incidentes. En mayo de 2021, un usuario del foro Discourse [sugirió](https://discourse.slicer.org/t/apply-for-osi-open-source-license-status/17791) someter la licencia al [proceso de revisión de licencias de la OSI](https://opensource.org/approval). Tras cierta discusión y al no haber objeciones, el liderazgo de la comunidad decidió [enviar la licencia para su revisión](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/2021-May/thread.html). Aunque el proceso de la OSI no es legalmente vinculante, la discusión podría dar a los usuarios potenciales de Slicer una perspectiva sobre cómo se comparan las disposiciones de la licencia con otras licencias de uso común.

La discusión concluyó que incluir el acuerdo de contribución dentro de la licencia hace que no pueda ser aprobada por la OSI, y que el requisito de usar el software para fines legales podría no ser consistente con la [Definición de Código Abierto](https://opensource.org/osd). Por lo demás, los términos de la licencia no parecen ser controvertidos. Las partes interesadas deben revisar la [discusión completa](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/2021-June/thread.html#5166) para conocer los detalles.

## Cómo citar

### 3D Slicer como plataforma

Para reconocer a 3D Slicer como plataforma, cite el [sitio web de Slicer](https://www.slicer.org/) y las siguientes publicaciones al publicar trabajos que usen o incorporen 3D Slicer:

**Fedorov A., Beichel R., Kalpathy-Cramer J., Finet J., Fillion-Robin J-C., Pujol S., Bauer C., Jennings D., Fennessy F.M., Sonka M., Buatti J., Aylward S.R., Miller J.V., Pieper S., Kikinis R. [3D Slicer as an Image Computing Platform for the Quantitative Imaging Network](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3466397/pdf/nihms383480.pdf). Magnetic Resonance Imaging. 2012 Nov;30(9):1323-41. PMID: 22770690. PMCID: PMC3466397.**

## El nombre y el logotipo de 3D Slicer

3D Slicer y su logotipo son marcas registradas del Brigham and Women's Hospital (BWH) y no pueden utilizarse sin permiso. Dicho permiso se concede ampliamente para usos académicos o comerciales, como documentar el uso de Slicer en su proyecto o promover su uso por parte de otros. Utilice los colores originales del logotipo de Slicer y no altere su forma ni su texto. No está permitido usar Slicer para dar a entender que el BWH o la comunidad de Slicer respaldan su producto o proyecto sin contar con autorización. Para otros usos, contacte a Ron Kikinis ([kikinis@bwh.harvard.edu](mailto:kikinis@bwh.harvard.edu)) y Steve Pieper ([pieper@bwh.harvard.edu](mailto:pieper@bwh.harvard.edu)).

### Módulos individuales

Para reconocer módulos individuales: cada módulo tiene una pestaña de agradecimientos (acknowledgment) en la sección superior. Allí se puede encontrar información sobre los contribuyentes y las fuentes de financiamiento:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/acknowledgement_ack_tab.png)

Generalmente se puede encontrar información adicional (incluida información sobre las publicaciones relacionadas) en las páginas del manual, accesibles a través de la pestaña de ayuda (help) en la sección superior:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/acknowledgement_help_tab.png)

## Agradecimientos

Slicer es posible gracias a las contribuciones de una comunidad internacional de científicos de múltiples disciplinas, incluidas la ingeniería y la biomedicina. Las siguientes secciones dan crédito a algunos de los principales contribuyentes al esfuerzo central de 3D Slicer. Cada extensión de 3D Slicer tiene una página de agradecimientos independiente con información específica de esa extensión.

El apoyo continuo a Slicer depende de USTED

Por favor, dele una estrella al repositorio de Slicer en GitHub. Es una forma sencilla de mostrar agradecimiento y puede ayudarnos a calificar para servicios útiles que solo están disponibles para proyectos abiertos ampliamente reconocidos.
No olvide citar nuestras publicaciones, ya que eso nos ayuda a obtener nuevo financiamiento mediante subvenciones.
Si encuentra que Slicer le resulta útil, como a la comunidad, ¡involúcrese! ¡No es necesario ser programador para ayudar!

### Contribuyentes principales

- Ron Kikinis: Investigador Principal

- Steve Pieper: Arquitecto en Jefe

- Jean-Christophe Fillion-Robin: Desarrollador Líder

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

*Los contribuyentes no son solo desarrolladores, sino también personas que ayudan a conseguir financiamiento y a hacer avanzar la plataforma.*

### Grupos que contribuyen de manera significativa a la ingeniería central de Slicer

- SPL: Ron Kikinis, Nicole Aucoin, Lauren O'Donnell, Andrey Fedorov, Isaiah Norton, Sonia Pujol, Noby Hata, Junichi Tokuda

- Isomics: Steve Pieper, Alex Yarmarkovich

- Kitware: Jean-Christophe Fillion-Robin, Julien Finet, Will Schroeder, Stephen Aylward, Andinet Enquobahrie, Beatriz Paniagua, Matt McCormick, Johan Andruejol, Max Smolens, Alexis Girault, Sam Horvath

- Universidad de Iowa: Hans Johnson

- GE: Jim Miller

- Perk Lab, Universidad de Queen's: Andras Lasso, Tamas Ungi, Csaba Pinter, Gabor Fichtinger

- Instituto Astronómico Kapteyn, Universidad de Groninga: Davide Punzo

### Fuentes de financiamiento

Muchas de las actividades en torno al esfuerzo de Slicer son posibles gracias al financiamiento de fuentes públicas y privadas. Los Institutos Nacionales de Salud (NIH) de los EE. UU. son un contribuyente importante a través de una variedad de subvenciones y contratos competitivos. Las fuentes de financiamiento que contribuyen al desarrollo del núcleo de Slicer o de sus extensiones incluyen (ordenadas por fecha de finalización):

*Nota: los títulos oficiales de las subvenciones se conservan en su idioma original.*

| Número de subvención | Descripción | Investigadores principales | Fecha de inicio | Fecha de fin | Título |
| --- | --- | --- | --- | --- | --- |
| CHOP | Programa Frontier de CHOP | Matthew Jolley | 2024-07-01 | a la fecha | Children's Hospital of Philadelphia Frontier Programs conduct visionary research that translates to cutting-edge care |
| NSF/DBI 2301405 | MorphoCloud y MorphoDepot | Murat Maga | 2024-03-01 | 2028-02-28 | MorphoCloud: A Cloud Powered, Open-Source Platform For Research, Teaching And Collaboration In 3d Digital Morphology And Beyond |
| NSF/OAC 2118240 | Extensión de fotogrametría | Murat Maga | 2021-09-15 | 2026-08-31 | Imageomics: A New Frontier of Biological Information Powered by Knowledge-Guided Machine Learning |
| AV 993932 | SlicerHeart para ventrículo único | Matthew Jolley | 2023-03-01 | 2026-02-28 | Computational Modelling of the Atrioventricular Valve Repair Single Ventricle Patients with Atrioventricular Canal |
| NIH P01HD104435 | Segmentaciones multiorgánicas de embriones de ratón (MEMOS), extensión ANTsPy, terminologías | Murat Maga | 2021-01-11 | 2025-12-31 | 3D Quantitative Analysis of Mouse Models of Structural Birth Defects Through Computational Anatomy |
| [NIH 1R01HL153166-01](https://projectreporter.nih.gov/project_info_description.cfm?aid=10029738&icde=51006191) | Modelado computacional de la válvula tricúspide en SCIH | Matthew Jolley | 2021-06-30 | 2025-06-30 | Computer Modeling of the Tricuspid Valve in Hypoplastic Left Heart Syndrome |
| NIH R03OD032627 | Kit de herramientas de análisis de correspondencia densa (DeCA) | Murat Maga | 2021-09-22 | 2023-09-21 | Deep Phenotyping of 3D Data for Candidate Gene Selection from Kids First Studies |
| [CZI EOSS 4](https://chanzuckerberg.com/eoss/proposals/3d-slicer-in-my-language-internationalization-and-usability-improvements/) | Internacionalización y usabilidad de Slicer | Pujol, Sonia | 2021-09-01 | 2023-09-01 | 3D Slicer in My Language: Internationalization and Usability Improvements |
| [NIH 4P41EB015902](https://projectreporter.nih.gov/project_info_description.cfm?aid=9115586&icde=31485398) | Centro de Análisis de Neuroimágenes | Ron Kikinis | 2013-08-01 | 2023-08-31 | Application of Slicer to image-guided neurosurgery and other applications through steered computation and image navigation databases |
| CANARIE RS3-036 | SlicerAIGT | Fichtinger, Gabor | 2020-10-01 | 2023-03-31 | Develop free open source research software for AI-powered image guided therapy on Slicer platform |
| [NIH R01MH112748](https://reporter.nih.gov/search/-oPV-FDakki3bPslkjMUwg/project-details/10053340) | Herramientas de segmentación cerebral de alta precisión | Bouix, Sylvain | 2017-12-01 | 2022-10-31 | High Resolution, Comprehensive Atlases of the Human Brain Morphology |
| NSF/DBI 1759883 | Extensión SlicerMorph, infraestructura de Markups | Murat Maga | 2018-08-01 | 2022-07-31 | An Integrated Platform for Retrieval, Visualization and Analysis of 3D Morphology From Digital Biological Collections |
| [NIH R44DK115332](https://www.sbir.gov/sbirsearch/detail/1683213) | Biopsia renal | Enquobahrie, Andinet A. | 2019-08-13 | 2021-07-31 | Advanced virtual simulator for real-time ultrasound-guided renal biopsy training |
| ICEX 0202101723 | Colaboración SlicerVR | Juan Ruiz Alzola | 2021-01-16 | 2021-12-31 | Sistema Virtual Colaborativa Aplicación Médicas |
| [NIH R01EB025212](https://govtribe.com/award/federal-grant-award/project-grant-r01eb025212) | Anotación de software | Enquobahrie, Andinet A. | 2019-07-02 | 2021-03-31 | Software for Practical Annotation and Exchange of Virtual Anatomy |
| CANARIE RS319 | SlicerIGT | Fichtinger, Gabor | 2019-10-01 | 2020-09-30 | Canadian Research Software Infrastructure |
| CANARIE RS214 | SlicerRT | Fichtinger, Gabor | 2017-07-01 | 2020-09-30 | Canadian Research Software Infrastructure |
| CHOP | SlicerHeart | Matthew Jolley | 2015-08-15 | 2020-08-15 | Pediatric cardiac valve modeling, Children Hospital of Philadelphia |
| [MAC/1.1b/098](https://mt4sd.ulpgc.es/en/macbioidi-project/) | MACBIOLDI | Juan Ruiz Alzola | 2017-01-01 | 2020-09-30 | Medical Technology for Sustainable Development (MedTec4SusDev) |
| [NIH 2P41EB015898](https://projectreporter.nih.gov/project_info_details.cfm?aid=8855115&icde=27026518) | DiffusionMRI | Tempany, Clare M | 2004-04-01 | 2020-06-30 | Image Guided Therapy Center |
| [NIH 5P41EB015898](https://projectreporter.nih.gov/project_info_description.cfm?aid=9125821&icde=31485478) | Centro Nacional de Terapia Guiada por Imágenes | Clare Tempany | 2004-04-01 | 2020-06-30 | Use of Slicer in a wide array of image-guided therapy research for prostate cancer, neurosurgery, and image navigation |
| [NIH 1R01EB021391](https://projectreporter.nih.gov/project_info_description.cfm?aid=9123966&icde=31459429) | Shape | Paniagua, Beatriz | 2016-09-19 | 2020-06-30 | SHAPE ANALYSIS TOOLBOX FOR MEDICAL IMAGE COMPUTING PROJECTS |
| [NIH U24CA194354](https://projectreporter.nih.gov/project_info_description.cfm?aid=8875289&icde=27050248) | Slicer-Radiomics-U24 | Aerts, Hugo | 2015-04-01 | 2020-03-31 | Quantitative Radiomics System Decoding the Tumor Phenotype |
| [NIH 1U01CA190234](https://projectreporter.nih.gov/project_info_description.cfm?aid=8799943&icde=27026470) | Slicer-Radiomics-U01 | Aerts, Hugo | 2015-01-01 | 2019-12-01 | Genotype And Imaging Phenotype Biomarkers In Lung Cancer |
| [NIH 5U24CA180924](https://projectreporter.nih.gov/project_info_details.cfm?aid=9127923&icde=31460433) | Análisis de datos moleculares mapeados espacialmente | Joel Saltz | 2014-09-01 | 2019-08-31 | Tools to Analyze Morphology and Spatially Mapped Molecular Data |
| [NIH 5R01CA184354](https://projectreporter.nih.gov/project_info_description.cfm?aid=8828624&icde=27036841) | NIRFAST (Dartmouth) | Davis, Scott C. | 2014-04-01 | 2019-02-28 | Mri Fluorescence Tomography For Quantifying Tumor Receptor Concentration In Vivo |
| [NIH R43DE027595](https://projectreporter.nih.gov/project_info_description.cfm?aid=9465772&icde=36620728) | VROrthognathic | Paniagua, Beatriz | 2017-09-07 | 2018-09-06 | High-Fidelity Virtual Reality Trainer for Orthognathic Surgery |
| [NIH 1R21DE025306](https://projectreporter.nih.gov/project_info_description.cfm?aid=9111256&icde=31459429) | CMF | Paniagua, Beatriz | 2016-09-01 | 2018-08-31 | TEXTURAL BIOMARKERS OF ARTHRITIS FOR THE SUBCHONDRAL BONE IN THE TEMPOROMANDIBULAR JOINT |
| [NIH 1U01NS082086](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462842&icde=27164806) | HD_SHAPEANALSS | Gerig, Guido | 2012-09-28 | 2018-08-31 | 4D Shape Analysis for Modeling Spatiotemporal Change Trajectories in Huntington's |
| [NIH U24 CA180918](https://projectreporter.nih.gov/project_info_description.cfm?aid=8911287&icde=27026906) | [QIICR](https://qiicr.org) | Ron Kikinis, Andrey Fedorov | 2013-09-04 | 2018-08-31 | Quantitative Image Informatics for Cancer Research (QIICR) |
| [NIH 5R01NS055903](https://projectreporter.nih.gov/project_info_description.cfm?aid=8900362&icde=27164764) | HD_KIDS | Nopoulos, Peggy | 2009-03-01 | 2018-07-31 | Growth and Development of the Striatum in Huntington's Disease |
| [NIH 1U01CA199459](https://projectreporter.nih.gov/project_info_description.cfm?aid=8971083&icde=27026834) | SlicerDMRI - Resonancia magnética de difusión | O'Donnell, Lauren Jean | 2015-09-22 | 2018-07-31 | Open Source Diffusion MRI Technology For Brain Cancer Research |
| [NIH 5R01EB020667-02](https://projectreporter.nih.gov/project_info_description.cfm?aid=9100712&icde=34329960) | OpenIGTLink | Tokuda, Junichi | 2015-07-01 | 2018-06-30 | OpenIGTLink: A Network Communication Interface for Closed-Loop Image-Guided Interventions |
| [NIH 5P41EB015902](https://projectreporter.nih.gov/project_info_description.cfm?aid=8890837&icde=27036647) | DiffusionMRI | Kikinis, Ron | 2013-08-01 | 2018-05-31 | Neuroimaging Analysis Center (Nac) |
| [NIH 2R42HD081712](https://projectreporter.nih.gov/project_info_description.cfm?aid=9141675&icde=31459353) | Craneosinostosis | Linguraru, Marius George | 2016-05-01 | 2018-04-30 | IMAGE-GUIDED PLANNING SYSTEM FOR SKULL CORRECTION IN CHILDREN WITH CRANIOSYNOSTOSIS: PHASE II |
| [NIH R01CA160902](https://projectreporter.nih.gov/project_info_description.cfm?aid=8817256&icde=27036729) | DWI | Maier, Stephan E | 2012-04-01 | 2018-02-28 | Advancement And Validation Of Prostate Diffusion And Spectroscopic Mri |
| [NIH 1R01DE024450](https://projectreporter.nih.gov/project_info_description.cfm?aid=8576556&icde=18353487) | CMF | Cevidanes, Lucia | 2013-09-10 | 2017-08-31 | Quantification Of 3D Bony Changes In Temporomandibular Joint Osteoarthritis |
| [NIH 2R42CA167907](https://projectreporter.nih.gov/project_info_description.cfm?aid=8979242&icde=27036988) | Fantoma de calibración PET/CT | Kinahan, Paul E | 2012-05-01 | 2017-07-31 | Calibrated Methods For Quantitative Pet/Ct Imaging Phase Ii |
| [NIH R42CA167907](https://projectreporter.nih.gov/project_info_description.cfm?aid=8979242&icde=27036988) | Fantoma de calibración PET/CT | Kinahan, Paul E. | 2012-05-01 | 2017-07-01 | Calibrated Methods For Quantitative Pet/Ct Imaging Phase Ii |
| NA | HD_TRACKON | Tabrizi, Sarah | 2012-01-01 | 2016-12-31 | TRACK-ON HD |
| CCO ACRU | SlicerRT | Fichtinger, Gabor | 2011-01-01 | 2016-12-31 | Cancer Care Ontario Applied Cancer Research Unit, Canadá |
| CCO OCAIRO | SlicerRT | Jaffray, David | 2011-01-01 | 2016-12-31 | Ontario Consortium for Adaptive Interventions in Radiation Oncology, Canadá |
| NA | HD_TRAJECTORY | Kim, Eun Young | 2014-11-01 | 2016-10-31 | Developing a Robust Segmentation Pipeline That Allows for Consistent Trajectory Estimation of HD Gene Positive Individuals Across Multiple Longitudinal MRI Sites |
| [NIH 1R41HD081712](https://projectreporter.nih.gov/project_info_description.cfm?aid=8778815&icde=27036063) | Craneosinostosis | Linguraru, Marius George | 2014-09-26 | 2016-08-31 | Image-Guided Planning System For Skull Correction In Children With Craniosynostos |
| [NIH 5R01NS040068](https://projectreporter.nih.gov/project_info_description.cfm?aid=8338456&icde=27164778) | HD_PREDICT | Paulsen, Jane | 2000-08-01 | 2016-08-31 | Neurobiological Predictors of Huntington's Disease (PREDICT-HD) |
| [NIH 3R42CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=8863934&icde=27037113) | Biopsia con aguja guiada por PET-CT | Cleary, Kevin R. | 2012