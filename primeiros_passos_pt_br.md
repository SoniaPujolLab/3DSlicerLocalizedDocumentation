# Primeiros passos

Boas-vindas à comunidade do 3D Slicer. Esta página contém as informações de que você precisa para começar a usar o 3D Slicer, incluindo como instalá-lo, como usar os recursos básicos e onde encontrar mais informações.

## Requisitos do sistema

O 3D Slicer roda em qualquer computador Windows, Mac ou Linux lançado nos últimos 5 anos. Computadores mais antigos podem funcionar (dependendo principalmente dos recursos gráficos).

O Slicer também pode rodar em máquinas virtuais e contêineres docker. Por exemplo, o [3D Slicer + notebook Jupyter em um navegador web](https://mybinder.org/v2/gh/Slicer/SlicerNotebooks/master?filepath=SlicerWeb.ipynb) está disponível gratuitamente pelo serviço Binder (sem necessidade de instalação; o aplicativo pode rodar em qualquer navegador web).

### Versões de sistema operacional

- Windows: Windows 11 com todas as atualizações recomendadas instaladas. A Microsoft não dá mais suporte ao Windows 10 (nem a versões anteriores) e o Slicer não é testado nessas versões legadas do sistema operacional, mas ainda pode funcionar.

- macOS: macOS Sonoma (14) ou posterior (sistemas baseados tanto em Intel quanto em ARM). Recomenda-se a versão pública mais recente.

- Linux: Ubuntu 22.04 ou posterior  
Debian 11 ou posterior  
Fedora 35 ou posterior  
AlmaLinux 8 ou posterior. Recomenda-se a versão LTS (suporte de longo prazo) mais recente.

### Configuração de hardware recomendada

- Memória: mais de 4 GB (recomenda-se 8 ou mais). Como regra geral, tenha 10 vezes mais memória do que a quantidade de dados que você carrega.

- Tela: resolução mínima de 1366 por 768 (recomenda-se 1920 por 1080 ou superior).

- Gráficos: recomenda-se hardware gráfico dedicado (GPU discreta) com memória própria para uma renderização de volume rápida.
GPU: os gráficos devem suportar no mínimo OpenGL 3.2. Uma placa de vídeo integrada é suficiente para visualização básica. Recomenda-se uma placa de vídeo discreta (como uma GPU NVidia) para a renderização de volume 3D interativa e a renderização rápida de cenas complexas. A memória de textura da GPU (VRAM) deve ser maior do que o seu maior conjunto de dados (por exemplo, ao trabalhar com dados de 2 GB, obtenha VRAM > 4 GB) e verifique se suas imagens cabem nas dimensões máximas de textura do hardware da sua GPU. Exceto a renderização, a maioria dos cálculos é realizada na CPU; portanto, ter uma GPU mais rápida geralmente não afeta a velocidade geral do aplicativo.

- Alguns cálculos no 3D Slicer são multithread e se beneficiam de configurações com vários núcleos e várias CPUs.

- Dispositivo de interface: recomenda-se um mouse de três botões com roda de rolagem. São suportados caneta, tela multitoque, touchpad e mesa digitalizadora. Todos os headsets de realidade virtual compatíveis com OpenVR são suportados para exibição em realidade virtual.

- Conexão com a internet para acessar extensões, pacotes Python, documentação on-line, conjuntos de dados de exemplo e tutoriais.

## Instalação do 3D Slicer

Para baixar o Slicer, clique [aqui](https://download.slicer.org/).

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_download.png)

**Observações:**

- A "Versão de pré-lançamento" do 3D Slicer (chamada de "Slicer Preview Release") é atualizada diariamente (o processo começa às 23h, horário do leste dos EUA, e leva algumas horas para ser concluído) e representa o desenvolvimento mais recente, incluindo novos recursos e correções. Não são fornecidas atualizações *contínuas* de extensões para as versões de pré-lançamento: as extensões disponíveis para uma versão de pré-lançamento correspondem à versão mais recente que estava disponível no momento em que essa versão foi criada. Para obter extensões atualizadas, é necessário instalar uma nova versão de pré-lançamento.

- A "Versão estável" do 3D Slicer (chamada de "Slicer Stable Release") geralmente é atualizada algumas vezes por ano e é testada com mais rigor. São fornecidas atualizações contínuas de extensões para a *última* Versão estável do Slicer, mas não para versões anteriores. Por exemplo, se a última Versão estável do Slicer for a Slicer-5.2.2 e o usuário tiver a Slicer-5.2.1 instalada, então o usuário não receberá mais nenhuma atualização de extensões. Para verificar se as versões mais recentes do aplicativo e das extensões estão instaladas, você pode ir ao módulo `Welcome` (Bem-vindo) e, na seção `Updates` (Atualizações), clicar no botão `Check now` (Verificar agora).

- Em geral, o Slicer é simples de instalar em todas as plataformas. É possível instalar várias versões do aplicativo na mesma conta de usuário sem que elas interfiram umas nas outras. Se você tiver problemas misteriosos com a instalação, pode tentar excluir os [arquivos de configuração do aplicativo](https://slicer.readthedocs.io/en/latest/user_guide/settings.html#settings-file-location).

- Apenas instaladores do Slicer de 64 bits estão disponíveis para download. Os desenvolvedores podem tentar compilar versões de 32 bits por conta própria, caso precisem rodar o Slicer em um sistema operacional de 32 bits. Dito isso, isso deve ser cuidadosamente considerado, pois muitas tarefas de pesquisa clínica, como o processamento de grandes conjuntos de dados volumétricos de TC ou RM, exigem mais memória do que um programa de 32 bits consegue acomodar.

Depois de baixado, siga as instruções abaixo para concluir a instalação:

### Windows

- Execute o instalador.

  * Limitação atual: o caminho de instalação deve conter apenas caracteres em inglês ([imprimíveis ASCII](https://en.wikipedia.org/wiki/ASCII#Printable_characters)), pois caso contrário alguns pacotes Python podem não carregar corretamente (consulte este [problema](https://github.com/Slicer/Slicer/issues/5383) para mais detalhes).

- Execute o Slicer pelo menu Iniciar do Windows.

- Use "Aplicativos e recursos" nas configurações do Windows para remover o aplicativo.

### Mac

- Abra o pacote de instalação (arquivo .dmg).

- Arraste o aplicativo Slicer (Slicer.app) para a sua pasta Aplicativos (ou outro local de sua escolha).

  * Esta etapa é necessária porque o conteúdo de um arquivo .dmg é aberto como um volume somente leitura, e não é possível instalar extensões ou pacotes Python em um volume somente leitura.

- Exclua a pasta Slicer.app para desinstalar.

Observação para instalar uma Versão de pré-lançamento: atualmente, os pacotes das versões de pré-lançamento não são assinados. Portanto, quando o aplicativo é iniciado pela primeira vez, a seguinte mensagem é exibida: "Slicer… não pode ser aberto porque é de um desenvolvedor não identificado". Para resolver esse erro, localize o aplicativo no Finder, clique com o botão direito (clique com dois dedos) e clique em `Open` (Abrir). Quando aparecer `This app can't be opened` (Este aplicativo não pode ser aberto), clique em cancelar. Clique novamente com o botão direito e escolha `Open` (Abrir) (sim, você precisa repetir o que fez antes; o resultado será diferente da primeira vez). Clique no botão `Open` (Abrir) ou `Open anyway` (Abrir mesmo assim) para iniciar o aplicativo. Veja mais explicações e técnicas alternativas [aqui](https://support.apple.com/en-my/guide/mac-help/mh40616/mac).

#### Instalação com o Homebrew

O Slicer pode ser instalado com um único comando de terminal usando o gerenciador de pacotes [Homebrew](https://brew.sh/):

```
brew install --cask slicer  # para instalar
brew upgrade slicer         # para atualizar
brew uninstall slicer       # para desinstalar

```

Este procedimento evita o típico processo de buscar no google, baixar, montar e arrastar para instalar aplicativos no macOS.

As versões de pré-lançamento podem ser instaladas usando [`homebrew-cask-versions`](https://github.com/Homebrew/homebrew-cask-versions):

```
brew tap homebrew/cask-versions     # precisa ser executado uma vez
brew install --cask slicer-preview  # para instalar
brew upgrade slicer-preview         # para atualizar
brew uninstall slicer-preview       # para desinstalar

```

### Linux

- Abra o arquivo compactado tar.gz e copie o diretório para o local de sua escolha.

- Pode ser necessário instalar pacotes adicionais, dependendo da distribuição e versão do Linux, conforme descrito nas subseções abaixo.

- Execute o arquivo executável `Slicer`.

- Remova o diretório para desinstalar.

**Observações:**

- Espera-se que o Slicer funcione na grande maioria das distribuições Linux de desktop e servidor. O sistema precisa fornecer pelo menos GLIBC 2.17 e GLIBCCC 3.4.19. Para mais detalhes, leia [aqui](https://www.python.org/dev/peps/pep-0599/#the-manylinux2014-policy).

- Obter argumentos de linha de comando e saídas de processos que contenham caracteres não ASCII exige que o sistema use uma localidade UTF-8. Se o sistema usar uma localidade diferente, o comando `export LANG="C.UTF-8"` pode ser usado antes de iniciar o aplicativo para mudar para uma localidade aceitável.

#### Ubuntu 24.04 (Noble Numbat)

```
sudo apt-get install libglu1-mesa libpulse-mainloop-glib0 libnss3 libasound2t64 qt5dxcb-plugin

```

#### Ubuntu 22.04 (Jammy Jellyfish), Debian 12 (bookworm), Debian 11 (bullseye)

```
sudo apt-get install libglu1-mesa libpulse-mainloop-glib0 libnss3 libasound2 qt5dxcb-plugin libsm6

```

Aviso

Usuários do Debian 10.12 podem encontrar um erro ao iniciar o Slicer:

```
Warning: Ignoring XDG_SESSION_TYPE=wayland on Gnome. Use QT_QPA_PLATFORM=wayland to run on Wayland anyway.
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

Available platform plugins are: xcb.

```

[A solução](https://forum.qt.io/topic/93247/qt-qpa-plugin-could-not-load-the-qt-platform-plugin-xcb-in-even-though-it-was-found/81) é criar um link simbólico para `libxcb-util.so` ou para `libxcb-util.so.0.0.0`, dependendo de qual biblioteca esteja presente. Assim, o comando deve ser:

```
sudo ln -s /usr/lib/x86_64-linux-gnu/libxcb-util.so /usr/lib/x86_64-linux-gnu/libxcb-util.so.1

```

ou:

```
sudo ln -s /usr/lib/x86_64-linux-gnu/libxcb-util.so.0.0.0 /usr/lib/x86_64-linux-gnu/libxcb-util.so.1

```

#### ArchLinux

Há pacotes contribuídos por usuários no [AUR](https://aur.archlinux.org/)

- [3dslicer-bin](https://aur.archlinux.org/packages/3dslicer-bin): este pacote reempacota o binário oficial por conveniência. Observe que o Slicer oficial é compilado com `Slicer_STORE_SETTINGS_IN_APPLICATION_HOME_DIR=ON` e instalado em `/opt`, onde um usuário sem privilégios de root não tem permissão de escrita; assim, o usuário não conseguirá instalar extensões nem atualizar as configurações do aplicativo.

- [3dslicer](https://aur.archlinux.org/packages/3dslicer): você pode compilar o pacote a partir do código-fonte usando este arquivo `PKGBUILD`, ou simplesmente instalá-lo a partir de um repositório não oficial: [repositório archlinuxcn](https://wiki.archlinux.org/title/Unofficial_user_repositories#archlinuxcn).

- [3dslicer-git](https://aur.archlinux.org/packages/3dslicer-git): igual ao [3dslicer](https://aur.archlinux.org/packages/3dslicer), mas usando o código-fonte mais recente.

#### Fedora 40, 39, 38, 37, 36, 35

Instale as dependências:

```
sudo dnf install mesa-libGLU mesa-libGL libnsl libXrender pulseaudio-libs-glib2 nss libXcomposite libXdamage libXrandr ftgl libXcursor libXi libXtst alsa-lib qt5-qtx11extras

```

Aviso

A biblioteca libcrypto.so.1.1 incluída na instalação do Slicer é incompatível com as bibliotecas do sistema usadas pelo Fedora 35. A correção, até que seja atualizada, é mover ou remover os arquivos libcrypto incluídos:

```
$SLICER_ROOT/lib/Slicer-5.xx/libcrypto.*

```

Se um clique duplo no aplicativo não o iniciar, tente os seguintes passos na ordem:

1. Verifique as permissões de execução do aplicativo

  - Clique com o botão direito no aplicativo → *Propriedades* → certifique-se de que **"Executável como um programa"** esteja marcado.

  - Ou verifique a partir de um terminal:

  
  

```
ls -la

```
        Você deverá ver algo como `-rwxr-xr-x` no início da linha referente ao executável.

            Observação

        Alguns gerenciadores de arquivos compactados (por exemplo, certas ferramentas `unrar`/`unzip`) podem exigir a execução da extração com `sudo` para restaurar as permissões de arquivo corretas.

        Se as permissões de execução estiverem ausentes, adicione-as com:

  
  

```
chmod +x Slicer

```

2. Inicie a partir do terminal

  
  

```
./Slicer

```

3. Se você receber o erro

  
  

```
error: Failed to obtain launcher executable name !

```
    tente mover o executável para a sua pasta *Software Home* e clicar duas vezes no aplicativo novamente. Ele deverá iniciar corretamente a partir de lá.

## Usando o Slicer

O 3D Slicer oferece muitos recursos e dá aos usuários grande flexibilidade sobre como usá-los. Como resultado, novos usuários podem se sentir sobrecarregados com o número de opções e ter dificuldade para descobrir como realizar até mesmo operações simples. Isso é normal, e muitos usuários superaram com sucesso essa etapa difícil investindo algum tempo em aprender a usar este software.

Como aprender o Slicer?

### Início rápido

Você pode tentar descobrir como o aplicativo funciona carregando conjuntos de dados e explorando o que é possível fazer.

#### Carregar dados

Abra o 3D Slicer e, usando o painel de Boas-vindas, carregue seus próprios dados ou baixe dados de exemplo para explorar. Os dados de exemplo costumam ser úteis para experimentar os recursos do 3D Slicer caso você não tenha dados próprios.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_load_data.png)

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_sample_data.png)

#### Visualizar dados

A aba Hierarquia de sujeitos (Subject hierarchy) do módulo Data mostra todos os conjuntos de dados da cena. Clique no ícone do "olho" para mostrar/ocultar um item em todas as visualizações.

Você pode personalizar as visualizações (mostrar o marcador de orientação, a régua, mudar a orientação, a transparência) clicando no alfinete no canto superior esquerdo do visualizador. Nos visualizadores de cortes, a barra horizontal pode ser usada para rolar pelos cortes ou selecionar um corte.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_view_controllers.png)

#### Processar dados

O 3D Slicer é construído sobre uma arquitetura modular. Escolha um módulo para processar ou analisar seus dados. Os módulos mais importantes são os seguintes (a lista completa está disponível na seção [Módulos](https://slicer.readthedocs.io/en/latest/user_guide/modules/index.html)):

- *Welcome* (Bem-vindo): o módulo padrão quando o 3D Slicer é iniciado. O painel apresenta opções para carregar dados e personalizar o 3D Slicer. Abaixo dessas opções há menus suspensos que contêm informações essenciais para usar o 3D Slicer.

- [Data](https://slicer.readthedocs.io/en/latest/user_guide/modules/data.html): atua como um hub central de organização de dados. Lista todos os dados atualmente na cena e permite operações básicas como buscar, renomear, excluir e mover.

- [DICOM](https://slicer.readthedocs.io/en/latest/user_guide/modules/dicom.html): importa e exporta objetos DICOM, como imagens, segmentações, conjuntos de estruturas, objetos de radioterapia, etc.

- [Volumes](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumes.html): usado para alterar a aparência de vários tipos de volumes.

- [Volume Rendering](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumerendering.html): fornece visualização interativa de dados de imagem 3D.

- [Segmentations](https://slicer.readthedocs.io/en/latest/user_guide/modules/segmentations.html): edita as propriedades de exibição e importa/exporta segmentações.

- [Segment Editor](https://slicer.readthedocs.io/en/latest/user_guide/modules/segmenteditor.html): segmenta volumes 3D usando diversas ferramentas manuais, semiautomáticas e automáticas.

- [Markups](https://slicer.readthedocs.io/en/latest/user_guide/modules/markups.html): permite criar e editar marcações associadas a uma cena.

- [Models](https://slicer.readthedocs.io/en/latest/user_guide/modules/models.html): carrega e ajusta os parâmetros de exibição dos modelos. Permite ao usuário alterar a aparência dos modelos de superfície 3D e organizá-los.

- [Transforms](https://slicer.readthedocs.io/en/latest/user_guide/modules/transforms.html): este módulo é usado para criar e editar matrizes de transformação. Você pode estabelecer essas relações movendo nós da lista Transformable para a lista Transformed, ou arrastando os nós sob os nós de Transformação no módulo Data.

#### Salvar dados

Todos os dados da cena podem ser salvos de uma vez usando o menu `File` (Arquivo) -> `Save data` (Salvar dados), ou conjuntos de dados selecionados podem ser exportados a partir do módulo `Data` clicando com o botão direito e selecionando `Export to file...` (Exportar para arquivo...) ou `Export to DICOM...` (Exportar para DICOM...). Os detalhes estão descritos na [seção de carregamento e salvamento de dados](https://slicer.readthedocs.io/en/latest/user_guide/data_loading_and_saving.html).

#### Extensões

O 3D Slicer oferece suporte a plug-ins chamados extensões. Uma extensão pode ser entendida como um pacote de distribuição que reúne um ou mais módulos do Slicer. Após instalar uma extensão, os módulos associados serão apresentados ao usuário como se fossem integrados. As extensões podem ser baixadas pelo gerenciador de extensões para instalar seletivamente os recursos úteis ao usuário final.

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_module_list.png)

![](https://github.com/Slicer/Slicer/releases/download/docs-resources/getting_started_extensions_manager.png)

Para mais detalhes sobre como baixar extensões, consulte a [documentação do Gerenciador de extensões](https://slicer.readthedocs.io/en/latest/user_guide/extensions.html#extensions-manager).
Clique [aqui](https://www.slicer.org/wiki/Documentation/Nightly/ModuleExtensionListing/Extensions_by_category) para ver uma lista completa de extensões. Os links na página fornecem documentação de cada extensão.

O Slicer é extensível. Se você tiver interesse em personalizar ou adicionar funcionalidades ao Slicer, clique [aqui](https://training.slicer.org/#developer-tutorials).

### Tutoriais

Aprenda tanto conceitos básicos quanto fluxos de trabalho altamente especializados a partir dos inúmeros tutoriais passo a passo e em vídeo disponíveis.

Experimente o [Tutorial de boas-vindas](https://training.slicer.org/#stc-gen-101-welcome-tutorial) e o [Tutorial de carregamento de dados e visualização 3D](https://training.slicer.org/#stc-vis-102-data-loading-and-3d-visualization) para aprender o básico.

Para mais tutoriais, visite a [página de tutoriais](https://training.slicer.org/).

### Manual do usuário

Navegue pela seção [Interface de usuário](https://slicer.readthedocs.io/en/latest/user_guide/user_interface.html) para encontrar uma visão geral rápida da interface do aplicativo, ou pela seção [Módulos](https://slicer.readthedocs.io/en/latest/user_guide/modules/index.html) para uma descrição detalhada de cada módulo.

### Pedir ajuda

O 3D Slicer existe há muitos anos e muitas perguntas já foram feitas e respondidas sobre ele. Se você tiver alguma dúvida, pode começar com uma busca na web; por exemplo, pesquise no Google `slicer load jpg` para descobrir como importar uma pilha de imagens jpg.

O aplicativo tem uma comunidade de usuários grande, muito simpática e prestativa. Temos pessoas que ficarão felizes em ajudar com perguntas simples, como fazer uma tarefa específica no Slicer, e contamos com um grande número de especialistas em engenharia e medicina que podem aconselhá-lo sobre como resolver problemas complexos.

**Se você tiver alguma dúvida, vá ao [fórum do Slicer](https://discourse.slicer.org) e pergunte para nós!**

## Glossário

Os termos usados nos diversos campos da computação de imagens médicas e biomédicas e das imagens clínicas nem sempre são consistentes. Esta seção define termos de uso comum no 3D Slicer, especialmente aqueles que podem ter um significado diferente em outros contextos.

- **Bounds (limites)**: descreve a caixa delimitadora de um objeto espacial ao longo de 3 eixos. No VTK, é definido por 6 valores de ponto flutuante: `X_min`, `X_max`, `Y_min`, `Y_max`, `Z_min`, `Z_max`.

- **Brilho/contraste**: especifica o mapeamento linear dos valores de voxel para o brilho de um pixel exibido. O brilho é o deslocamento linear e o contraste é o multiplicador. Em imagens médicas, esse mapeamento linear é mais comumente especificado por valores de janela/nível (window/level).

- **Cell (célula)**: as células de dados são elementos topológicos simples das malhas, como linhas, polígonos, tetraedros, etc.

- **Legenda de cores** (ou barra de cores, barra escalar): um widget sobreposto aos cortes ou às visualizações 3D que exibe uma legenda de cores, indicando o significado das cores.

- **Sistema de coordenadas** (ou referencial de coordenadas, referencial, espaço): especificado pela posição da origem, pelas direções dos eixos e pela unidade de distância. Todos os sistemas de coordenadas no 3D Slicer são destros (de mão direita).

- **Extension (extensão)** (ou extensão do Slicer): uma coleção de módulos que não vem incluída no aplicativo principal, mas que pode ser baixada e instalada usando o Gerenciador de extensões.

- [**Gerenciador de extensões**](https://slicer.readthedocs.io/en/latest/user_guide/extensions.html#extensions-manager): um componente de software do Slicer que permite navegar, instalar e desinstalar extensões do [Catálogo de extensões (também conhecido como a loja de aplicativos do Slicer)](https://extensions.slicer.org) diretamente do aplicativo.

- [**Índice de extensões**](https://github.com/Slicer/ExtensionsIndex): um repositório que contém a descrição de cada extensão a partir da qual o Catálogo de extensões é construído.

- **Extent (extensão espacial)**: intervalo de coordenadas inteiras ao longo de 3 eixos. No VTK, é definido por 6 valores, para os eixos IJK: `I_min`, `I_max`, `J_min`, `J_max`, `K_min`, `K_max`. Tanto os valores mínimos quanto os máximos são inclusivos, portanto o tamanho de um vetor é `(I_max - I_min + 1)` x `(J_max - J_min + 1)` x `(K_max - K_min + 1)`.

- **Fiducial (marcador fiducial)**: representa um ponto no espaço 3D. O termo tem origem na cirurgia guiada por imagem, onde "marcadores fiduciais" são usados para marcar posições de pontos.

- **Frame (quadro)**: um ponto temporal em uma sequência de tempo. Para evitar ambiguidade, este termo não é usado para se referir a um corte de um volume.

- **Geometria**: especifica a localização e a forma de um objeto no espaço 3D. Consulte o termo "Volume" para a definição da geometria da imagem.

- **Intensidade de imagem**: normalmente refere-se ao valor de um voxel. O brilho e a cor do pixel exibido são calculados a partir desse valor com base na janela/nível escolhidos e na tabela de busca de cores.

- **IJK**: eixos do sistema de coordenadas de voxels. Os valores de coordenadas inteiros correspondem às posições dos centros dos voxels. Os valores IJK costumam ser usados como valores de coordenadas para designar um elemento dentro de um vetor 3D. Por convenção do VTK, I indexa a coluna, J indexa a linha e K indexa o corte. Observe que o numpy usa a convenção de ordenação oposta, onde `a[K][J][I]`. Às vezes, essa disposição de memória é descrita como I sendo o índice de variação mais rápida e K o de variação mais lenta.

- **ITK**: [Insight Toolkit](https://itk.org/). Biblioteca de software que o Slicer usa para a maioria das operações de processamento de imagens.

- **Labelmap (mapa de rótulos)** (ou volume de mapa de rótulos, nó de volume de mapa de rótulos): nó de volume que possui valores de voxel discretos (inteiros). Normalmente, cada valor corresponde a uma estrutura ou região específica. Isso permite uma representação compacta de regiões não sobrepostas em um único vetor 3D. A maioria dos softwares usa um único mapa de rótulos para armazenar uma segmentação de imagem, mas o Slicer usa um nó de segmentação dedicado, que pode conter múltiplas representações (vários mapas de rótulos para permitir o armazenamento de segmentos sobrepostos; representação de superfície fechada para uma visualização 3D rápida, etc.).

- **LPS**: sistema de coordenadas anatômicas esquerda-posterior-superior (left-posterior-superior). É o sistema de coordenadas mais usado na computação de imagens médicas. O Slicer armazena todos os dados em disco no sistema de coordenadas LPS (e os converte de/para RAS ao gravar ou ler do disco).

- **Markups (marcações)**: objetos geométricos simples e medições que o usuário pode posicionar nos visualizadores. O [módulo Markups](https://slicer.readthedocs.io/en/latest/user_guide/modules/markups.html) pode ser usado para criar tais objetos. Há vários tipos, como lista de pontos, linha, curva, plano e ROI.

- **Volume de origem (source volume)**: os valores de voxel deste volume são usados durante a segmentação pelos efeitos que dependem da intensidade de um volume subjacente.

- **MRML**: [Medical Reality Markup Language](https://en.wikipedia.org/wiki/Medical_Reality_Markup_Language): biblioteca de software para armazenamento, visualização e processamento de objetos de informação que podem ser usados em aplicações médicas. A biblioteca foi projetada para ser reutilizável em diversos aplicativos de software, mas o 3D Slicer é o único aplicativo importante que se sabe que a utiliza.

- **Model (modelo)** (ou nó de modelo): nó MRML que armazena uma malha de superfície (composta por células 2D como triângulos, polígonos, etc.) ou uma malha volumétrica (composta por células 3D como tetraedros, cunhas, etc.).

- **Module (módulo)** (ou módulo do Slicer): um módulo do Slicer é um componente de software que consiste em uma interface gráfica de usuário (exibida no painel do módulo quando ele é selecionado), uma lógica (que implementa algoritmos que operam sobre nós MRML) e que pode fornecer novos tipos de nós MRML, gerenciadores exibíveis (responsáveis por exibir esses nós nas visualizações), plug-ins de entrada/saída (responsáveis por carregar/salvar nós MRML em arquivos) e diversos outros plug-ins. Os módulos costumam ser independentes e se comunicam entre si apenas modificando nós MRML, mas às vezes um módulo usa recursos fornecidos por outros módulos chamando métodos de sua lógica.

- **Node (nó)** (ou nó MRML): um objeto de dados na cena. Um nó pode representar dados (como uma imagem ou uma malha), descrever como eles são exibidos (cor, opacidade, etc.), ser armazenado em disco, as transformações espaciais aplicadas sobre eles, etc. Existe uma hierarquia de classes em C++ que define os comportamentos comuns dos nós, como a propriedade de poder ser armazenado em disco ou de poder ser transformado geometricamente. A estrutura dessa hierarquia de classes pode ser inspecionada no código ou na [documentação da API](https://apidocs.slicer.org/main/classvtkMRMLStorableNode.html).

- **Marcador de orientação**: marcador em forma de seta, caixa ou figura humana para mostrar as direções dos eixos nos cortes e nas visualizações 3D.

- **RAS**: sistema de coordenadas anatômicas direita-anterior-superior (right-anterior-superior). Sistema de coordenadas usado internamente no Slicer. Pode ser convertido de/para o sistema de coordenadas LPS invertendo a direção dos dois primeiros eixos.

- **Reference (referência)**: não tem um significado específico, mas normalmente se refere a uma entrada secundária (objeto de dados, referencial de coordenadas, geometria, etc.) para uma operação.

- **Região de interesse (ROI)**: especifica uma região em forma de caixa em 3D. Pode ser usada para recortar volumes, recortar modelos, etc.

- **Registration (registro)**: o processo de alinhar objetos no espaço. O resultado do registro é uma transformação, que transforma o objeto "móvel" para coincidir com o objeto "fixo".

- **Resolução**: tamanho do voxel de um volume, normalmente especificado em mm/pixel. Raramente é usado na interface de usuário porque seu significado é um pouco enganoso: um valor de resolução alto significa um espaçamento grande, o que significa uma resolução de imagem baixa (grosseira).

- **Ruler (régua)**: pode se referir a: 1. Régua da visualização: a linha exibida como sobreposição nos visualizadores para servir como referência de tamanho. 2. Linha de markups: ferramenta de medição de distância.

- **Componente escalar**: um elemento de um vetor. O número de componentes escalares é o comprimento do vetor.

- **Valor escalar**: um número simples. Normalmente de ponto flutuante.

- **Scene (cena)** (ou cena MRML): é a estrutura de dados que contém todos os dados atualmente carregados no aplicativo e informações adicionais sobre como eles devem ser exibidos ou usados. O termo tem origem na [computação gráfica](https://en.wikipedia.org/wiki/Rendering_(computer_graphics)).

- **Segment (segmento)**: corresponde a uma única estrutura em uma segmentação. Veja mais informações na seção [Segmentação de imagens](https://slicer.readthedocs.io/en/latest/user_guide/image_segmentation.html).

- **Segmentation (segmentação)** (também conhecida como contorno, anotação; região de interesse, conjunto de estruturas, máscara): processo de delinear estruturas 3D em imagens. A segmentação também pode se referir ao nó MRML que é o resultado do processo de segmentação. Um nó de segmentação normalmente contém múltiplos segmentos (cada segmento corresponde a uma estrutura 3D). Os nós de segmentação não são nós de mapa de rótulos nem nós de modelo, mas podem armazenar múltiplas representações (mapa de rótulos binário, superfície fechada, etc.). Veja mais informações na seção [Segmentação de imagens](https://slicer.readthedocs.io/en/latest/user_guide/image_segmentation.html).

- **Slice (corte)**: interseção de um objeto 3D com um plano.

- **Anotações da visualização de corte**: texto no canto dos cortes que exibe o nome e as etiquetas DICOM selecionadas dos volumes exibidos.

- **Spacing (espaçamento)**: tamanho do voxel de um volume, normalmente especificado em mm/pixel.

- **Transform (transformação)**: pode transformar qualquer objeto 3D de um sistema de coordenadas para outro. O tipo mais comum é a transformação rígida, que pode mudar a posição e a orientação de um objeto. As transformações lineares podem escalar, espelhar e cisalhar objetos. As transformações não lineares podem deformar arbitrariamente o espaço 3D. Para exibir um volume no sistema de coordenadas do mundo, o volume precisa ser reamostrado, portanto é necessária uma transformação *do* sistema de coordenadas do mundo *para* o volume (chamada de transformação de reamostragem). Para transformar todos os outros tipos de nós para o sistema de coordenadas do mundo, todos os pontos precisam ser transformados *para* o sistema de coordenadas do mundo (transformação de modelagem). Como um nó de transformação deve poder ser aplicado a qualquer nó, os nós de transformação podem fornecer tanto a transformação *de* quanto *para* o nó pai (armazenam uma e calculam a outra em tempo real).

- **Volume (volume)** (ou nó de volume, volume escalar, imagem): nó MRML que armazena um vetor 3D de voxels. Os índices do vetor costumam ser chamados de IJK. O intervalo de coordenadas IJK é chamado de extents. A geometria do volume é especificada por sua origem (posição do ponto IJK=(0,0,0)), seu espaçamento (tamanho de um voxel ao longo dos eixos I, J, K), as direções dos eixos (direção dos eixos I, J, K no sistema de coordenadas de referência) em relação a um referencial. Imagens 2D são volumes 3D de corte único, com sua posição e orientação especificadas no espaço 3D.

- [**Voxel**](https://en.wikipedia.org/wiki/Voxel): um elemento de um volume 3D. Tem formato de prisma retangular. As coordenadas de um voxel correspondem à posição do seu ponto central. O valor de um voxel pode ser um valor escalar simples ou um vetor.

- **VR**: abreviação que pode se referir a volume rendering (renderização de volume) ou a virtual reality (realidade virtual). Para evitar ambiguidade, geralmente recomenda-se usar o termo completo (ou definir explicitamente o significado da abreviação no contexto dado).

- **VTK**: [Visualization Toolkit](https://vtk.org/). Biblioteca de software que o Slicer usa para a representação e a visualização de dados. Como a maioria das classes do Slicer deriva de classes do VTK e usa intensamente outras classes do VTK, o Slicer adotou muitas convenções do estilo e da interface de programação de aplicações do VTK.

- **Window/level (janela/nível)** (ou largura de janela/nível de janela): especifica o mapeamento linear dos valores de voxel para o brilho de um pixel exibido. A janela (window) é o tamanho do intervalo de intensidade que é mapeado para todo o intervalo de intensidade exibível. O nível (level) é o valor de voxel que é mapeado para o centro de todo o intervalo de intensidade exibível.
