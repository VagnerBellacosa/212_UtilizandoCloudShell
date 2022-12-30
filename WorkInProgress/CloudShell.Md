# Para começar com o Cloud Shell e a gcloud

45 minutos1 crédito

## GSP002

![Laboratórios autoguiados do Google Cloud](https://cdn.qwiklabs.com/GMOHykaqmlTHiqEeQXTySaMXYPHeIvaqa2qHEzw6Occ%3D)

## Visão geral

O Cloud Shell dá acesso de linha de comando a recursos de computação hospedados no Google Cloud. Ele é uma máquina virtual baseada em Debian com um diretório principal permanente de 5 GB, que facilita o gerenciamento dos projetos e recursos do Google Cloud. A ferramenta de linha de comando `gcloud` e outros utilitários necessários já vêm instalados no Cloud Shell, o que permite começar o trabalho de imediato.

Neste laboratório prático, você vai aprender a se conectar aos recursos de computação hospedados no Google Cloud usando a ferramenta `gcloud` do Cloud Shell.

Recomendamos que os próprios alunos digitem os comandos para reforçar os principais conceitos. Muitos laboratórios vão incluir um bloco de código com os comandos necessários. Você pode copiá-los desse bloco e colar nos locais apropriados durante o laboratório.

### Atividades do laboratório

- Usar os comandos `gcloud`
- Conectar-se a serviços do Compute hospedados no Google Cloud

### Pré-requisitos

- Conhecer os editores de texto padrão do Linux, como `vim`, `emacs` ou `nano`.

## Configuração

#### Antes de clicar no botão Start Lab

Leia estas instruções. Os laboratórios são cronometrados e não podem ser pausados. O timer é iniciado quando você clica em **Começar o laboratório** e mostra por quanto tempo os recursos do Google Cloud ficarão disponíveis.

Este laboratório prático do Qwiklabs permite que você realize as atividades em um ambiente real de nuvem, não em uma simulação ou demonstração. Você receberá novas credenciais temporárias para fazer login e acessar o Google Cloud durante o laboratório.

#### O que é necessário

Para fazer este laboratório, você precisa ter:

- acesso a um navegador de Internet padrão (recomendamos o Chrome);
- tempo para concluir as atividades.

**Observação**: não use seu projeto ou sua conta do Google Cloud neste laboratório.

**Observação**: se estiver usando um dispositivo Chrome OS, abra uma janela anônima para executar o laboratório.

### Como iniciar seu laboratório e fazer login no console do Google Cloud

1. Clique no botão **Começar o laboratório**. Se for preciso pagar, você verá um pop-up para selecionar a forma de pagamento. No painel **Detalhes do laboratório** à esquerda, você verá o seguinte:

   - O botão **Abrir Console do Cloud**
   - Tempo restante
   - As credenciais temporárias que você vai usar neste laboratório
   - Outras informações se forem necessárias

2. Clique em **Abrir Console do Google**. O laboratório ativa recursos e depois abre outra guia com a página **Fazer login**.

   ***Dica\***: coloque as guias em janelas separadas lado a lado.

   **Observação**: se aparecer a caixa de diálogo **Escolher uma conta**, clique em **Usar outra conta**.

3. Caso seja preciso, copie o **Nome de usuário** no painel **Detalhes do laboratório** e cole esse nome na caixa de diálogo **Fazer login**. Clique em **Avançar**.

4. Copie a **Senha** no painel **Detalhes do laboratório** e a cole na caixa de diálogo **Olá**. Clique em **Avançar**.

   **Importante**: você precisa usar as credenciais do painel à esquerda. Não use suas credenciais do Google Cloud Ensina.

   **Observação**: se você usar sua própria conta do Google Cloud neste laboratório, é possível que receba cobranças adicionais.

5. Acesse as próximas páginas:

   - Aceite os Termos e Condições.
   - Não adicione opções de recuperação nem autenticação de dois fatores (porque essa é uma conta temporária).
   - Não se inscreva em testes gratuitos.

Depois de alguns instantes, o console do GCP vai ser aberto nesta guia.

**Observação**: para ver uma lista dos produtos e serviços do Google Cloud, clique no **Menu de navegação** no canto superior esquerdo. ![Ícone do menu de navegação](https://cdn.qwiklabs.com/9vT7xPlxoNP%2FPsK0J8j0ZPFB4HnnpaIJVCDByaBrSHg%3D)

### Ative o Google Cloud Shell

O Google Cloud Shell é uma máquina virtual com ferramentas de desenvolvimento. Ele conta com um diretório principal permanente de 5 GB e é executado no Google Cloud. O Google Cloud Shell permite acesso de linha de comando aos seus recursos do GCP.

1. No Console do GCP, na barra de ferramentas superior direita, clique no botão **Abrir o Cloud Shell**.

   ![Ícone do Cloud Shell](https://cdn.qwiklabs.com/vdY5e%2Fan9ZGXw5a%2FZMb1agpXhRGozsOadHURcR8thAQ%3D)

2. Clique em **Continue** (continuar):

   ![cloudshell_continue](https://cdn.qwiklabs.com/lr3PBRjWIrJ%2BMQnE8kCkOnRQQVgJnWSg4UWk16f0s%2FA%3D)

Demora alguns minutos para provisionar e conectar-se ao ambiente. Quando você está conectado, você já está autenticado e o projeto é definido como seu **PROJECT_ID** . Por exemplo:

![Terminal do Cloud Shell](https://cdn.qwiklabs.com/hmMK0W41Txk%2B20bQyuDP9g60vCdBajIS%2B52iI2f4bYk%3D)

**gcloud** é a ferramenta de linha de comando do Google Cloud Platform. Ele vem pré-instalado no Cloud Shell e aceita preenchimento com tabulação.

É possível listar o nome da conta ativa com este comando:

```
gcloud auth list
content_copy
```

Saída:

```output
ACTIVE: *
ACCOUNT: student-01-xxxxxxxxxxxx@qwiklabs.net
To set the active account, run:
    $ gcloud config set account `ACCOUNT`
	content_copy
```

É possível listar o ID de projeto com este comando:

```
gcloud config list project
	content_copy
```

Saída:

```output
[core]
project = <project_ID>
	content_copy
```

Exemplo de saída:

```Output
[core]
project = qwiklabs-gcp-44776a13dea667a6
	content_copy
```

A documentação completa do **gcloud** está disponível na página [Visão geral do gcloud](https://cloud.google.com/sdk/gcloud) do Google Cloud.

Depois da ativação do Cloud Shell, você pode usar a linha de comando para invocar a ferramenta `gcloud` do SDK do Cloud ou outras ferramentas disponíveis na instância da máquina virtual. Mais adiante no laboratório, você vai usar o diretório `$HOME`, que armazena arquivos de vários projetos e sessões do Cloud Shell no disco permanente. O diretório `$HOME` é particular e não pode ser acessado por outros usuários.

## Tarefa 1: configure o ambiente

Nesta seção, vamos falar sobre os aspectos do ambiente de desenvolvimento que podem ser ajustados.

### O que são regiões e zonas

Alguns recursos do [Google Compute Engine](https://cloud.google.com/compute/docs/instances) estão em regiões ou zonas. As regiões são localizações geográficas específicas onde você executa recursos. Todas elas têm uma ou mais zonas. Por exemplo, `us-central1` indica uma região na área central dos Estados Unidos com as zonas `us-central1-a`, `us-central1-b`, `us-central1-c` e `us-central1-f`. A imagem a seguir mostra as zonas em suas respectivas regiões:

| Western US | Central US    | Eastern US | Western Europe | Eastern Asia  |
| :--------- | :------------ | :--------- | :------------- | :------------ |
| us-west1-a | us-central1-a | us-east1-b | europe-west1-b | asia-east1-a  |
| us-west1-b | us-central1-b | us-east1-c | europe-west1c  | asia-east1-b  |
| -          | us-central1-c | us-east1-d | europe-west1-d | aisia-east1-c |
| -          | us-central1-f | -          | -              | -             |

Os recursos que estão em uma zona são chamados de recursos *zonais*. Uma zona contém instâncias de máquina virtual e discos permanentes. Para anexá-los um ao outro, ambos os recursos devem estar na mesma zona. Da mesma forma, para atribuir um endereço IP estático a uma instância, ela deve estar na mesma região que ele.

Confira mais detalhes sobre as regiões e zonas e veja uma lista completa na [Documentação de regiões e zonas](https://cloud.google.com/compute/docs/regions-zones/).

1. Defina a região como `____` .

```
gcloud config set compute/region 
```

Copiado.

content_copy

1. Para ver a configuração da região do projeto, execute o seguinte comando:

```
gcloud config get-value compute/region
```

Copiado.

content_copy

1. Defina a zona como `____` .

```
gcloud config set compute/zone 
```

Copiado.

content_copy

1. Para ver a configuração da zona do projeto, execute o seguinte comando:

```
gcloud config get-value compute/zone
```

Copiado.

content_copy

### Como encontrar as informações do projeto

1. Copie o ID do projeto para a área de transferência ou o editor de texto. Ele pode ser encontrado em dois lugares:

- Em **Informações do projeto** no "Painel" do Console do Google Cloud. Para acessar, clique no **Menu de navegação** (![Menu de navegação](https://cdn.qwiklabs.com/tkgw1TDgj4Q%2BYKQUW4jUFd0O5OEKlUMBRYbhlCrF0WY%3D)) e em **Página inicial > Painel**.
- Na guia do Qwiklabs, ao lado do nome de usuário e da senha.

1. No Cloud Shell, execute o seguinte comando `gcloud` para ver o ID do seu projeto:

```
gcloud config get-value project
```

Copiado.

content_copy

1. No Cloud Shell, execute o seguinte comando `gcloud` para ver os detalhes do projeto:

```
gcloud compute project-info describe --project $(gcloud config get-value project)
```

Copiado.

content_copy

Na saída do comando, encontre os valores dos metadados de zona e região. Mais adiante neste laboratório, você usará a zona `google-compute-default-zone`.

Quando a saída não contém as chaves e os valores `google-compute-default-region` e `google-compute-default-zone`, isso quer dizer que nenhuma zona ou região padrão está definida.

A resposta inclui outras informações úteis relacionadas ao seu projeto. Dedique alguns momentos para analisar isso em detalhes.

### Como definir variáveis de ambiente

Essas variáveis definem o ambiente e economizam tempo na criação de scripts com APIs ou executáveis.

1. Crie uma variável de ambiente para armazenar seu ID do projeto:

```
export PROJECT_ID=$(gcloud config get-value project)
```

Copiado.

content_copy

1. Crie uma variável de ambiente para armazenar sua Zona:

```
export ZONE=$(gcloud config get-value compute/zone)
```

Copiado.

content_copy

1. Para verificar se as variáveis foram definidas corretamente, execute os comandos abaixo:

```
echo -e "PROJECT ID: $PROJECT_ID\nZONE: $ZONE"
```

Copiado.

content_copy

Se as variáveis tiverem sido definidas corretamente, os comandos "echo" vão gerar o ID do projeto e a zona.

### Como criar uma máquina virtual com a ferramenta gcloud

Use a ferramenta `gcloud` para criar uma nova instância de máquina virtual (VM).

1. Execute o comando a seguir para criar sua VM:

```
gcloud compute instances create gcelab2 --machine-type e2-medium --zone $ZONE
```

Copiado.

content_copy

**Saída**:

```
Created [https://www.googleapis.com/compute/v1/projects/qwiklabs-gcp-04-326fae68bc3d/zones/us-east1-c/instances/gcelab2].
NAME     ZONE           MACHINE_TYPE   PREEMPTIBLE  INTERNAL_IP  EXTERNAL_IP   STATUS
gcelab2  {{{project_0.startup_script.project_zone}}}  e2-medium               10.128.0.2   34.67.152.90  RUNNING
```

**Detalhes do comando**

- `gcloud compute` permite gerenciar os recursos do Compute Engine de forma mais simples do que com a API do Compute Engine.
- `instances create` cria uma nova instância.
- `gcelab2` é o nome da VM.
- A sinalização `--machine-type` especifica o tipo de máquina *e2-medium*.
- A sinalização `--zone` especifica o local de criação da VM.
- Ao omitir `--zone`, a ferramenta `gcloud` pode inferir a zona desejada com base nas propriedades padrão. Se as outras configurações de instância necessárias, como `machine type` e `image`, não forem especificadas no comando `create`, elas serão definidas com os valores padrão.

#### Teste a tarefa concluída

Clique em **Verificar meu progresso** para conferir a tarefa realizada. Uma pontuação de avaliação será exibida se você tiver criado uma máquina virtual com a ferramenta `gcloud`.

Crie uma máquina virtual com a gcloud

Verificar meu progresso

- Para abrir a ajuda do comando `create`, execute o comando abaixo:

```
gcloud compute instances create --help
```

Copiado.

content_copy

**Observação:** pressione "ENTER" ou a barra de espaço para rolar a página do conteúdo de ajuda Para sair, digite **Q**.

### Explore os comandos gcloud

A ferramenta `gcloud` oferece diretrizes de uso simples que estão disponíveis ao adicionar a sinalização `-h` ao final de qualquer comando `gcloud`.

1. Execute este comando:

```
gcloud -h
```

Copiado.

content_copy

Acesse uma ajuda com um nível de detalhes maior adicionando a sinalização `--help` a um comando ou executando `gcloud help`.

1. Execute este comando:

```
gcloud config --help
```

Copiado.

content_copy

Para sair digite `Q` e pressione Enter.

1. Execute este comando:

```
gcloud help config
```

Copiado.

content_copy

Os resultados dos comandos `gcloud config --help` e `gcloud help config` são equivalentes. Ambos retornam uma ajuda longa e detalhada.

**Nota:** pressione ENTER ou a barra de espaço para navegar pelo conteúdo de ajuda. Para sair, digite **Q**.

As [sinalizações globais](https://cloud.google.com/sdk/gcloud/reference/) da `gcloud` regem o comportamento dos comandos a cada invocação. As sinalizações substituem todos os valores configurados nas propriedades do SDK.

1. Veja a lista de configurações no seu ambiente:

```
gcloud config list
```

Copiado.

content_copy

1. Para ver todas as propriedades e as respectivas configurações:

```
gcloud config list --all
```

Copiado.

content_copy

1. Liste os componentes:

```
gcloud components list
```

Copiado.

content_copy

Esse comando exibe os componentes da gcloud que estão prontos para uso neste laboratório.

## Tarefa 2: execute a filtragem da saída da linha de comando

A CLI gcloud é uma ferramenta importante para trabalhar na linha de comando. Às vezes pode ser necessário especificar informações a serem exibidas.

1. Liste a instância de computação disponível no projeto

```
gcloud compute instances list
```

Copiado.

content_copy

É bastante comum haver vários recursos implantados em um projeto. Felizmente a gcloud tem alguns formatos inteligentes que podem ajudar a identificar recursos específicos.

**Saída**:

```
  NAME: gcelab2
  ZONE: 
  MACHINE_TYPE: e2-medium
  PREEMPTIBLE:
  INTERNAL_IP: 10.142.0.2
  EXTERNAL_IP: 35.237.43.111
  STATUS: RUNNING
```

1. Liste a máquina virtual gcelab2

```
gcloud compute instances list --filter="name=('gcelab2')"
```

Copiado.

content_copy

**Saída**:

```
  NAME: gcelab2
  ZONE: 
  MACHINE_TYPE: e2-medium
  PREEMPTIBLE:
  INTERNAL_IP: 10.142.0.2
  EXTERNAL_IP: 35.237.43.111
  STATUS: RUNNING
```

No comando acima, foi solicitado à gcloud que mostrasse apenas as informações correspondentes aos critérios, por exemplo, o nome da instância virtual correspondente aos critérios.

1. Liste as regras de firewall do projeto

```
gcloud compute firewall-rules list
```

Copiado.

content_copy

**Saída**:

```
NAME                         NETWORK      DIRECTION  PRIORITY  ALLOW                         DENY  DISABLED
default-allow-icmp           default      INGRESS    65534     icmp                                False
default-allow-internal       default      INGRESS    65534     tcp:0-65535,udp:0-65535,icmp        False
default-allow-rdp            default      INGRESS    65534     tcp:3389                            False
default-allow-ssh            default      INGRESS    65534     tcp:22                              False
dev-net-allow-ssh            dev-network  INGRESS    1000      tcp:22                              False
serverless-to-vpc-connector  dev-network  INGRESS    1000      icmp,udp:665-666,tcp:667            False
vpc-connector-egress         dev-network  INGRESS    1000      icmp,udp,tcp                        False
vpc-connector-health-check   dev-network  INGRESS    1000      tcp:667                             False
vpc-connector-to-serverless  dev-network  EGRESS     1000      icmp,udp:665-666,tcp:667            False
```

1. Liste as regras de firewall da rede padrão

```
gcloud compute firewall-rules list --filter="network='default'"
```

Copiado.

content_copy

**Saída**:

```
NAME                         NETWORK      DIRECTION  PRIORITY  ALLOW                         DENY  DISABLED
default-allow-icmp           default      INGRESS    65534     icmp                                False
default-allow-internal       default      INGRESS    65534     tcp:0-65535,udp:0-65535,icmp        False
default-allow-rdp            default      INGRESS    65534     tcp:3389                            False
default-allow-ssh            default      INGRESS    65534     tcp:22                              False
```

1. Liste as regras de firewall da rede padrão em que a regra de permissão corresponda a uma regra ICMP

```
gcloud compute firewall-rules list --filter="NETWORK:'default' AND ALLOW:'icmp'"
```

Copiado.

content_copy

**Saída**:

```
NAME                         NETWORK      DIRECTION  PRIORITY  ALLOW                         DENY  DISABLED
default-allow-icmp           default      INGRESS    65534     icmp                                False
default-allow-internal       default      INGRESS    65534     tcp:0-65535,udp:0-65535,icmp        False
```

## Tarefa 3: conecte-se à sua instância de VM

O `gcloud compute` facilita a conexão com instâncias. O comando `gcloud compute ssh` adiciona um wrapper no SSH que cuida da autenticação e do mapeamento dos nomes de instâncias para os endereços IP.

1. Para se conectar à VM com SSH, execute o comando abaixo:

```
gcloud compute ssh gcelab2 --zone $ZONE
```

Copiado.

content_copy

**Saída**:

```
WARNING: The public SSH key file for gcloud does not exist.
WARNING: The private SSH key file for gcloud does not exist.
WARNING: You do not have an SSH key for gcloud.
WARNING: [/usr/bin/ssh-keygen] will be executed to generate a key.
This tool needs to create the directory
[/home/gcpstaging306_student/.ssh] before being able to generate SSH Keys.
Do you want to continue? (Y/n)
```

1. Para continuar, digite **Y**.

```
Generating public/private rsa key pair.
Enter passphrase (empty for no passphrase)
```

1. Para deixar a senha longa vazia, pressione **ENTER**.

Você se conectou à máquina virtual criada no laboratório. Percebeu como o prompt de comando mudou?

O que você vê no prompt agora é semelhante a **sa_107021519685252337470@gcelab2**.

- A referência antes de **@** indica a conta que está sendo usada.
- Após o símbolo **@** está a indicação da máquina host acessada.

1. Instale o servidor da Web `nginx` na máquina virtual

```
sudo apt install -y nginx
```

Copiado.

content_copy

1. Como nenhuma ação é necessária aqui, desconecte-se do SSH e saia do shell remoto executando o comando abaixo:

```
exit
```

Copiado.

content_copy

Você voltará ao prompt de comando do projeto.

## Tarefa 4: atualize o Firewall

Ao usar recursos de computação, como as máquinas virtuais, é importante entender as regras de firewall associadas.

1. Liste as regras de firewall para o projeto

```
gcloud compute firewall-rules list
```

Copiado.

content_copy

**Saída**:

```
NAME                         NETWORK      DIRECTION  PRIORITY  ALLOW                         DENY  DISABLED
default-allow-icmp           default      INGRESS    65534     icmp                                False
default-allow-internal       default      INGRESS    65534     tcp:0-65535,udp:0-65535,icmp        False
default-allow-rdp            default      INGRESS    65534     tcp:3389                            False
default-allow-ssh            default      INGRESS    65534     tcp:22                              False
dev-net-allow-ssh            dev-network  INGRESS    1000      tcp:22                              False
serverless-to-vpc-connector  dev-network  INGRESS    1000      icmp,udp:665-666,tcp:667            False
vpc-connector-egress         dev-network  INGRESS    1000      icmp,udp,tcp                        False
vpc-connector-health-check   dev-network  INGRESS    1000      tcp:667                             False
vpc-connector-to-serverless  dev-network  EGRESS     1000      icmp,udp:665-666,tcp:667            False
```

Há duas redes disponíveis. A rede `padrão` é onde está localizada nossa máquina virtual `gcelab2`.

1. Tente acessar o serviço nginx em execução na máquina virtual `gcelab2`.

A máquina virtual não tem uma regra de firewall adequada, portanto, a comunicação com ela vai falhar. Nosso servidor da Web **nginx** está aguardando a comunicação na porta **tcp:80**. Para que a comunicação funcione, precisamos fazer o seguinte:

- Adicionar uma tag à máquina virtual gcelab2
- Adicionar uma regra de firewall para o tráfego HTTP

1. Adicione uma tag à máquina virtual

```
gcloud compute instances add-tags gcelab2 --tags http-server,https-server
```

Copiado.

content_copy

1. Atualize a regra de firewall para permitir

```
gcloud compute firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server
```

Copiado.

content_copy

1. Liste as regras de Firewall para o projeto

```
gcloud compute firewall-rules list --filter=ALLOW:'80'
```

Copiado.

content_copy

**Saída**:

```
NAME                NETWORK  DIRECTION  PRIORITY  ALLOW   DENY  DISABLED
default-allow-http  default  INGRESS    1000      tcp:80        False
```

1. Verifique se a máquina virtual aceita a comunicação HTTP

```
curl http://$(gcloud compute instances list --filter=name:gcelab2 --format='value(EXTERNAL_IP)')
```

Copiado.

content_copy

A saída padrão `nginx` é exibida.

## Tarefa 5: execute a visualização dos registros do sistema

A visualização dos registros é essencial para você compreender o funcionamento do seu projeto. Use o comando gcloud para acessar registros diferentes, disponíveis no Google Cloud.

1. Exiba os registros disponíveis no sistema:

```
gcloud logging logs list
```

Copiado.

content_copy

**Saída**:

```
NAME
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/GCEGuestAgent
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/OSConfigAgent
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/autoscaler.googleapis.com%2Fstatus_change
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/cloudaudit.googleapis.com%2Factivity
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/cloudaudit.googleapis.com%2Fsystem_event
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/compute.googleapis.com%2Fautoscaler
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/compute.googleapis.com%2Finstance_group_manager_events
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/compute.googleapis.com%2Fshielded_vm_integrity
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/run.googleapis.com%2Frequests
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/run.googleapis.com%2Fstderr
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/run.googleapis.com%2Fstdout
```

1. Exiba os registros relacionados aos recursos de computação

```
gcloud logging logs list --filter="compute"
```

Copiado.

content_copy

**Saída**:

```
NAME
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/compute.googleapis.com%2Fautoscaler
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/compute.googleapis.com%2Finstance_group_manager_events
projects/qwiklabs-gcp-03-6bef54ddd5e7/logs/compute.googleapis.com%2Fshielded_vm_integrity
```

1. Leia os registros relacionados ao tipo de recurso de `gce_instance`

```
gcloud logging read "resource.type=gce_instance" --limit 5
```

Copiado.

content_copy

1. Leia os registros de uma máquina virtual específica

```
gcloud logging read "resource.type=gce_instance AND labels.instance_name='gcelab2'" --limit 5
```

Copiado.

content_copy

## Teste seu conhecimento

Responda à pergunta de múltipla escolha abaixo para reforçar sua compreensão dos conceitos deste laboratório.



Três maneiras básicas de interagir com os serviços e recursos do Google Cloud são:



Client libraries



Command-line interface



GLib



Cloud Console



GStreamer

Enviar



## Parabéns!

Você aprendeu a inicializar o Cloud Shell e executou alguns comandos de amostra da `gcloud`.

### Termine a Quest

![selo de conclusão](https://cdn.qwiklabs.com/ykt8NTzPWC6%2BW8mAljshFqjsAPrZ8bElG7SLw4kSrtU%3D) ![selo de conclusão do sdk](https://cdn.qwiklabs.com/zTElq%2B6%2F9Fl9puC3rQKGKZfxrng9WeK0wGuVxwakC4U%3D)

Este laboratório autoguiado faz parte das Quests [Google Cloud Essentials](https://google.qwiklabs.com/quests/23) e [Using the Cloud SDK Command Line](https://google.qwiklabs.com/quests/95) do Qwiklabs. Uma Quest é uma série de laboratórios relacionados que formam o programa de aprendizado. Concluir esta Quest dá a você o selo acima como reconhecimento da sua conquista. Você pode publicar os selos e incluir um link para eles no seu currículo on-line ou nas redes sociais. Inscreva-se em uma Quest e receba crédito de conclusão imediato por fazer este laboratório. [Veja outras Quests do Qwiklabs](https://google.qwiklabs.com/catalog).

### Comece o próximo laboratório

Continue sua Quest com o laboratório [Provisionar serviços com o Google Cloud Marketplace](https://google.qwiklabs.com/catalog_lab/339) ou confira estas sugestões:

- [Como criar um disco permanente](https://google.qwiklabs.com/catalog_lab/559)
- [Como configurar redes usando a gcloud](https://google.qwiklabs.com/catalog_lab/2047)

### Próximas etapas / Saiba mais

- [Documentação](https://cloud.google.com/shell/docs/) e [tutorial em vídeo](https://www.youtube.com/watch?v=hBMcAKzGt3w) sobre o Cloud Shell.
- [Documentação](https://cloud.google.com/sdk/gcloud/) e [tutorial em vídeo](https://www.youtube.com/watch?v=oTIK9OvQBxQ&list=PLIivdWyY5sqIij_cgINUHZDMnGjVx3rxi&index=15) sobre a `gcloud`.

### Treinamento e certificação do Google Cloud

...ajuda você a aproveitar as tecnologias do Google Cloud ao máximo. [Nossas aulas](https://cloud.google.com/training/courses) incluem habilidades técnicas e práticas recomendadas para ajudar você a alcançar rapidamente o nível esperado e continuar sua jornada de aprendizado. Oferecemos treinamentos que vão do nível básico ao avançado, com opções de aulas virtuais, sob demanda e por meio de transmissões ao vivo para que você possa encaixá-las na correria do seu dia a dia. As [certificações](https://cloud.google.com/certification/) ajudam você a validar e comprovar suas habilidades e conhecimentos das tecnologias do Google Cloud.

##### Manual atualizado em 18 de agosto de 2022

##### Laboratório testado em 18 de agosto de 2022

Copyright 2020 Google LLC. Todos os direitos reservados. Google e o logotipo do Google são marcas registradas da Google LLC. Todos os outros nomes de produtos e empresas podem ser marcas registradas das respectivas empresas a que estão associados.