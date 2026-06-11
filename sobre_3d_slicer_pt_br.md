# Sobre o 3D Slicer

## O que é o 3D Slicer?

- Um aplicativo de software para visualização e análise de conjuntos de dados de computação de imagens médicas. Todos os tipos de dados comumente usados são suportados, como imagens, segmentações, superfícies, anotações, transformações etc., em 2D, 3D e 4D. A visualização está disponível no desktop e em realidade virtual. A análise inclui segmentação, registro e diversas quantificações.

- Uma plataforma de software de pesquisa, que permite que pesquisadores desenvolvam e avaliem rapidamente novos métodos e os distribuam a usuários clínicos. Todos os recursos estão disponíveis e são extensíveis em Python e C++. Um ambiente Python completo é fornecido, no qual qualquer pacote Python pode ser instalado e combinado com os recursos integrados. O Slicer possui um console Python integrado e pode atuar como kernel de notebooks Jupyter com recursos de renderização 3D remota.

- Uma plataforma de desenvolvimento de produtos, que permite que empresas prototipem e lancem produtos rapidamente para os usuários. Os desenvolvedores podem se concentrar no desenvolvimento de novos métodos e não precisam gastar tempo redesenvolvendo recursos básicos de importação/exportação de dados, visualização e interação. O aplicativo foi projetado para ser altamente personalizável (com marca própria, interface de usuário simplificada etc.). O 3D Slicer é totalmente gratuito e não há restrições sobre como ele é usado — cabe ao distribuidor do software garantir que o aplicativo desenvolvido seja adequado ao uso pretendido.

**Observação:** Não há restrição de uso, mas o Slicer **NÃO** é aprovado para uso clínico e o aplicativo distribuído destina-se ao uso em pesquisa. As permissões e a conformidade com as normas aplicáveis são de responsabilidade do usuário. Para detalhes sobre a licença, consulte [aqui](https://www.slicer.org/wiki/License).

Destaques:

- Software gratuito e de [código aberto](https://en.wikipedia.org/wiki/Open_source) disponível em vários sistemas operacionais: Linux, macOS e Windows.

- Multiórgão: da cabeça aos pés.

- Suporte a imagens multimodalidade, incluindo ressonância magnética (RM), tomografia computadorizada (TC), ultrassom (US), medicina nuclear e microscopia.

- Interface em tempo real para dispositivos médicos, como sistemas de navegação cirúrgica, sistemas de imagem, dispositivos robóticos e sensores.

- Altamente extensível: os usuários podem facilmente adicionar mais recursos instalando módulos adicionais pelo Gerenciador de extensões, executando scripts Python personalizados no console Python integrado, executando qualquer programa executável a partir da interface do aplicativo ou implementando módulos personalizados em Python ou C++.

- Comunidade de usuários grande e ativa.

## Licença

O software 3D Slicer é distribuído sob uma licença de código aberto de estilo BSD, amplamente compatível com a Definição de Código Aberto da [The Open Source Initiative](https://opensource.org/), e não contém restrições sobre os usos legais do software.

Para usar o Slicer, leia o [Contrato de Licença de Software do 3D Slicer](https://github.com/Slicer/Slicer/blob/main/License.txt) antes de baixar qualquer versão binária do Slicer.

### Notas históricas sobre a licença

A Licença do Slicer foi redigida em 2005 por advogados que trabalhavam para o Brigham and Women's Hospital (BWH), um hospital de ensino afiliado à Faculdade de Medicina de Harvard, para ser semelhante à BSD, mas com algumas disposições adicionais relacionadas a software médico. Ela é específica do BWH, portanto não é diretamente reutilizável, mas pode servir como modelo para projetos com objetivos semelhantes.

Ela foi escrita em parte porque o BWH era o contratante principal de um consórcio de desenvolvimento financiado pelos NIH ([NA-MIC](https://www.na-mic.org/)) e queria que todas as contribuições de código fossem compatíveis com o uso final em produtos médicos do mundo real (ou seja, dispositivos médicos comerciais aprovados pela FDA, que são quase universalmente de código fechado, mesmo quando se baseiam em software aberto). A conformidade com a Licença do Slicer era exigida dos subcontratados, um grupo que incluía a GE Research, a Kitware e várias universidades (MIT, UNC…), que revisaram e aceitaram essa licença.

A licença está em uso contínuo desde 2005 para o pacote de software 3D Slicer ([slicer.org](http://slicer.org)) que, até 2021, havia sido baixado mais de um milhão de vezes e citado em cerca de 12.000 publicações acadêmicas (<https://www.slicer.org/wiki/Main_Page/SlicerCommunity>). Parte do código também está sendo usada atualmente em vários produtos médicos para os quais essa licença foi revisada e aceita pelas empresas envolvidas.

### Termos da licença e seus motivos

Estes são alguns dos pontos principais que o BWH incluiu além dos termos BSD para adequar a licença ao caso de um grande hospital que distribui software médico de código aberto.

Para usar e redistribuir o 3D Slicer:

- A licença declara que o código é "projetado para pesquisa" e que "APLICAÇÕES CLÍNICAS NÃO SÃO RECOMENDADAS NEM ACONSELHADAS", para deixar bem claro que quaisquer usos clínicos comerciais do código são de responsabilidade exclusiva do usuário, e não do BWH ou dos demais desenvolvedores. Trata-se de um aviso de isenção de responsabilidade, e não de uma restrição legal.

Para fazer alterações ou adicionar qualquer código-fonte ou dado ao 3D Slicer:

- Os colaboradores concedem explicitamente direitos isentos de royalties caso contribuam com código coberto por uma patente que controlem (ou seja, para evitar patentes ocultas ou "submarinas").

- Não é permitido código GPL ou outro código copyleft, porque isso poderia tornar complicado e arriscado misturar o código do Slicer com propriedade intelectual privada, frequentemente presente em produtos médicos regulamentados.

- Os colaboradores afirmam que anonimizaram quaisquer dados de pacientes que contribuam, para evitar problemas com a HIPAA ou regulamentações relacionadas.

### Situação em comparação com outras licenças de código aberto

Em junho de 2021, a Licença do Slicer já havia sido usada por mais de 15 anos sem incidentes. Em maio de 2021, um usuário do fórum Discourse [sugeriu](https://discourse.slicer.org/t/apply-for-osi-open-source-license-status/17791) submeter a licença ao [processo de revisão de licenças da OSI](https://opensource.org/approval). Após alguma discussão e sem objeções, a liderança da comunidade decidiu [submeter a licença para revisão](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/2021-May/thread.html). Embora o processo da OSI não seja juridicamente vinculante, a discussão poderia dar aos potenciais usuários do Slicer uma perspectiva sobre como as disposições da licença se comparam a outras licenças de uso comum.
A discussão concluiu que incluir o acordo de contribuição dentro da licença a torna não aprovável pela OSI, e que a exigência de usar o software para fins legais pode não ser consistente com a [Definição de Código Aberto](https://opensource.org/osd). Fora isso, os termos da licença não parecem ser controversos. As partes interessadas devem consultar a [discussão completa](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/2021-June/thread.html#5166) para mais detalhes.

## Como citar

### O 3D Slicer como plataforma

Para reconhecer o 3D Slicer como plataforma, cite o [site do Slicer](https://www.slicer.org/) e as seguintes publicações ao publicar trabalhos que usem ou incorporem o 3D Slicer:

**Fedorov A., Beichel R., Kalpathy-Cramer J., Finet J., Fillion-Robin J-C., Pujol S., Bauer C., Jennings D., Fennessy F.M., Sonka M., Buatti J., Aylward S.R., Miller J.V., Pieper S., Kikinis R. [3D Slicer as an Image Computing Platform for the Quantitative Imaging Network](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3466397/pdf/nihms383480.pdf). Magnetic Resonance Imaging. 2012 Nov;30(9):1323-41. PMID: 22770690. PMCID: PMC3466397.**

## O nome e o logotipo do 3D Slicer

3D Slicer e o logotipo são marcas registradas do Brigham and Women's Hospital (BWH) e não podem ser usados sem permissão. Essa permissão é amplamente concedida para usos acadêmicos ou comerciais, como documentar o uso do Slicer em seu projeto ou promover o uso do Slicer por outras pessoas. Use as cores originais do logotipo do Slicer e não altere sua forma nem seu texto. Não é permitido usar o Slicer para sugerir que o BWH ou a comunidade do Slicer endossam seu produto ou projeto sem autorização. Para outros usos, entre em contato com Ron Kikinis ([kikinis@bwh.harvard.edu](mailto:kikinis%40bwh.harvard.edu)) e Steve Pieper ([pieper@bwh.harvard.edu](mailto:pieper%40bwh.harvard.edu)).

### Módulos individuais

Para reconhecer módulos individuais: cada módulo possui uma aba de agradecimentos na seção superior. Lá podem ser encontradas informações sobre os colaboradores e a fonte de financiamento:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/acknowledgement_ack_tab.png)

Informações adicionais (incluindo informações sobre as publicações relacionadas) geralmente podem ser encontradas nas páginas do manual, acessíveis pela aba de ajuda na seção superior:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/acknowledgement_help_tab.png)

## Agradecimentos

O Slicer é possível graças às contribuições de uma comunidade internacional de cientistas de inúmeras áreas, incluindo engenharia e biomedicina. As seções a seguir dão crédito a alguns dos principais colaboradores do esforço central do 3D Slicer. Cada extensão do 3D Slicer tem uma página de agradecimentos separada, com informações específicas daquela extensão.

O suporte contínuo ao Slicer depende de VOCÊ.

Dê uma estrela ao repositório do Slicer no GitHub. É uma forma fácil de agradecer e pode nos ajudar a nos qualificarmos para serviços úteis que estão disponíveis apenas para projetos abertos amplamente reconhecidos.
Não se esqueça de citar nossas publicações, pois isso nos ajuda a obter novos financiamentos.
Se o Slicer é útil para você, como é para a comunidade, participe. Você não precisa ser programador para ajudar!

### Principais colaboradores

- Ron Kikinis: Pesquisador principal

- Steve Pieper: Arquiteto-chefe

- Jean-Christophe Fillion-Robin: Desenvolvedor líder

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

- Sonia Pujol: Diretora de Treinamento

- Junichi Tokuda

- Lauren O'Donnell

- Andinet Enquobahrie

- Beatriz Paniagua

*Os colaboradores não são apenas desenvolvedores, mas também pessoas que ajudam a garantir financiamento e a impulsionar a plataforma.*

### Grupos que contribuem de forma significativa para a engenharia central do Slicer

- SPL: Ron Kikinis, Nicole Aucoin, Lauren O'Donnell, Andrey Fedorov, Isaiah Norton, Sonia Pujol, Noby Hata, Junichi Tokuda

- Isomics: Steve Pieper, Alex Yarmarkovich

- Kitware: Jean-Christophe Fillion-Robin, Julien Finet, Will Schroeder, Stephen Aylward, Andinet Enquobahrie, Beatriz Paniagua, Matt McCormick, Johan Andruejol, Max Smolens, Alexis Girault, Sam Horvath

- Universidade de Iowa: Hans Johnson

- GE: Jim Miller

- Perk Lab, Queen's University: Andras Lasso, Tamas Ungi, Csaba Pinter, Gabor Fichtinger

- Instituto Astronômico Kapteyn, Universidade de Groningen: Davide Punzo

### Fontes de financiamento

Muitas das atividades em torno do esforço do Slicer são possíveis graças ao financiamento de fontes públicas e privadas. Os Institutos Nacionais de Saúde dos EUA (NIH) são um contribuinte importante por meio de uma variedade de subvenções e contratos competitivos. As fontes de financiamento que contribuem para o desenvolvimento do núcleo do Slicer ou de extensões incluem (ordenadas por data de término):

| Número da subvenção | Descrição | Pesquisadores principais (PIs) | Data de início | Data de término | Título |
| --- | --- | --- | --- | --- | --- |
| CHOP | Programa Frontier do CHOP | Matthew Jolley | 2024-07-01 | até o momento | Os Programas Frontier do Children's Hospital of Philadelphia conduzem pesquisas visionárias que se traduzem em cuidados de ponta |
| NSF/DBI 2301405 | MorphoCloud e MorphoDepot | Murat Maga | 2024-03-01 | 2028-02-28 | MorphoCloud: uma plataforma de código aberto baseada em nuvem para pesquisa, ensino e colaboração em morfologia digital 3D e além |
| NSF/OAC 2118240 | Extensão de fotogrametria | Murat Maga | 2021-09-15 | 2026-08-31 | Imageomics: uma nova fronteira de informação biológica impulsionada por aprendizado de máquina guiado por conhecimento |
| AV 993932 | SlicerHeart para ventrículo único | Matthew Jolley | 2023-03-01 | 2026-02-28 | Modelagem computacional do reparo da valva atrioventricular em pacientes com ventrículo único e canal atrioventricular |
| NIH P01HD104435 | Segmentações multiórgão de embriões de camundongo (MEMOS), extensão ANTsPy, terminologias | Murat Maga | 2021-01-11 | 2025-12-31 | Análise quantitativa 3D de modelos murinos de defeitos congênitos estruturais por meio de anatomia computacional |
| [NIH 1R01HL153166-01](https://projectreporter.nih.gov/project_info_description.cfm?aid=10029738&icde=51006191) | Modelagem computacional da valva tricúspide na HLHS | Matthew Jolley | 2021-06-30 | 2025-06-30 | Modelagem computacional da valva tricúspide na síndrome do coração esquerdo hipoplásico |
| NIH R03OD032627 | Kit de ferramentas de análise de correspondência densa (DeCA) | Murat Maga | 2021-09-22 | 2023-09-21 | Fenotipagem profunda de dados 3D para seleção de genes candidatos a partir dos estudos Kids First |
| [CZI EOSS 4](https://chanzuckerberg.com/eoss/proposals/3d-slicer-in-my-language-internationalization-and-usability-improvements/) | Internacionalização e usabilidade do Slicer | Pujol, Sonia | 2021-09-01 | 2023-09-01 | 3D Slicer no meu idioma: melhorias de internacionalização e usabilidade |
| [NIH 4P41EB015902](https://projectreporter.nih.gov/project_info_description.cfm?aid=9115586&icde=31485398&ddparam=&ddvalue=&ddsub=&cr=3&csb=default&cs=ASC) | Centro de Análise de Neuroimagem | Ron Kikinis | 2013-08-01 | 2023-08-31 | Aplicação do Slicer à neurocirurgia guiada por imagem e outras aplicações por meio de computação direcionada e bancos de dados de navegação por imagem |
| CANARIE RS3-036 | SlicerAIGT | Fichtinger, Gabor | 2020-10-01 | 2023-03-31 | Desenvolver software de pesquisa gratuito e de código aberto para terapia guiada por imagem com IA na plataforma Slicer |
| [NIH R01MH112748](https://reporter.nih.gov/search/-oPV-FDakki3bPslkjMUwg/project-details/10053340) | Ferramentas de segmentação cerebral de alta precisão | Bouix, Sylvain | 2017-12-01 | 2022-10-31 | Atlas abrangentes e de alta resolução da morfologia do cérebro humano |
| NSF/DBI 1759883 | Extensão SlicerMorph, infraestrutura de Markups | Murat Maga | 2018-08-01 | 2022-07-31 | Uma plataforma integrada para recuperação, visualização e análise de morfologia 3D a partir de coleções biológicas digitais |
| [NIH R44DK115332](https://www.sbir.gov/sbirsearch/detail/1683213) | Biópsia renal | Enquobahrie, Andinet A. | 2019-08-13 | 2021-07-31 | Simulador virtual avançado para treinamento de biópsia renal guiada por ultrassom em tempo real |
| ICEX 0202101723 | Colaboração SlicerVR | Juan Ruiz Alzola | 2021-01-16 | 2021-12-31 | Sistema Virtual Colaborativo de Aplicações Médicas |
| [NIH R01EB025212](https://govtribe.com/award/federal-grant-award/project-grant-r01eb025212) | Anotação de software | Enquobahrie, Andinet A. | 2019-07-02 | 2021-03-31 | Software para anotação e troca práticas de anatomia virtual |
| CANARIE RS319 | SlicerIGT | Fichtinger, Gabor | 2019-10-01 | 2020-09-30 | Infraestrutura canadense de software de pesquisa |
| CANARIE RS214 | SlicerRT | Fichtinger, Gabor | 2017-07-01 | 2020-09-30 | Infraestrutura canadense de software de pesquisa |
| CHOP | SlicerHeart | Matthew Jolley | 2015-08-15 | 2020-08-15 | Modelagem de valvas cardíacas pediátricas, Children's Hospital of Philadelphia |
| [MAC/1.1b/098](https://mt4sd.ulpgc.es/en/macbioidi-project/) | MACBIOLDI | Juan Ruiz Alzola | 2017-01-01 | 2020-09-30 | Tecnologia médica para o desenvolvimento sustentável (MedTec4SusDev) |
| [NIH 2P41EB015898](https://projectreporter.nih.gov/project_info_details.cfm?aid=8855115&icde=27026518) | DiffusionMRI | Tempany, Clare M | 2004-04-01 | 2020-06-30 | Centro de Terapia Guiada por Imagem |
| [NIH 5P41EB015898](https://projectreporter.nih.gov/project_info_description.cfm?aid=9125821&icde=31485478&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC) | Centro Nacional de Terapia Guiada por Imagem | Clare Tempany | 2004-04-01 | 2020-06-30 | Uso do Slicer em uma ampla gama de pesquisas de terapia guiada por imagem para câncer de próstata, neurocirurgia e navegação por imagem |
| [NIH 1R01EB021391](https://projectreporter.nih.gov/project_info_description.cfm?aid=9123966&icde=31459429&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC) | Shape | Paniagua, Beatriz | 2016-09-19 | 2020-06-30 | Caixa de ferramentas de análise de forma para projetos de computação de imagens médicas |
| [NIH U24CA194354](https://projectreporter.nih.gov/project_info_description.cfm?aid=8875289&icde=27050248) | Slicer-Radiomics-U24 | Aerts, Hugo | 2015-04-01 | 2020-03-31 | Sistema quantitativo de radiômica para decodificar o fenótipo tumoral |
| [NIH 1U01CA190234](https://projectreporter.nih.gov/project_info_description.cfm?aid=8799943&icde=27026470) | Slicer-Radiomics-U01 | Aerts, Hugo | 2015-01-01 | 2019-12-01 | Biomarcadores de genótipo e fenótipo de imagem no câncer de pulmão |
| [NIH 5U24CA180924](https://projectreporter.nih.gov/project_info_details.cfm?aid=9127923&icde=31460433&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC) | Análise de dados moleculares mapeados espacialmente | Joel Saltz | 2014-09-01 | 2019-08-31 | Ferramentas para analisar morfologia e dados moleculares mapeados espacialmente |
| [NIH 5R01CA184354](https://projectreporter.nih.gov/project_info_description.cfm?aid=8828624&icde=27036841&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | NIRFAST (Dartmouth) | Davis, Scott C. | 2014-04-01 | 2019-02-28 | Tomografia de fluorescência por RM para quantificar a concentração de receptores tumorais in vivo |
| [NIH R43DE027595](https://projectreporter.nih.gov/project_info_description.cfm?aid=9465772&icde=36620728&ddparam=&ddvalue=&ddsub=&cr=2&csb=default&cs=ASC&pball=) | VROrthognathic | Paniagua, Beatriz | 2017-09-07 | 2018-09-06 | Simulador de realidade virtual de alta fidelidade para cirurgia ortognática |
| [NIH 1R21DE025306](https://projectreporter.nih.gov/project_info_description.cfm?aid=9111256&icde=31459429&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | CMF | Paniagua, Beatriz | 2016-09-01 | 2018-08-31 | Biomarcadores de textura da artrite para o osso subcondral na articulação temporomandibular |
| [NIH 1U01NS082086](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462842&icde=27164806&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_SHAPEANALSS | Gerig, Guido | 2012-09-28 | 2018-08-31 | Análise de forma 4D para modelar trajetórias de mudança espaço-temporal na doença de Huntington |
| [NIH U24 CA180918](https://projectreporter.nih.gov/project_info_description.cfm?aid=8911287&icde=27026906) | [QIICR](https://qiicr.org) | Ron Kikinis, Andrey Fedorov | 2013-09-04 | 2018-08-31 | Informática quantitativa de imagens para pesquisa do câncer (QIICR) |
| [NIH 5R01NS055903](https://projectreporter.nih.gov/project_info_description.cfm?aid=8900362&icde=27164764&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_KIDS | Nopoulos, Peggy | 2009-03-01 | 2018-07-31 | Crescimento e desenvolvimento do corpo estriado na doença de Huntington |
| [NIH 1U01CA199459](https://projectreporter.nih.gov/project_info_description.cfm?aid=8971083&icde=27026834) | SlicerDMRI Diffusion MRI | O'Donnell, Lauren Jean | 2015-09-22 | 2018-07-31 | Tecnologia de RM por difusão de código aberto para pesquisa do câncer cerebral |
| [NIH 5R01EB020667-02](https://projectreporter.nih.gov/project_info_description.cfm?aid=9100712&icde=34329960) | OpenIGTLink | Tokuda, Junichi | 2015-07-01 | 2018-06-30 | OpenIGTLink: uma interface de comunicação em rede para intervenções guiadas por imagem em circuito fechado |
| [NIH 5P41EB015902](https://projectreporter.nih.gov/project_info_description.cfm?aid=8890837&icde=27036647&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | DiffusionMRI | Kikinis, Ron | 2013-08-01 | 2018-05-31 | Centro de Análise de Neuroimagem (NAC) |
| [NIH 2R42HD081712](https://projectreporter.nih.gov/project_info_description.cfm?aid=9141675&icde=31459353&ddparam=&ddvalue=&ddsub=&cr=5&csb=default&cs=ASC) | Craniossinostose | Linguraru, Marius George | 2016-05-01 | 2018-04-30 | Sistema de planejamento guiado por imagem para correção do crânio em crianças com craniossinostose: Fase II |
| [NIH R01CA160902](https://projectreporter.nih.gov/project_info_description.cfm?aid=8817256&icde=27036729&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | DWI | Maier, Stephan E | 2012-04-01 | 2018-02-28 | Avanço e validação da RM por difusão e espectroscópica da próstata |
| [NIH 1R01DE024450](https://projectreporter.nih.gov/project_info_description.cfm?aid=8576556&icde=18353487) | CMF | Cevidanes, Lucia | 2013-09-10 | 2017-08-31 | Quantificação de alterações ósseas 3D na osteoartrite da articulação temporomandibular |
| [NIH 2R42CA167907](https://projectreporter.nih.gov/project_info_description.cfm?aid=8979242&icde=27036988&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Fantoma de calibração PET/CT | Kinahan, Paul E | 2012-05-01 | 2017-07-31 | Métodos calibrados para imagens quantitativas PET/CT, Fase II |
| [NIH R42CA167907](https://projectreporter.nih.gov/project_info_description.cfm?aid=8979242&icde=27036988&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Fantoma de calibração PET/CT | Kinahan, Paul E. | 2012-05-01 | 2017-07-01 | Métodos calibrados para imagens quantitativas PET/CT, Fase II |
| NA | HD_TRACKON | Tabrizi, Sarah | 2012-01-01 | 2016-12-31 | TRACK-ON HD |
| CCO ACRU | SlicerRT | Fichtinger, Gabor | 2011-01-01 | 2016-12-31 | Unidade de Pesquisa Aplicada do Câncer do Cancer Care Ontario, Canadá |
| CCO OCAIRO | SlicerRT | Jaffray, David | 2011-01-01 | 2016-12-31 | Consórcio de Ontário para Intervenções Adaptativas em Radio-Oncologia, Canadá |
| NA | HD_TRAJECTORY | Kim, Eun Young | 2014-11-01 | 2016-10-31 | Desenvolvimento de um pipeline de segmentação robusto que permita a estimativa consistente de trajetórias de indivíduos com gene HD positivo em múltiplos centros de RM longitudinal |
| [NIH 1R41HD081712](https://projectreporter.nih.gov/project_info_description.cfm?aid=8778815&icde=27036063&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASCIMAGE-GUIDED) | Craniossinostose | Linguraru, Marius George | 2014-09-26 | 2016-08-31 | Sistema de planejamento guiado por imagem para correção do crânio em crianças com craniossinostose |
| [NIH 5R01NS040068](https://projectreporter.nih.gov/project_info_description.cfm?aid=8338456&icde=27164778&ddparam=&ddvalue=&ddsub=&cr=4&csb=default&cs=ASC) | HD_PREDICT | Paulsen, Jane | 2000-08-01 | 2016-08-31 | Preditores neurobiológicos da doença de Huntington (PREDICT-HD) |
| [NIH 3R42CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=8863934&icde=27037113&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Biópsia com agulha guiada por PET-CT | Cleary, Kevin R. | 2012-09-01 | 2016-08-01 | Melhoria da biópsia de lesões hepáticas na sala de TC por meio da fusão com imagens PET |
| [NIH 1R43DE024334](https://projectreporter.nih.gov/project_info_description.cfm?aid=8710950&icde=27036891) | OrthognathicTrac | Enquobahrie, Andinet A. | 2014-08-05 | 2016-07-31 | Orientação por imagem em tempo real para melhorar a cirurgia ortognática |
| [NIH 1R01EB014947](https://projectreporter.nih.gov/project_info_description.cfm?aid=8272742&icde=13552329) | PediatricRadiologicDecisionSupport | Murphy, Shawn N | 2012-08-01 | 2016-07-31 | Suporte à decisão radiológica pediátrica habilitado por Mi2B2 |
| [NIH 5R01CA111288](https://projectreporter.nih.gov/project_info_description.cfm?aid=8906771&icde=27026518) | ProstateBRP | Tempany, Clare M. | 2004-12-01 | 2016-07-01 | Tecnologias habilitadoras para intervenções de próstata guiadas por RM |
| [NIH 5U01CA151261](https://projectreporter.nih.gov/project_info_description.cfm?aid=8707214&icde=27026645) | ProstateQIN | Fennessy, Fiona | 2010-09-01 | 2016-07-01 | RM quantitativa do câncer de próstata como biomarcador e guia para o tratamento |
| [NIH 1U01NS082074](https://projectreporter.nih.gov/project_info_description.cfm?aid=8596213&icde=27164895&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_GENETICS | Calhoun/Turner | 2013-07-01 | 2016-06-30 | Imagem e genética na doença de Huntington |
| [NIH 1U01NS083173](https://projectreporter.nih.gov/project_info_description.cfm?aid=8529927&icde=27164835&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_PET | Feigin, Andrew | 2013-07-01 | 2016-06-30 | Imagem de redes cerebrais: um novo biomarcador para a doença de Huntington pré-clínica |
| [NIH 1R01CA170665](https://projectreporter.nih.gov/project_info_description.cfm?aid=8384153&icde=27037397&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Dayton, Paul A. | 2012-09-01 | 2016-06-01 | Detecção de microtumores por meio da quantificação de anomalias vasculares induzidas por tumores |
| [NIH 1U01NS083223](https://projectreporter.nih.gov/project_info_description.cfm?aid=8652000&icde=27164795&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_WHITEMATTER | Westin, Carl-Fredrik | 2014-01-01 | 2015-12-31 | Caracterização da substância branca na doença de Huntington usando RM por difusão |
| CCO RC | SlicerRT | Fichtinger, Gabor | 2010-01-01 | 2015-12-31 | Cátedra de Pesquisa do Cancer Care Ontario, Canadá |
| [NIH 1U01NS082083](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462829&icde=27164863&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_FMRI_DWI | Rao, Stephen Mark | 2012-09-26 | 2015-08-31 | Conectividade funcional na doença de Huntington pré-manifesta |
| [NIH R41CA196565](https://projectreporter.nih.gov/project_info_description.cfm?aid=8905274&icde=27036277&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Registro de próstata de Duke | Palmeri, Mark L. e McCormick, Matthew M. | 2015-04-01 | 2015-04-01 | Avaliação do câncer de próstata via imagem de elasticidade ARFI 3D integrada e RM multiparamétrica |
| [NIH 1R43EB016621](https://projectreporter.nih.gov/project_info_description.cfm?aid=8472102&icde=27037328&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Aylward, Stephen R. | 2013-05-01 | 2015-04-01 | Suporte e automação rápidos de procedimentos em campo |
| [NIH 1R41NS081792](https://projectreporter.nih.gov/project_info_description.cfm?aid=8453963&icde=27037364&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Aylward, Stephen R. | 2013-01-01 | 2014-12-01 | Sistema de avaliação multimodalidade baseado em imagem para lesão cerebral traumática |
| [NIH 2R42CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=8390856&icde=27037039&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Biópsia com agulha guiada por PET-CT | Cleary, Kevin R. | 2012-09-01 | 2014-08-01 | Melhoria da biópsia de lesões hepáticas na sala de TC por meio da fusão com imagens PET |
| [NIH 1R43CA165621](https://projectreporter.nih.gov/project_info_description.cfm?aid=8252988&icde=27037450&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | [TubeTK](https://tubetk.org) | Aylward, Stephen R | 2012-12-01 | 2014-08-01 | Análise ultrassonográfica quantitativa da morfologia vascular para avaliação do câncer |
| [NIH 5U01NS082085](https://projectreporter.nih.gov/project_info_description.cfm?aid=8462830&icde=27164813&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_SUBCORTICAL_SHAPE | Miller, Michael e Ross, Christopher | 2012-09-26 | 2014-07-31 | Análise de forma dos núcleos da base e circuitos na doença de Huntington |
| [NIH 5U54EB005149](https://projectreporter.nih.gov/project_info_description.cfm?aid=8501010&icde=27164945&ddparam=&ddvalue=&ddsub=&cr=5&csb=default&cs=ASC) | HD_DWI | Kikinis, Ron | 2010-09-30 | 2014-06-30 | Aliança Nacional para Computação de Imagens Médicas |
| [NIH 5R01NS054893](https://projectreporter.nih.gov/project_info_description.cfm?aid=8077226&icde=27164732&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | HD_FMRI | Paulsen, Jane | 2007-05-15 | 2013-04-30 | Alterações cognitivas e funcionais do cérebro na doença de Huntington pré-clínica (HD) |
| [NIH R41CA153488](https://projectreporter.nih.gov/project_info_description.cfm?aid=7999618&icde=27037084&ddparam=&ddvalue=&ddsub=&cr=1&csb=default&cs=ASC) | Biópsia com agulha guiada por PET-CT | Cleary, Kevin R. | 2010-07-01 | 2012-06-01 | Melhoria da biópsia de lesões hepáticas na sala de TC por meio da fusão com imagens PET |

## Uso comercial

Convidamos entidades comerciais a usar o 3D Slicer.

### A licença do Slicer permite o uso comercial

- O 3D Slicer é um software gratuito e de código aberto distribuído sob uma licença de estilo BSD.

- A licença não impõe restrições ao uso do software.

- O 3D Slicer NÃO é aprovado pela FDA. É responsabilidade do usuário garantir a conformidade com as normas e regulamentações aplicáveis.

- Para mais detalhes, consulte o Contrato de Licença de Software do 3D Slicer.

### Parceiros comerciais

- A [Ebatinca SL](https://ebatinca.com/) é uma empresa internacional de tecnologia em Las Palmas, Espanha, focada em tecnologia para o desenvolvimento sustentável. Áreas principais: navegação e treinamento por ultrassom, RV colaborativa, suporte à pesquisa e soluções personalizadas baseadas no Slicer.

- A [Isomics](https://isomics.com/) usa o 3D Slicer em diversas parcerias de pesquisa acadêmica e comercial em áreas como planejamento e orientação para neurocirurgia, imagem quantitativa para ensaios clínicos e informática de imagens clínicas.

- A [Kitware](https://www.kitware.com/opensource/slicer.html) concentra-se em resolver os desafios científicos mais complexos do mundo por meio de soluções de software personalizadas. A empresa tem um longo histórico de contribuição para plataformas de código aberto que servem de base para muitos aplicativos de visualização médica e processamento de dados. A Kitware ajuda clientes a desenvolver produtos comerciais baseados no 3D Slicer e já usou a plataforma para prototipar rapidamente soluções em praticamente todos os aspectos da imagem médica.

*Listados em ordem alfabética.*

### Produtos baseados no 3D Slicer

Muitas empresas preferem não divulgar quais componentes de software usam em seus produtos, portanto aqui só podemos listar alguns produtos comerciais baseados no 3D Slicer:

- Allen Institute for Brain Science: o Allen Institute for Brain Science está desenvolvendo o Cell Locator, um aplicativo de desktop para alinhar manualmente espécimes a espaços 3D anotados. Veja mais informações neste [blog da Kitware](https://blog.kitware.com/cell-locator-a-3d-slicer-based-desktop-application-that-manually-aligns-specimens-to-annotated-3d-spaces-developed-for-the-allen-institute-for-brain-science/).

- A [Dent.AI Medical Imaging](https://thedent.ai) está desenvolvendo um sistema de planejamento de cirurgia oral com IA que gera modelos virtuais realistas de pacientes a partir de dados de CBCT e escaneamento intraoral para apoiar a colocação de implantes navegada e procedimentos de reconstrução óssea.

- A [EBATINCA](https://ebatinca.com) está desenvolvendo o StaRT, uma plataforma interativa de simulação e educação em radioterapia, que oferece fluxos de trabalho clínicos realistas e exercícios baseados em casos, projetados para estudantes e profissionais clínicos de todo o mundo. Veja mais informações no [site do produto](https://ebatinca.com/productos/start).

- [Polarean, Inc.](https://polarean.com/): o XENOVIEW VDP da Polarean é um software aprovado pela FDA, construído sobre o 3D Slicer, para visualização e avaliação da ventilação pulmonar. Veja mais informações neste [blog da Kitware](https://www.kitware.com/kitware-supports-development-and-launch-of-fda-cleared-mr-image-processingsoftware-for-lung-ventilation-imaging/).

- Imagem e dosimetria radiofarmacêutica: RPTDose, um aplicativo baseado no 3D Slicer que agiliza e integra técnicas de análise quantitativa de imagem e estimativa de dose para orientar e otimizar o uso de agentes de terapia radiofarmacêutica em ensaios clínicos. Veja mais informações neste [blog da Kitware](https://blog.kitware.com/kitware-customer-highlight-radiopharmaceutical-imaging-and-dosimetry-llc-rapid/).

- A [SonoVol](https://sonovol.com/) desenvolveu um sistema de imagem por ultrassom de corpo inteiro para pequenos animais. Essa startup surgiu de pesquisas no Departamento de Engenharia Biomédica da Universidade da Carolina do Norte em Chapel Hill. Sua equipe agora faz parte da Revvity, Inc. Veja mais informações neste [blog da Kitware](https://blog.kitware.com/kitware-customer-highlight-sonovol/) e no [site do produto](https://www.perkinelmer.com/category/ultrasound-imaging).

- Xoran Technologies: plataforma guiada por imagem para cirurgia de estimulação cerebral profunda. Veja mais informações neste [blog da Kitware](https://blog.kitware.com/xoran-technologies-and-kitware-collaborate-on-image-guided-platform-for-deep-brain-stimulation-surgery/).

- A [Xstrahl](https://www.xstrahl.com/) está desenvolvendo uma Plataforma de Pesquisa em Radiação de Pequenos Animais (SARRP) que usa o 3D Slicer como aplicativo de front-end para o posicionamento de feixes de radioterapia e o controle do sistema. Veja mais informações neste [blog da Kitware](https://blog.kitware.com/kitware-customer-highlight-muriplan-from-xstrahl-a-3d-slicer-based-radiotherapy-treatment-planning-system/).

*Listados em ordem alfabética.*

## Governança

Esta seção apresenta os princípios orientadores e a estrutura de tomada de decisões do projeto Slicer, incluindo o Código de Conduta e o modelo de governança que descrevem como as decisões são tomadas e quem é responsável por manter a saúde do projeto.

### Código de Conduta

A comunidade do Slicer está comprometida em promover um ambiente acolhedor, respeitoso e inclusivo. Os detalhes estão descritos no Código de Conduta abaixo.

#### Nosso compromisso

Nós, como membros, colaboradores e líderes, comprometemo-nos a fazer da participação em nossa comunidade uma experiência livre de assédio para todas as pessoas, independentemente de idade, porte físico, deficiência visível ou invisível, etnia, características sexuais, identidade e expressão de gênero, nível de experiência, educação, condição socioeconômica, nacionalidade, aparência pessoal, raça, casta, cor, religião ou identidade e orientação sexual.

Comprometemo-nos a agir e interagir de maneiras que contribuam para uma comunidade aberta, acolhedora, diversa, inclusiva e saudável.

#### Nossos padrões

Exemplos de comportamento que contribuem para um ambiente positivo em nossa comunidade incluem:

- Demonstrar empatia e gentileza com as outras pessoas

- Respeitar opiniões, pontos de vista e experiências diferentes

- Dar e aceitar com elegância feedback construtivo

- Assumir a responsabilidade e pedir desculpas às pessoas afetadas por nossos erros, aprendendo com a experiência

- Focar no que é melhor não apenas para nós como indivíduos, mas para a comunidade como um todo

Exemplos de comportamento inaceitável incluem:

- Uso de linguagem ou imagens sexualizadas e atenção ou investidas sexuais de qualquer tipo

- Trolling, comentários insultuosos ou depreciativos e ataques pessoais ou políticos

- Assédio público ou privado

- Publicar informações privadas de outras pessoas, como endereço físico ou de e-mail, sem sua permissão explícita

- Outras condutas que possam razoavelmente ser consideradas inadequadas em um ambiente profissional

#### Responsabilidades de aplicação

Os líderes da comunidade são responsáveis por esclarecer e fazer cumprir nossos padrões de comportamento aceitável e tomarão medidas corretivas apropriadas e justas em resposta a qualquer comportamento que considerem inadequado, ameaçador, ofensivo ou prejudicial.

Os líderes da comunidade têm o direito e a responsabilidade de remover, editar ou rejeitar comentários, commits, código, edições de wiki, issues e outras contribuições que não estejam alinhadas a este Código de Conduta, e comunicarão os motivos das decisões de moderação quando apropriado.

#### Abrangência

Este Código de Conduta aplica-se a todos os espaços da comunidade e também quando um indivíduo representa oficialmente a comunidade em espaços públicos. Exemplos de representação da nossa comunidade incluem o uso de um endereço de e-mail oficial, publicações por meio de uma conta oficial de mídia social ou atuação como representante designado em um evento on-line ou presencial.

#### Aplicação

Casos de comportamento abusivo, de assédio ou de qualquer outra forma inaceitável podem ser denunciados aos líderes da comunidade listados [aqui](https://github.com/Slicer/Slicer/blob/master/GOVERNANCE.md#benevolent-dictators-for-life) por mensagem privada no [fórum do Slicer](https://discourse.slicer.org). Todas as reclamações serão analisadas e investigadas de forma rápida e justa.

Todos os líderes da comunidade são obrigados a respeitar a privacidade e a segurança de quem denuncia qualquer incidente.

#### Atribuição

Este Código de Conduta é adaptado do [Contributor Covenant](https://www.contributor-covenant.org), versão 2.1, disponível em <https://www.contributor-covenant.org/version/2/1/code_of_conduct.html>.

As Diretrizes de Impacto na Comunidade foram inspiradas na [escala de aplicação do código de conduta da Mozilla](https://github.com/mozilla/diversity).

Para respostas a perguntas frequentes sobre este código de conduta, consulte o FAQ em <https://www.contributor-covenant.org/faq>. Traduções estão disponíveis em <https://www.contributor-covenant.org/translations>.

#### Alterações

Para o histórico de atualizações e revisões deste documento, consulte <https://github.com/Slicer/Slicer/commits/main/CODE_OF_CONDUCT.md>.

### Processo de tomada de decisões

1. Dado o tema de interesse, inicie a discussão no [fórum do Slicer](https://discourse.slicer.org).

2. Identifique um pequeno grupo de membros da comunidade interessados em estudar o tema com mais profundidade.

3. Leve a discussão para fora da lista geral, trabalhe na análise de opções e alternativas e resuma as conclusões na wiki ou em local semelhante. As páginas de [Labs](https://www.slicer.org/wiki/Documentation/Labs) costumam ser um bom espaço para esse resumo.

4. Anuncie no [fórum do Slicer](https://discourse.slicer.org) a discussão aprofundada do tema para o [hangout da comunidade do Slicer](https://discourse.slicer.org/c/community/hangout), incentivando qualquer pessoa interessada em opinar sobre o tema a participar da discussão. Se alguém tiver interesse em participar da discussão, mas não puder comparecer à reunião por conflito de agenda, deve notificar os líderes do projeto em questão e identificar um horário adequado para todos.

5. Com sorte, chega-se a um consenso no hangout e segue-se com o plano acordado.

*A versão inicial destas diretrizes foi estabelecida durante a [semana de projetos de inverno de 2017](https://www.na-mic.org/Wiki/index.php/2017_Winter_Project_Week/UpdatingCommunityForums).*

### Ditadores benevolentes vitalícios

Os [ditadores benevolentes](https://slicer.readthedocs.io/en/latest/user_guide/about.html#benevolent-dictators-for-life) podem integrar mudanças para manter a saúde da plataforma e ajudar a interpretar ou resolver conflitos relacionados às diretrizes de contribuição.

Atualmente, incluem:

- Jean-Christophe Fillion-Robin

- Andras Lasso

- Steve Pieper

*Ordenados alfabeticamente pelo sobrenome.*

A comunidade do Slicer é inclusiva e dá boas-vindas a qualquer pessoa que queira trabalhar para se tornar um desenvolvedor principal e, depois, um BDFL (ditador benevolente vitalício). Isso acontece com muito trabalho e a aprovação dos BDFLs existentes.

## Fale conosco

Recomenda-se publicar quaisquer perguntas, relatos de bugs ou solicitações de melhoria no [fórum do Slicer](https://discourse.slicer.org).

Nosso rastreador de problemas on-line está disponível [aqui](https://issues.slicer.org).

Para consultoria comercial/confidencial, entre em contato com um dos [parceiros comerciais](#parceiros-comerciais).
