# Obter ajuda

[Entre em contato com a comunidade do Slicer ou com os parceiros comerciais](https://slicer.readthedocs.io/en/latest/user_guide/about.html#contact-us) se você tiver alguma pergunta, relato de bug ou solicitação de melhoria, seguindo as diretrizes descritas abaixo.

## Preciso de ajuda para usar o Slicer

- Você pode começar digitando sua pergunta na busca web do Google. Há uma boa chance de que sua pergunta já tenha sido feita e respondida antes, pois todas as perguntas já feitas sobre o Slicer estão disponíveis publicamente e indexadas pelo Google. As fontes de informação mais atualizadas são o [fórum do Slicer](https://discourse.slicer.org) e a [documentação do Slicer no Read the Docs](https://slicer.readthedocs.io/). O Google pode encontrar discussões mais antigas nas antigas listas de e-mail e páginas wiki do Slicer, que podem ou não ser exatamente precisas para a versão atual do Slicer, mas que ainda podem oferecer dicas úteis.

- Faça o seu melhor para resolver o problema lendo a [documentação](https://slicer.readthedocs.io), o [portfólio de materiais de treinamento](https://training.slicer.org/) e verificando os registros de erros (na barra de menus do aplicativo: View->Error log).

- Se você ainda não tiver certeza do que fazer: [faça uma pergunta no fórum do Slicer](https://discourse.slicer.org). Além de descrever a pergunta específica, ajuda se você descrever o contexto da sua pergunta (quem você é, no que está trabalhando, por que isso é importante, qual é o objetivo geral do seu projeto). Saber mais sobre você e seu projeto aumenta a chance de que alguém se voluntarie para responder à pergunta, e você pode obter uma resposta mais relevante.

## Quero relatar um problema

Estamos constantemente fazendo correções e melhorias, portanto, antes de relatar qualquer problema:

1. Confirme que o problema ainda existe na Versão estável atual do Slicer.

2. Se ele ainda existir na Versão estável do Slicer, confirme que o problema ainda existe na última Versão de pré-lançamento do Slicer.

Se você tiver dificuldade para encontrar respostas usando o recurso de busca do [fórum do Slicer](https://discourse.slicer.org) ou por meio de buscas na internet como o Google, experimente um modelo de linguagem grande como Microsoft Copilot, OpenAI ChatGPT, Google Gemini, etc.

Se você não tiver certeza se o Slicer está se comportando de forma incorreta ou se você não está usando-o corretamente, então [pergunte sobre isso no fórum do Slicer](https://discourse.slicer.org/c/support) (na categoria `Support`).
Se você tiver *certeza* de que o Slicer não está funcionando como deveria, então [envie um relato de bug no rastreador de problemas do Slicer](https://github.com/Slicer/Slicer/issues/new?assignees=&labels=type%3Abug&template=bug_report.md).

Na sua pergunta ou relato, forneça todas as informações descritas no [modelo de relato de bug](https://github.com/Slicer/Slicer/blob/main/.github/ISSUE_TEMPLATE/bug_report.md#summary).

Dica

Não seja anônimo: pessoas reais que se esforçam para resolver problemas reais têm mais chances de receber ajuda valiosa. Se você falar sobre você e seu projeto, ele pode receber mais atenção e o problema pode ser resolvido mais cedo.

## Gostaria de solicitar uma melhoria ou um novo recurso

Primeiro, pesquise no [fórum do Slicer](https://discourse.slicer.org) e no [rastreador de problemas do Slicer](https://github.com/Slicer/Slicer/issues?q=is%3Aissue+is%3Aopen+label%3Atype%3Aenhancement) para ver se alguém já solicitou esse recurso. Se você encontrar uma solicitação muito parecida, avise-nos de que você também tem interesse adicionando um comentário e/ou um "joinha" (thumbs-up) à publicação principal.

Se você não encontrar uma solicitação de recurso semelhante, escreva uma publicação na [categoria de solicitações de recursos](https://discourse.slicer.org/c/support/feature-requests) para discuti-la com os desenvolvedores do Slicer e os membros da comunidade.

Dica

Se você escrever sobre você e seu projeto, há uma chance maior de que sua solicitação seja trabalhada. Descreva que tipo de ajuda você pode oferecer para a implementação (seu próprio tempo, financiamento, etc.).

## Gostaria de informar à comunidade do Slicer como o Slicer me ajudou na minha pesquisa

Envie-nos a citação do seu artigo publicando-a na [categoria Community do fórum do Slicer](https://discourse.slicer.org/c/community/).

Contexto: o financiamento do Slicer é fornecido por meio de mecanismos competitivos, principalmente pelo governo dos Estados Unidos e, em menor grau, por meio de financiamento de outros governos. A justificativa para esses recursos é que o Slicer viabiliza o trabalho científico. Conhecer as publicações científicas viabilizadas pelo Slicer é uma etapa fundamental nesse processo. Dada a natureza internacional da comunidade do Slicer, a nacionalidade dos cientistas não é importante. Cada bom artigo conta.

## Solução de problemas

### O aplicativo Slicer não inicia

- A CPU ou os recursos gráficos do seu computador podem não atender aos [requisitos mínimos do sistema](https://slicer.readthedocs.io/en/latest/user_guide/getting_started.html#system-requirements).

  * Atualizar o driver da sua placa de vídeo pode resolver alguns problemas, mas se isso não ajudar e você tiver um computador antigo, talvez seja necessário atualizar para um computador de fabricação mais recente ou mudar para um renderizador por software.
Um renderizador por software é particularmente útil para rodar o Slicer em uma máquina sem tela (headless), como uma máquina virtual em um provedor de computação em nuvem com uma CPU potente, mas sem GPU, usando o Protocolo de Área de Trabalho Remota (RDP).

            Observação

        **Configuração de um renderizador por software no Windows:**

    +             Baixe o driver Mesa OpenGL em <https://github.com/pal1000/mesa-dist-win/releases> (versão MSVC: mesa3d-X.Y.Z-release-msvc.7z). Última vez testado com a versão <https://github.com/pal1000/mesa-dist-win/releases/tag/22.2.0>

    +             Extraia o arquivo compactado e copie os arquivos da pasta x64 para a subpasta bin da árvore de instalação do Slicer.

    +             Configure o renderizador definindo variáveis de ambiente e, em seguida, inicie o Slicer:

  
  

```
set GALLIUM_DRIVER=llvmpipe
set MESA_GL_VERSION_OVERRIDE=3.3COMPAT
Slicer.exe

```

        Este renderizador por software foi testado e funciona bem em máquinas virtuais Windows no Microsoft Azure.

- O Slicer pode não funcionar se estiver instalado em uma pasta que tenha caracteres especiais no nome. Tente instalar o Slicer em um caminho que contenha apenas letras latinas e números (a-z, 0-9).

- As configurações do seu Slicer podem ter sido corrompidas.

  * Tente iniciar o Slicer usando `Slicer.exe --disable-settings` (se isso resolver o problema, exclua os arquivos Slicer.ini e Slicer-.ini do diretório de configurações do seu Slicer).    * Renomeie ou remova o diretório de configurações do seu Slicer (por exemplo, `c:\Users\<seunomedeusuario>\AppData\Roaming\slicer.org`). Veja as instruções para obter o diretório de configurações [aqui](https://slicer.readthedocs.io/en/latest/user_guide/settings.html#settings-file-location). Tente iniciar o Slicer.

    * Pode haver bibliotecas conflitantes ou incompatíveis no caminho do seu sistema (provavelmente causadas pela instalação de aplicativos que colocam bibliotecas em locais incorretos no seu sistema). Verifique os registros do seu sistema para obter detalhes e relate o problema.

      +                 No Windows:

        - Inicie o Visualizador de Eventos (eventvwr.exe), selecione Logs do Windows / Aplicativo e encontre o erro do aplicativo. Se houver um problema de carregamento de uma DLL, aparecerá uma linha semelhante a esta: `Faulting module path: <algo>.dll`. Se você encontrou uma linha semelhante a esta, tente a seguinte solução alternativa: inicie uma janela de comandos. Digite `set path=` para limpar a variável de caminho. Digite Slicer.exe para iniciar o Slicer. Se o Slicer iniciar com sucesso, então você precisa remover os itens desnecessários do caminho do sistema (ou excluir as bibliotecas instaladas em locais incorretos).

        - Se o Slicer ainda não funcionar, colete mais algumas informações e relate o problema:

          * Obtenha informações sobre as dependências de DLL usando a ferramenta Dependency Walker:

            +                             Baixe o depends.exe [aqui](https://www.dependencywalker.com/)

            +                             Execute o depends.exe usando o inicializador do Slicer: `Slicer.exe --launch path\to\depends.exe "bin\SlicerApp-real.exe"`

            +                             No Dependency Walker: certifique-se de que os caminhos completos das DLLs sejam mostrados (clique em View / Full paths se você só vir os nomes das DLLs). Use File / Save as… => Comma Separated Values (*.csv) para salvar os logs em um arquivo.

          * Habilite o registro de carregamento de processos usando a ferramenta sxstrace, inicie o Slicer e salve o arquivo de log (veja as instruções [aqui](https://technet.microsoft.com/en-ca/library/hh875651.aspx))

      +                 No Linux:

        - Algumas versões do Linux exigem compilar o seu próprio kerberos e openssl, conforme [descrito e acompanhado neste problema](https://github.com/Slicer/Slicer/issues/5663).
