# Interface de usuário

## Visão geral do aplicativo

O Slicer armazena todos os dados carregados em um repositório de dados, chamado de "cena" (ou cena do Slicer ou cena MRML). Cada conjunto de dados, como um volume de imagem, um modelo de superfície ou um conjunto de pontos, é representado na cena como um "nó".

O Slicer oferece um grande número de "módulos", cada um implementando um conjunto específico de funções para criar ou manipular dados na cena. Em geral, os módulos não interagem diretamente entre si: todos eles apenas operam sobre os nós de dados da cena. O pacote do Slicer contém mais de 100 módulos integrados, e módulos adicionais podem ser instalados usando o Gerenciador de extensões.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_main_window_rev02.png)

### Painel do módulo

Este painel (localizado por padrão no lado esquerdo da janela principal do aplicativo) exibe todas as opções e recursos que o módulo atual oferece ao usuário. O módulo atual pode ser selecionado usando a barra de ferramentas de **Seleção de módulo**.

#### Sonda de dados (Data Probe)

A Sonda de dados está localizada na parte inferior do painel do módulo. Ela exibe informações sobre o conteúdo da visualização na posição do ponteiro do mouse:

- Informações da visualização de corte (exibidas quando o mouse está sobre uma visualização de corte):

  * Nome da visualização de corte: `Red`, `Green`, `Yellow`, etc.

  * Posição anatômica: três valores de coordenadas, com o prefixo `R`/`L` (direita/esquerda), `A`/`P` (anterior/posterior), `S`/`I` (superior/inferior). A origem, a posição (0,0,0), foi escolhida pelo técnico de imagem quando a imagem foi criada. Por exemplo, `(R 17.6, P 35.3, S 12.1)` para uma imagem clínica significa que a posição atual está a 17,6 mm à direita da origem, 35,3 mm em direção ao posterior e 12,1 mm superior em relação à origem.

  * Orientação da visualização: `Axial`, `Sagittal`, `Coronal` para as orientações anatômicas padrão, e `Reformat` para qualquer outra orientação.

  * Espaçamento de cortes: distância entre os cortes nesta orientação. Para uma imagem clínica, `Sp: 2.5` significa que os cortes estão a 2,5 mm de distância um do outro.

- Informações da camada de volume: três linhas, uma para cada camada de volume

  * Tipo de camada: `L` (rótulo), `F` (primeiro plano), `B` (plano de fundo).

  * Nome do volume, ou `None` se nenhum volume estiver selecionado para essa camada.

  * Coordenadas de voxel (IJK) do volume.

  * Valor do voxel. Para volumes de rótulos, também é exibido o nome do rótulo correspondente ao valor do voxel.

- Informações de segmentação: para cada segmentação visível naquela posição

  * Tipo de camada: `S` (segmentação)

  * Nome da segmentação.

  * Nomes dos segmentos. Vários nomes de segmentos são listados se vários segmentos forem exibidos naquela posição (os segmentos se sobrepõem).

### Visualizações

O Slicer exibe os dados em diversas visualizações. O usuário pode escolher entre vários layouts predefinidos, que podem conter visualizações de corte, 3D, de gráfico e de tabela.

A barra de ferramentas de Layout oferece um menu suspenso de layouts úteis para muitos tipos de estudos. Quando o Slicer é fechado normalmente, o layout selecionado é salvo e restaurado na próxima vez que o aplicativo é iniciado.

### Menu do aplicativo

- **File** (Arquivo): funções para carregar uma cena salva anteriormente ou conjuntos de dados individuais de diversos tipos, e para baixar conjuntos de dados de exemplo da internet. Uma opção para salvar cenas e dados também é fornecida aqui. **Add Data** (Adicionar dados) permite carregar dados de arquivos. O módulo **DICOM** é recomendado para importar dados de arquivos DICOM e carregar os dados DICOM importados. **Save** (Salvar) abre a janela "Save Data" (Salvar dados), que oferece uma variedade de opções para salvar todos os dados ou conjuntos de dados selecionados.

- **Edit** (Editar): contém uma opção para exibir as Configurações do aplicativo (Application Settings), que permite aos usuários personalizar a aparência e o comportamento do Slicer, como os módulos exibidos na barra de ferramentas, o tamanho da fonte do aplicativo, a localização do diretório temporário e a localização de módulos adicionais do Slicer a serem incluídos.

- **View** (Visualizar): funções para mostrar/ocultar janelas e widgets adicionais, como o **Gerenciador de extensões** para instalar extensões da loja de aplicativos do Slicer, o **Registro de erros** (Error Log) para verificar se o aplicativo encontrou algum possível erro, o **Console Python** para obter um console Python com o qual interagir com os dados ou módulos carregados, **mostrar/ocultar barras de ferramentas** ou **alternar o layout da visualização**.

- **Help** (Ajuda): contém links para documentação, guias e sites da comunidade. **Report a Bug** (Relatar um bug) fornece instruções para relatar bugs e acesso conveniente às mensagens de log. Há também links para pesquisar **Publicações do Slicer** (Slicer Publications) e aprender **Como citar** (How to Cite) o Slicer.

### Barra de ferramentas

A barra de ferramentas oferece acesso rápido às funções de uso frequente. Os painéis individuais da barra de ferramentas podem ser mostrados/ocultados usando o menu: seção View / Toolbars.

A barra de ferramentas de **Seleção de módulo** é usada para selecionar o "módulo" atualmente ativo. A barra de ferramentas oferece opções para pesquisar nomes de módulos (`Ctrl` + `f` ou clique no ícone da lupa) ou selecionar a partir de um menu. O **botão suspenso do histórico de módulos** mostra a lista de módulos usados recentemente. Os **botões de seta** podem ser usados para voltar a/retornar de um módulo usado anteriormente.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_module_toolbar.png)

A barra de ferramentas de **Módulos favoritos** contém uma lista dos módulos usados com mais frequência. A lista pode ser personalizada usando o menu: Edit / Application settings / Modules / Favorite Modules. Arraste e solte módulos da lista de Módulos para a lista de Módulos favoritos para adicionar um módulo.

### Barra de status

Este painel pode exibir o status do aplicativo, como a operação atual em andamento. Clicar nos pequenos ícones **X** exibe a janela do Registro de erros.

## Revisar os dados carregados

Os dados disponíveis no Slicer podem ser revisados no módulo Data, que pode ser encontrado na barra de ferramentas ou na lista de módulos ![](https://slicer.readthedocs.io/en/latest/_images/SubjectHierarchy.png). Mais detalhes sobre o módulo podem ser encontrados na [wiki do Slicer](https://www.slicer.org/wiki/Documentation/Nightly/Modules/Data).

A aba padrão Hierarquia de sujeitos (Subject hierarchy) do módulo Data pode mostrar os conjuntos de dados em uma hierarquia de árvore, organizados como paciente/estudo/série, como é típico no DICOM, ou em qualquer outra estrutura de pastas:

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/data_loading_and_saving_subject_hier.png)

A visualização de Hierarquia de sujeitos contém inúmeras funções integradas para todos os tipos de dados. Essas funções podem ser acessadas clicando com o botão direito no nó da árvore. A lista de ações difere conforme o tipo de dado, por isso é útil explorar as opções.

Os dados de imagens médicas vêm em diversas formas e representações, o que pode confundir quem está começando na área. O diagrama a seguir oferece uma breve visão geral dos tipos de dados mais típicos encontrados ao usar o Slicer, especialmente em um fluxo de trabalho que envolve segmentação.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/data_loading_and_saving_formats.png)

### Selecionar os dados exibidos

A aba Hierarquia de sujeitos do módulo Data mostra todos os conjuntos de dados da cena. Clique no ícone do "olho" para mostrar/ocultar um item em todas as visualizações. Arraste e solte um item em uma visualização para exibi-lo nessa visualização.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/drag_to_view.gif)

Vários itens podem ser selecionados na árvore de hierarquia de sujeitos usando Ctrl-clique-esquerdo ou Shift-clique-esquerdo e arrastados de uma vez para a visualização selecionada. Se dois volumes forem arrastados para uma visualização ao mesmo tempo, ambos serão exibidos, mesclados entre si.

Se uma visualização for exibida apenas em visualizações selecionadas, você pode clicar com o botão direito no item e selecionar "Show in all views" (Mostrar em todas as visualizações) para mostrá-lo rapidamente em todas as visualizações.

Se o vínculo de visualização estiver habilitado para uma visualização de corte, arrastar um volume para qualquer uma das visualizações exibirá o volume em todas as visualizações desse grupo.

As opções de exibição podem ser ajustadas clicando com o botão direito no ícone do olho na coluna de exibição da árvore. Observe que essas opções são diferentes das opções oferecidas ao clicar com o botão direito na coluna "Node" (Nó) ou "Transform" (Transformação) da árvore.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_sh_display_menu.png)

Para volumes, as opções de exibição incluem:

- Redefinir o campo de visão ao exibir (Reset field of view on show): se habilitado, exibir um volume ajusta as visualizações para mostrar o volume no centro, preenchendo o campo de visão.

- Redefinir a orientação da visualização ao exibir (Reset view orientation on show): se habilitado, exibir um volume alinha as visualizações de corte com os eixos do volume.

## Interagir com as visualizações

### Referência cruzada de visualizações

Manter pressionada a tecla `Shift` enquanto move o mouse em qualquer visualização de corte ou 3D fará com que a mira (Crosshair) se mova para a posição selecionada em todas as visualizações. Por padrão, quando a mira é movida em qualquer visualização, todas as visualizações de corte rolam para a mesma posição RAS indicada pelo mouse. Esse recurso é útil durante a inspeção.

Para mostrar/ocultar a posição da mira, clique no ícone da mira ![](https://slicer.readthedocs.io/en/latest/_images/SlicesCrosshair.png).

Para personalizar o comportamento e a aparência da mira, clique no botão de "seta para baixo" no lado direito do ícone da mira.

### Modos do mouse

O Slicer tem vários modos do mouse: **Transform** (Transformar; que permite operações interativas de rotação, translação e zoom), **Window/Level** (Janela/Nível; para ajustar o brilho/contraste dos volumes de imagem) e **Place** (Posicionar; que permite posicionar objetos de forma interativa nas visualizações de corte e 3D).

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_mousemode_toolbar.png)

Os ícones da barra de ferramentas que alternam entre esses modos do mouse são mostrados acima, da esquerda para a direita, respectivamente. Posicionar lista de pontos (Place Point List) é a opção de posicionamento padrão, como mostrado acima; também há opções para posicionar outros nós, como widgets de Régua (Ruler) e de Região de interesse (Region of Interest), disponíveis no menu suspenso de Modo de posicionamento (Place Mode).

Observação

O modo Transform é o modo de interação padrão. Por padrão, o modo Place persiste durante uma operação de "posicionamento" após a seleção do ícone de Modo de posicionamento, e então o modo volta para Transform. O modo Place pode ser tornado persistente (útil para posicionar vários pontos de controle) marcando a caixa de seleção Persistent (Persistente) mostrada no extremo direito da barra de ferramentas de Modo do mouse.

#### Ajustar a janela/nível da imagem

As imagens médicas geralmente contêm milhares de níveis de cinza, mas as telas de computador comuns só conseguem exibir 256 níveis de cinza, e o olho humano também tem limitações quanto à diferença mínima de contraste que consegue perceber (consulte [Kimpe 2007](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3043920/) para informações mais específicas). Portanto, as imagens médicas são exibidas com brilho/contraste ajustável (janela/nível).

Por padrão, o 3D Slicer usa a configuração de janela/nível especificada no arquivo DICOM. Se ela não estiver disponível, a janela/nível é definida para conter toda a faixa de intensidade da imagem (exceto os 0,1 % superiores/inferiores, calculados por percentis, para não permitir que uma cauda muito fina da distribuição de intensidade diminua demais o contraste da imagem).

A janela/nível pode ser ajustada manualmente a qualquer momento clicando no botão "Adjust window/level" (Ajustar janela/nível) na barra de ferramentas e, em seguida, clicando com o botão esquerdo e arrastando em qualquer um dos visualizadores de corte. A janela/nível ideal pode ser calculada para uma área escolhida clicando com o botão esquerdo e arrastando enquanto mantém pressionada a tecla `Ctrl`.

[![](https://img.youtube.com/vi/u1B0F1KcVsk/0.jpg)](https://youtu.be/u1B0F1KcVsk "Vídeo de demonstração de como ajustar a janela/nível da imagem")

Opções adicionais de janela/nível, predefinições, histograma de intensidade e ajustes automáticos estão disponíveis na seção Display (Exibição) do módulo [Volumes](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumes.html). As predefinições também estão disponíveis no menu de contexto das visualizações de corte. Você pode redefinir para as configurações de janela/nível calculadas automaticamente usando o menu de contexto ou usando `Ctrl` + `clique duplo esquerdo` na visualização de corte.

### Visualização 3D

Exibe uma visualização 3D renderizada da cena junto com referências visuais para especificar a orientação e a escala.

Eixos de orientação padrão: A = anterior, P = posterior, R = direita, L = esquerda, S = superior e I = inferior.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_3d_view_controls_2025_03_09.png)

Controles da visualização 3D: a barra azul que cruza qualquer visualização 3D mostra um ícone de alfinete à sua esquerda. Quando o mouse passa sobre esse ícone, um painel para configurar a visualização 3D é exibido. O painel é ocultado quando o mouse se afasta. Para exibir esse painel de forma permanente, basta clicar no ícone do alfinete.

- **Centralizar a visualização 3D** (quadrado pequeno) centraliza o corte sobre o conteúdo atualmente visível da visualização 3D e todos os volumes carregados (mesmo os volumes que não estão visíveis). O campo de visão (fator de zoom) não é ajustado, portanto pode ser necessário aproximar/afastar para ver todos os objetos. Para redefinir o centro e o campo de visão ao mesmo tempo, clique na visualização 3D e pressione a tecla `r`.

- **Maximizar a visualização** / **Restaurar o layout da visualização** maximiza temporariamente a visualização selecionada / restaura o layout completo das visualizações.

- **Direção do ponto de vista** alterna a orientação da visualização entre direções padrão. Clicar no botão **L**eft (esquerda), **R**ight (direita), **A**nterior, **P**osterior, **S**uperior, **I**nferior fará com que o conteúdo 3D seja visto a partir dessa direção.

- O botão **Vínculo de visualização** (View link) sincroniza as propriedades entre as visualizações 3D (posição e direção do ponto de vista, régua, marcador de orientação, etc.).

- Alternar o modo de renderização **Ortográfico/perspectiva**. O modo ortográfico (projeção paralela) é útil para avaliar o tamanho, porque o tamanho do objeto exibido não depende da distância ao ponto de vista. O modo perspectiva oferece melhor percepção de profundidade, porque os objetos mais próximos parecem maiores.

- **Régua** (Ruler) controla a exibição da régua. Disponível apenas no modo de renderização ortográfico.

- **Visualização estereoscópica** (Stereo viewing) habilita a exibição estereoscópica. Os modos vermelho/azul e anáglifo exigem apenas óculos baratos com lentes coloridas de vermelho/azul. Outros modos exigem hardware de exibição 3D especial. Observe que a [extensão SlicerVirtualReality](https://www.slicervr.org/) oferece uma experiência superior de visualização e interação estereoscópica, com visualização 3D totalmente imersiva com um único clique de um botão, e interação rica com os objetos da cena usando controladores 3D.

- Mais opções (…)

  * **Usar depth peeling** deve estar habilitado para a renderização correta de superfícies semitransparentes (em modelos, marcações, etc.). Isso pode tornar as atualizações de renderização um pouco mais lentas e gerar artefatos quando a renderização de volume é usada na visualização.

  * **Mostrar/ocultar quadros por segundo (FPS)** exibe a velocidade de renderização no canto da visualização.

- **Marcador de orientação** controla a exibição da figura humana, do cubo, etc. no canto inferior direito.

- **Opções de visibilidade** controla a visibilidade da cor de fundo da visualização e dos componentes exibidos.

- **Spin** (Girar) faz a visualização girar continuamente.

- **Rock** (Balançar) faz a visualização balançar continuamente da esquerda para a direita.

- **Aproximar/afastar** (Zoom in/out) aproxima/afasta ligeiramente a visualização. Botões convenientes para telas sensíveis ao toque.

- O **Bloqueio de inclinação** (Tilt Lock) pode ser ativado/desativado usando o atalho de teclado `Ctrl` + `b`. No modo de bloqueio de inclinação, a rotação da visualização 3D é restrita ao eixo de azimute (direção esquerda-direita) ao desabilitar a rotação em torno do eixo de elevação (direção cima-baixo).

#### Sombras ambientais

- Visibilidade das sombras: se habilitada, sombras ambientais são exibidas para melhorar a percepção de profundidade

  * Escala de tamanho (Size scale; padrão: 0): tamanho dos detalhes a serem enfatizados pelas sombras. Valores mais baixos enfatizam as irregularidades da superfície (saliências e depressões). Uma escala de tamanho maior faz com que regiões maiores que estão muito mais distantes fiquem muito mais escuras. O valor ideal pode ser determinado ajustando o valor a partir do valor mais alto, gradualmente, até que as regiões que estão atrás dos objetos pareçam mais escuras. Valores muito altos (1,5 a 3,0) podem fazer com que toda a imagem pareça mais escura, por isso é importante ficar abaixo dessa faixa, normalmente até cerca de 0,5 a 1,5.

  * Escala de intensidade (Intensity scale; padrão: 1): intensidade do escurecimento pelas sombras. Aumente o valor para tornar as sombras mais escuras.

  * Deslocamento de intensidade (Intensity shift; padrão: 0): quantidade mínima de oclusão necessária para um escurecimento visível pelas sombras. Normalmente, só é necessário aumentar esse valor se a escala de intensidade for aumentada, o que torna toda a imagem um pouco mais escura. Nesse caso, aumentar o deslocamento de intensidade pode compensar o escurecimento geral.

  * Limiar de opacidade do volume (Volume opacity threshold; de 0 % a 100 %; padrão: 25 %): este valor afeta apenas a renderização de volume. Os voxels que tiverem opacidade acima desse valor projetarão sombras. Escolher um valor muito baixo resulta em artefatos escuros em regiões que têm opacidade muito baixa. Escolher um valor muito alto resulta em artefatos perto de regiões opacas que têm um valor de opacidade um pouco mais baixo.

Exemplos: ![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_ambient_shadows.png)

Observação

As configurações padrão das sombras ambientais podem ser escolhidas no menu do aplicativo (Edit / Application Settings / Views / 3D viewer defaults).

### Visualização de corte

São fornecidas três visualizações de corte padrão (com barras coloridas em Vermelho, Amarelo e Verde) nas quais cortes 2D Axiais, Sagitais, Coronais ou Oblíquos das imagens de volume podem ser exibidos. As visualizações de corte genéricas adicionais têm uma barra de cor cinza e um número de identificação no canto superior esquerdo.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/user_interface_slice_view_controls.png)

Controles da visualização de corte: a barra colorida que cruza qualquer visualização de corte mostra um ícone de alfinete à sua esquerda (**Mostrar controles da visualização**). Quando o mouse passa sobre esse ícone, um painel para configurar a visualização de corte é exibido. O painel é ocultado quando o mouse se afasta. Para exibir esse painel de forma permanente, basta clicar no ícone do alfinete. Para mais opções, clique no ícone de seta dupla (**Mostrar todas as opções**).

O módulo View Controllers (Controladores de visualização) oferece uma forma alternativa de exibir esses controladores no Painel do módulo.

- **Redefinir o campo de visão** (quadrado pequeno) centraliza o corte sobre o volume de fundo atual.

- O botão do "olho" **Mostrar em 3D** (Show in 3D) na linha superior pode mostrar o corte atual nas visualizações 3D. O menu suspenso do botão contém opções avançadas para personalizar como esse corte é renderizado: "…match volume" significa que as propriedades são tomadas do volume completo, enquanto "…match 2D" significa que as propriedades são copiadas da visualização de corte atual (por exemplo, copia a posição de zoom e deslocamento). Normalmente, essas diferenças são sutis e as configurações podem ser deixadas nos valores padrão.

- **Orientação do corte** (Slice orientation) permite que você escolha a orientação desta visualização de corte.

- **Reformat** permite a manipulação interativa da orientação do corte.

- O **controle deslizante de deslocamento do corte** (Slice offset slider) permite percorrer o volume em cortes. O tamanho do passo é definido por padrão conforme o espaçamento do volume de fundo, mas pode ser modificado clicando no botão "Spacing and field of view" (Espaçamento e campo de visão). O rótulo ao lado do valor de deslocamento (por exemplo, `S`, `L`, `A`, `IL`, `IRP`) reflete a direção normal do corte. Se o controle deslizante de deslocamento for movido para a direita, o corte se move nessa direção normal. Se a direção normal do corte não estiver alinhada com um eixo, o rótulo contém uma combinação de direções, com a ordem dos eixos refletindo o predomínio do eixo. Por exemplo, se a normal do plano aponta para o anterior e ligeiramente para a esquerda, o rótulo é `AL`, enquanto se a normal do plano aponta principalmente para a esquerda e ligeiramente para o anterior, o rótulo é `LA`.

- O **modo de mesclagem** (Blending mode) especifica como as camadas de primeiro plano e de fundo são misturadas.

- **Espaçamento e campo de visão** (Spacing and field of view): o espaçamento define o incremento do controle deslizante de deslocamento do corte. O campo de visão define o nível de zoom do corte.

- **Rotacionar para o plano do volume** (Rotate to volume plane) altera a orientação do corte para corresponder à orientação de aquisição mais próxima do volume exibido.

- **Marcador de orientação** controla a exibição da figura humana, do cubo, etc. no canto inferior direito.

- **Régua** (Ruler) controla a exibição da régua na visualização de corte.

- O botão **Vínculo de visualização** (View link) sincroniza as propriedades das visualizações do mesmo grupo de visualizações, como a seleção de volumes de primeiro plano/fundo/rótulo, a opacidade dos volumes de primeiro plano/rótulo e o fator de zoom.

  * Para visualizações paralelas (ou seja, que estão definidas com a mesma orientação, como `axial`), a posição do centro da visualização também é sincronizada.

  * Um clique longo no botão expõe a opção **hot-linked** (vínculo a quente), que controla quando as propriedades são sincronizadas (imediatamente ou quando o botão do mouse é solto).

  * Um grupo de visualizações normalmente consiste em 3 visualizações ortogonais (por exemplo, na visualização `Four-Up`, as visualizações `R`, `G`, `Y` estão no mesmo grupo). Em layouts que contêm vários trios de visualizações de corte, cada trio forma um grupo separado (por exemplo, no layout `Three over three` há dois grupos de visualizações: um grupo é `R`, `G`, `Y` e o outro grupo é `R+`, `G+`, `Y+`).

- Os botões do "olho" de **Visibilidade da camada** (Layer visibility) e os seletores numéricos de **Opacidade da camada** (Layer opacity) controlam a visibilidade das segmentações e dos volumes na visualização de corte.

- O controle deslizante de **Opacidade do volume de primeiro plano** (Foreground volume opacity) permite uma transição gradual entre os volumes de primeiro plano e de fundo.

- A **Interpolação** (Interpolation) permite exibir os valores dos voxels sem interpolação. Recomenda-se manter a interpolação habilitada e desabilitá-la apenas para testes e resolução de problemas.

- Os **seletores de nós** (Node selectors) são usados para escolher quais volumes de fundo, primeiro plano e mapa de rótulos e quais segmentações exibir nesta visualização de corte. Observação: várias segmentações podem ser exibidas em uma visualização de corte, mas os controles da visualização de corte só permitem ajustar a visibilidade do nó de segmentação atualmente selecionado.

Removido na versão 5.10:

- O recurso **Lightbox** para selecionar uma visualização em mosaico (também conhecida como folha de contatos) foi removido. Em vez disso, pode ser usada a opção *Lightbox image columns* (Colunas de imagens do Lightbox) oferecida pelo módulo [Screen Capture](https://slicer.readthedocs.io/en/latest/user_guide/modules/screencapture.html).

## Atalhos de mouse e teclado

### Combinações de teclas alternativas para macOS

Ao usar atalhos no macOS, substitua as seguintes teclas por sua versão correspondente do macOS.

| Tecla  | Tecla do macOS         |
| ------ | ---------------------- |
| `Ctrl` | `Command` / `⌘`        |
| `Alt`  | `Option` / `⌥` / `Alt` |

### Atalhos genéricos

| Atalho                          | Operação                                                                   |
| ------------------------------- | -------------------------------------------------------------------------- |
| `Ctrl` + `f`                    | encontrar um módulo pelo nome (pressione `Enter` para selecionar)          |
| `Ctrl` + `o`                    | adicionar dados de um arquivo                                              |
| `Ctrl` + `s`                    | salvar dados em arquivos                                                   |
| `Ctrl` + `w`                    | fechar a cena                                                             |
| `Ctrl` + `0`                    | mostrar o Registro de erros                                              |
| `Ctrl` + `1`                    | mostrar a Ajuda do aplicativo                                            |
| `Ctrl` + `2`                    | mostrar as Configurações do aplicativo                                  |
| `Ctrl` + `3` / `Ctrl` + `` ` `` | mostrar/ocultar o Console Python                                         |
| `Ctrl` + `4`                    | mostrar o Gerenciador de extensões                                      |
| `Ctrl` + `5`                    | mostrar/ocultar o Painel do módulo                                      |
| `Ctrl` + `h`                    | abrir o módulo de inicialização padrão (configurável nas Configurações do aplicativo) |

### Visualizações de corte

Os atalhos a seguir estão disponíveis quando uma visualização de corte está ativa. Para ativar uma visualização, clique dentro dela: se você não quiser alterar nada na visualização, basta ativá-la e então fazer `clique direito` sem mover o mouse. Observe que simplesmente passar o mouse sobre uma visualização de corte não a ativará.

| Atalho                                 | Operação                                                                                                                          |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `clique direito` + `arrastar cima/baixo` | aproximar/afastar a imagem (`Alt` opcional, útil durante o posicionamento de pontos)                                           |
| `Ctrl` + `roda do mouse`               | aproximar/afastar a imagem                                                                                                      |
| `clique do meio` + `arrastar`          | deslocar (transladar) a visualização (`Alt` opcional, útil durante o posicionamento de pontos)                                |
| `Shift` + `clique esquerdo` + `arrastar` | deslocar (transladar) a visualização (`Alt` opcional, útil durante o posicionamento de pontos)                               |
| `seta esquerda` / `seta direita`       | ir para o corte anterior/seguinte                                                                                             |
| `b` / `f`                              | ir para o corte anterior/seguinte                                                                                             |
| `Shift` + `mover o mouse`              | mover a mira em todas as visualizações                                                                                       |
| `Ctrl` + `Alt` + `clique esquerdo` + `arrastar` | rotacionar a interseção de cortes das outras visualizações (as `Interseções de cortes` devem estar habilitadas na barra de ferramentas de `Seleção de mira`) |
| `v`                                    | alternar a visibilidade do corte na visualização 3D                                                                          |
| `r`                                    | redefinir o zoom e o deslocamento para os valores padrão                                                                     |
| `g`                                    | alternar a segmentação ou o volume de mapa de rótulos                                                                        |
| `t`                                    | alternar a visibilidade do volume de primeiro plano                                                                          |
| `[` / `]`                              | usar o volume anterior/seguinte como fundo                                                                                   |
| `{` / `}`                              | usar o volume anterior/seguinte como primeiro plano                                                                          |
| `clique duplo esquerdo`                | maximizar a visualização/restaurar o layout da visualização                                                                  |

### Visualizações 3D

Os atalhos a seguir estão disponíveis quando uma visualização 3D está ativa. Para ativar uma visualização, clique dentro dela: se você não quiser alterar nada na visualização, basta ativá-la e então fazer `clique direito` sem mover o mouse. Observe que simplesmente passar o mouse sobre uma visualização de corte não a ativará.

| Atalho                                           | Operação                                                                   |
| ------------------------------------------------ | -------------------------------------------------------------------------- |
| `Shift` + `mover o mouse`                        | mover a mira em todas as visualizações                                     |
| `clique esquerdo` + `arrastar`                   | rotacionar a visualização (`Alt` opcional, útil durante o posicionamento de pontos) |
| `seta esquerda` / `seta direita`                 | rotacionar a visualização                                                 |
| `seta cima` / `seta baixo`                       | rotacionar a visualização                                                 |
| `End` ou `Teclado numérico 1`                    | rotacionar para ver a partir do anterior                                 |
| `Shift` + `End` ou `Shift` + `Teclado numérico 1` | rotacionar para ver a partir do posterior                              |
| `Page Down` ou `Teclado numérico 3`              | rotacionar para ver a partir do lado esquerdo                            |
| `Shift` + `Page Down` ou `Shift` + `Teclado numérico 3` | rotacionar para ver a partir do lado direito                      |
| `Home` ou `Teclado numérico 7`                   | rotacionar para ver a partir do superior                                 |
| `Shift` + `Home` ou `Shift` + `Teclado numérico 7` | rotacionar para ver a partir do inferior                               |
| `Ctrl` + `clique esquerdo` + `arrastar`          | rotacionar a visualização no sentido horário/anti-horário                |
| `clique direito` + `arrastar cima/baixo`         | aproximar/afastar a visualização (`Alt` opcional, útil durante o posicionamento de pontos) |
| `Ctrl` + `roda do mouse`                         | aproximar/afastar a visualização                                         |
| `Ctrl` + `b`                                     | alternar o bloqueio de inclinação                                        |
| `+` / `-`                                        | aproximar/afastar a visualização                                         |
| `clique do meio` + `arrastar`                    | deslocar (transladar) a visualização (`Alt` opcional, útil durante o posicionamento de pontos) |
| `Shift` + `clique esquerdo` + `arrastar`         | deslocar (transladar) a visualização (`Alt` opcional, útil durante o posicionamento de pontos) |
| `Shift` + `seta esquerda` / `Shift` + `seta direita` | deslocar (transladar) a visualização                                |
| `Shift` + `seta cima` / `Shift` + `seta baixo`   | deslocar (transladar) a visualização                                     |
| `Shift` + `Teclado numérico 2` / `Shift` + `Teclado numérico 4` | deslocar (transladar) a visualização                       |
| `Shift` + `Teclado numérico 6` / `Shift` + `Teclado numérico 8` | deslocar (transladar) a visualização                       |
| `Teclado numérico 0` ou `Insert`                 | redefinir o zoom e o deslocamento, rotacionar para a visualização padrão mais próxima |
| `clique duplo esquerdo`                          | maximizar a visualização/restaurar o layout da visualização              |


Observação

Simulação caso os atalhos não estejam disponíveis no seu dispositivo:

- Mouse de um botão: em vez de `clique direito`, faça `Ctrl` + `clique`

- Trackpad: em vez de `clique direito`, faça `clique com dois dedos`

### Console Python

Os atalhos a seguir estão disponíveis no console Python.

| Atalho                     | Operação                                                                          |
| -------------------------- | --------------------------------------------------------------------------------- |
| `Tab`                      | autocompletar                                                                     |
| `seta cima` / `seta baixo` | histórico de comandos                                                            |
| `Esc`                      | limpar a seleção, voltar à linha de comando atual, limpar a linha de comando atual |
| `Ctrl` + `g`               | executar um script Python de um arquivo                                          |
| `Ctrl` + `v`               | colar um script Python da área de transferência e executá-lo                     |


Observe que, quando o código é colado em uma linha vazia, todo o código da área de transferência é executado *de uma só vez*. Se a linha de comando atual não estiver vazia, o código da área de transferência é colado no console e executado *linha por linha*. Quando o código é executado linha por linha, o comportamento é diferente, pois uma linha de entrada vazia fecha imediatamente o bloco atual, e a saída é impressa após a execução de cada linha.
