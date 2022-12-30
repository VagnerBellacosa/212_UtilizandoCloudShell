

- [Cloud Shell ](https://cloud.google.com/shell)
- [Documentação ](https://cloud.google.com/shell/docs)
- [Guias](https://cloud.google.com/shell/docs/quickstart)

Isso foi útil?



Envie comentários

# Iniciar o Cloud Shell

bookmark_border



Uma sessão do Cloud Shell pode ser iniciada de diferentes maneiras para melhor atender seu caso de uso.

## Iniciar no Console do Google Cloud

Para iniciar uma sessão do Cloud Shell no Console do Google Cloud, clique em ![Botão &quot;Ativar shell&quot;](https://cloud.google.com/static/shell/docs/images/activate_cloud_shell.svg) **Ativar o Cloud Shell** no [Console do Google Cloud](http://console.cloud.google.com/). Isso inicia uma sessão no painel inferior do Console do Google Cloud.

Você também pode transferir essa sessão para uma experiência em tela cheia clicando em ![Botão &quot;Abrir em uma nova janela&quot;](https://cloud.google.com/static/shell/docs/images/open-new-tab.png) **Abrir em uma nova janela**.

## Iniciar uma sessão independente

Se preferir uma sessão independente, inicie uma sessão do Cloud Shell com [shell.cloud.google.com](https://shell.cloud.google.com/). O terminal do Cloud Shell e o Editor do Cloud Shell são iniciados automaticamente para você.

Para abrir apenas o editor do Cloud Shell, use [ide.cloud.google.com](https://ide.cloud.google.com/). Ainda é possível acessar o terminal do Cloud Shell a qualquer momento usando o botão "Abrir terminal" ![Botão &quot;Ativar shell&quot;](https://cloud.google.com/static/shell/docs/images/activate_cloud_shell.svg) na barra de menus do Cloud Shell.

## Iniciar na documentação

Após iniciar seu [teste gratuito](https://console.cloud.google.com/freetrial), você encontrará ![Botão &quot;Ativar o Cloud Shell&quot;](https://cloud.google.com/static/shell/docs/images/activate-cloud-shell-button.svg) **Ativar o Cloud Shell** no cabeçalho da página de documentação em que você está.

![Terminal do Cloud Shell iniciado na metade inferior da página de documentação com um exemplo de comando do gcloud copiado para o terminal do Cloud Shell](https://cloud.google.com/static/shell/docs/images/launch-within-docs.png)

Esse botão inicia o Cloud Shell como um painel na parte inferior da página atual. Você pode testar o produto que está lendo, mantendo a documentação dele no contexto.

O terminal do Cloud Shell vem com a CLI gcloud, o Docker, o Terraform e [outros utilitários de linha de comando](https://cloud.google.com/shell/docs/how-cloud-shell-works#tools) pré-instalados e autentica automaticamente você com suas credenciais do Google para que possa usar o terminal para executar a amostra de código na documentação. Isso significa que é possível ativar e testar as APIs do Cloud, iniciar operações de longa duração e gerenciar os recursos do Google Cloud na linha de comando sem sair da documentação.

## Iniciar com um link "Abrir no Cloud Shell"

Se você quiser que os usuários testem seu projeto ou amostras de código sem precisar fazer o download da CLI gcloud ou instalar dependências, use o recurso [Abrir no Cloud Shell](https://cloud.google.com/shell/docs/open-in-cloud-shell) (OiCS). Ele permite que você construa e publique um URL que executa automaticamente determinadas ações após a inicialização do Cloud Shell, como clonar um repositório Git ou abrir um tutorial. Essa opção tem a vantagem adicional de permitir que você personalize a experiência iniciada do Cloud Shell com suporte para a inclusão de parâmetros de URL ao criar um link OiCS.

## Iniciar e se conectar localmente ao Cloud Shell com a CLI gcloud

Se você quiser interagir com o ambiente do Cloud Shell e se conectar usando uma linha de comando local, precisará [instalar a CLI gcloud](https://cloud.google.com/sdk/install). Usando a CLI gcloud, especificamente o grupo de comandos [`gcloud cloud-shell`](https://cloud.google.com/sdk/gcloud/reference/cloud-shell), é possível copiar arquivos entre a máquina local e o ambiente do Cloud Shell e estabelecer uma sessão SSH interativa com o Cloud Shell.

# Usar o Cloud Shell

bookmark_border



Nesta página, descrevemos como iniciar e configurar uma nova sessão do Cloud Shell.

## Iniciar uma nova sessão

Clique em ![img](https://cloud.google.com/static/shell/docs/images/activate-cloud-shell-button.svg) **Ativar o Cloud Shell** na parte superior do Console do Google Cloud.

Uma sessão do Cloud Shell é aberta em um novo frame na parte inferior do Console do Google Cloud e exibe um prompt de linha de comando. Pode levar alguns segundos para que a sessão seja inicializada.

### Usar o terminal

O Cloud Shell fornece acesso de linha de comando à instância de máquina virtual em uma janela do terminal que é aberta no Console do Google Cloud.

Além de acessar a [Google Cloud CLI](https://cloud.google.com/sdk/gcloud) e outros utilitários na linha de comando, você pode usar o comando `cloudshell` para iniciar tutoriais, abrir o editor do Cloud Shell e fazer o download de arquivos.

Consulte o guia sobre como usar o [Terminal do Cloud Shell](https://cloud.google.com/shell/docs/use-cloud-shell-terminal) para mais detalhes.

### Usar o editor do Cloud Shell

O editor de código interno oferece a conveniência de exibir e editar arquivos no mesmo ambiente em que os projetos são criados e implantados. Inicie o editor do Cloud Shell clicando em ![Botão &quot;Editor de código&quot;](https://cloud.google.com/static/code/docs/shell/images/open-editor.png) **Abrir editor** na barra de ferramentas da janela do Cloud Shell.

Para mais informações, consulte [Visão geral da interface do editor do Cloud Shell](https://cloud.google.com/shell/docs/editor-overview).

### Escolher o modo temporário

Por padrão, o Cloud Shell provisiona 5 GB de armazenamento permanente em disco na sua máquina virtual alocada temporariamente. Este é seu diretório `$HOME`. Quando você usa a experiência padrão do Cloud Shell, os arquivos no diretório principal permanecem entre as sessões.

Se você não precisar do armazenamento permanente, use o Cloud Shell no modo efêmero. No modo temporário, é possível começar a usar o Cloud Shell mais rapidamente porque há menos configuração e não há anexo ou arquivo de disco. No entanto, isso significa que todos os arquivos que você criar durante a sessão do modo temporário serão excluídos com a VM quando a sessão terminar.

Para escolher o modo temporário, anexe `ephemeral=true` ao URL ou abra o menu ![Ícone do menu Mais](https://cloud.google.com/static/shell/docs/images/more.svg) **Mais** do Cloud Shell, selecione **Modo temporário** e clique em **Salvar**.

Para definir o modo temporário como padrão do Cloud Shell, ative a opção **Sempre iniciar o Cloud Shell no modo temporário** antes de clicar em **Salvar**.

### Ajustar a janela de exibição

Para ajustar a janela de exibição, siga estas etapas:

1. Clique em ![Botão para ocultar o Shell](https://cloud.google.com/static/shell/docs/images/hide-button.png) **Ocultar** ou ![Botão para restaurar o Shell](https://cloud.google.com/static/shell/docs/images/restore-button.png) **Restaurar** para ocultar ou restaurar a exibição da sessão.
2. Clique em ![Botão para desanexar o Shell](https://cloud.google.com/static/shell/docs/images/detach-button.png) **Abrir sessão em uma nova janela** para desanexar a sessão como uma nova janela.
3. Para fechar a janela desanexada e reabrir a sessão no Console do Google Cloud, clique em ![img](https://cloud.google.com/static/shell/docs/images/activate-cloud-shell-button.svg) **Ativar o Cloud Shell** na parte superior da janela do Console do Google Cloud.
4. Para alternar entre temas, clique em ![Botão &quot;Configurações&quot;](https://cloud.google.com/static/shell/docs/images/settings-button.png) **Configurações** e **Alterar para tema claro** ou **Alternar para tema escuro**.

## A seguir

Agora que você já conhece a configuração do Cloud Shell, pode começar a usar as [ferramentas e comandos pré-instalados](https://cloud.google.com/shell/docs/how-cloud-shell-works#tools) da linha de comando. Também é possível instalar outras ferramentas no [diretório principal](https://cloud.google.com/shell/docs/how-cloud-shell-works#persistent_disk_storage) no armazenamento em disco permanente, conforme necessário.

- [Saiba como usar a visualização da Web](https://cloud.google.com/shell/docs/using-web-preview)
- [Veja exemplos do que pode ser feito no Cloud Shell](https://cloud.google.com/shell/docs/quickstart)