# Guia Rápido de Comandos Git



Um guia rápido de comandos Git para agilizar nas tarefas do dia a dia. Se for útil para você deixa um :star:


## Lista de Conteúdos

* [Configuração Global](#configura%C3%A7%C3%A3o-global)
* [Iniciando um repositório local](#iniciando-um-reposit%C3%B3rio-local)
* [Consultas](#consultas)
   * [`status`](#status)
   * [`log`](#log)
   * [`diff`](#diff)
   * [`show`](#show)
* [Gerenciamento da Stage Area](#gerenciamento-da-stage-area)
   * [`add` - Adicionando Arquivos](#add)
   * [`rm` - Removendo Arquivos](#rm)
   * [`mv` - Movendo arquivos](#mv)
* [Gerenciamento de Branchs](#gerenciamento-de-branchs)
* [Gerenciamento de Tags](#gerenciamento-de-tags)
* [Commits](#commit)
* [Desfazer / Reverter](#desfazer--reverter)
* [Acesso Remoto](#acesso-remoto)
   * [`clone` - Copia para local](#clone)
   * [`remote` - Conexão remota](#remote)
   * [`pull` - De remote para local](#pull)
   * [`push` - De local para remoto](#push)
 
 
**Observação:**
 
Os comandos que possuem variações podem ser combinados. 

Exemplo: Comando de log
`git log -n2 --oneline --decorate --parents`
 

## Configuração Global

Configura parametros globais para a utilização do Git. 
Esse procedimento é necessário logo após a instalação do seu software Git em sua máquina local e é utilizada para identificação em logs de históricos.

**Obs:** Não é necessário um diretório específico para execultar esses comandos.

[Topo](#lista-de-conte%C3%BAdos)

Comando | Descrição
:---|:---
`git config --global user.name "<seu nome>"` | Registra _**seu nome**_ nas configurações globais
`git config --global user.email "<seu email>"`| Registra _**seu email**_ nas configurações globais

[Topo](#lista-de-conte%C3%BAdos)

## Iniciando um repositório local

Deve ser executado acessando o diretório específico do seu projeto. Pode ser iniciado em qualquer etapa do projeto, sendo recomendado que se utilize sempre no inicio.

Comado | Descrição
:---|:---
`git init` | Inicia o controle de versionamento no diretório.


[Topo](#lista-de-conte%C3%BAdos)

## Consultas

### Status
Comado | Descrição
:---|:---
`git status` | Mostra o status dos arquivos do diretório monitorado, em relação a stage area e sugestões de próximas ações.

[Topo](#lista-de-conte%C3%BAdos)

### log
Comado | Descrição
:---|:---
`git log`| Lista o histórico de _commits_ e outras ações dentro de um repositório. 
`git log -n <x>` | Onde `x` é o limite da quantidade de resultados a serem exibidos.
`git log --oneline`| Listagem simplificada, somente títulos e a referencia dos logs, sem mostrar os detalhes.
`git log --stat` | Mostra as estatísticas do que foi feito (alterações, adições e deletados.
`git log --decorate` | Mostra a head, breach e o servidor remote.
`git log --parents`| Mostra a relação entre os commits.

[Topo](#lista-de-conte%C3%BAdos)

### diff
Comado | Descrição
:---|:---
`git diff` | Mostra as modificações do repositório em relação a _Stage Area_
`git diff --name-only`| Mostra somente o nome dos arquivos que foram modificados
`git diff` --staged | Mostra os arquivos que estão na _stage Area_
`git diff <arquivo.ext> ou <hasdocommit>` | Mostra as modificações de um arquivo específico ou de um determinado commit.
`git diff <hashinicial>..<hashfinal>` | Mostra somente as modificações entre as hashs de commits informadas. Lembrando que hash inicial é a ultima listada no `git log --oneline`
`git diff <hashinicial>~<x>` |  Onde `x` é o númedo desejado. Mostra as modificações a partir da hash inicial e as três anteriores a ela (mostra todas as alterações, incluídos ou não na _stage area_.

[Topo](#lista-de-conte%C3%BAdos)

### show
Comado | Descrição
:---|:---
`git show` | Mostra modificações feitas recentemente


**Obs.:** Se houver muitos resultados a serem exibidos, o Git irá mostrar os resultados parcialmente. Bastar teclar _Enter_ para continuar vendo os resultados ou tecle "_q_" para sair da lista de resultados.

[Topo](#lista-de-conte%C3%BAdos)



## Gerenciamento da Stage Area

### add

Comado | Descrição
:---|:---
`git add  <nomedoarquivo.ext>` | Adiciona um arquivo específico na _stage area_
`git add <nomedodiretorio>/.`| Adiciona o diretório especificado na _stage area_. O ponto, ao final do comando, significa que todos os subdiretórios e arquivos internos, serão adicionados.
`git add -A`| Adiciona todos os arquivos na _stage area_, porém **exclui** os arquivos que foram excluídos do projeto.
`git add .`| Adiciona todos os arquivos na _stage area_, porém **não exclui** os arquivos que foram excluídos do projeto.

[Topo](#lista-de-conte%C3%BAdos)


### rm

Remove/Deleta arquivos.

Comado | Descrição
:---|:---
`git rm <nomedoarquivo>`| Remove o arquivo informado (deleta definitivamente).
`git rm <nomedodiretorio>/. -f`| Remove todos os arquivos de um determinado diretório, o "-f" força a exclusão.
`git rm <nomedodiretorio>/. -fr`| remove todos os arquivos de um determinado diretório, o "-f" força a exclusão. (para arquivos ainda não "comitado"), o "r" torna o comando recursivo, ou seja, funcionará em todos os elementos internos da pasta.
`git rm <diretorio>/<arquivo.ext> ./`| Será movido para o direto raiz da navegação. Para mover um arquivo, é necessário que a pasta de destino exista, pois esse comando não criará a pasta caso não exista. 


[Topo](#lista-de-conte%C3%BAdos)

### mv
Move arquivos de acordo com o especificado.

Comado | Descrição
:---|:---
`git mv <diretorioorigem>/>arquivo.ext> <diretoriodestino>/` | Muda o arquivo de diretório, também mudando na _stage area_ (o diretório de destino deve existir antes de executar o comando)
`git mv <diretorioorigem>/<nomeantigo.ext> diretoriodestino/novonome.ext`| Além de mudar o arquivo de diretório, também muda o nome do arquivo. (o diretório de destino deve existir antes de executar o comando)

[Topo](#lista-de-conte%C3%BAdos)

## Gerenciamento de Branchs

Comado | Descrição
:---|:---
`git branch <nomedabranch>`| Cria uma nova _branch_
`git branch -d <nomedabranch>`| Ira deletar uma _branch_ criada no ambiente local. Para deletar uma _branch_ é necessário estar fora dela. A _branch_ a ser deletada não deve ter registro. Se houver registro e mesmo assim quer deletar a _branch_ em questão, utilize o `D` maiúsculo.
`git branch --no-merge`| Mostra o conteúdo não mesclado até o momento [SEM SAIDA].
`git branch --merged`| Mostra as _branches_ que estão listada.
`git branch -r`| Mostra todas as _branches_ existentes no repositório remoto.
`git checkout <branchdestino>`| Irá mudar de _branch_.
`git checkout -b <novabranch>` | Cria uma nova _branch_ e muda para a nova _branch_ automaticamente.
`git checkout -B <novabranch>`| atua criando uma nova _branch_ e mudando automaticamente para a nova _branch_ criada **[FORÇADO]**.
`git merge <branchdominante> -m 'descricao'`| Mescla o conteúdo entre as _branch_. **Obs.:** É importante sempre mesclar o conteúdo entre os _commits_, quando não for mais necessário manter os commits separadamente.


[Topo](#lista-de-conte%C3%BAdos)

## Gerenciamento de Tags

As tags são apenas um marcador que pode ser adicionado um commit especifico. É possível acessar uma branch em uma tag específica. 

Comado | Descrição
:---|:---
`git tag <texto>`| Adiciona uma tag. 
`git tag <texto> <hashdocommit>`| Adiciona uma tag ao _commit_ especifico referenciado na hash.
`git tag -d <texto>`| Deleta a tag informada.
`git tag -d <texto> <hashdocommit>` | Deleta a tag informada do _commit_ especificado referenciado na hash.
`git chechout <textodatag>` | Acessa a branch no _commit_ do qual a tag foi adicionada.


[Topo](#lista-de-conte%C3%BAdos)

## commit

Comado | Descrição
:---|:---
`git commit -m "<Descrição livre>"` | Executará com que o git execute o _commit_ dos arquivos que estavam na _stage area_, fazendo com que as alterações desses arquivos sejam salvas em seu repositório local.
`git commit -a -m "<Descrição livre>"`| Irá adicionar e commitar no mesmo comando, ação em apenas uma linha.


[Topo](#lista-de-conte%C3%BAdos)


## Desfazer / Reverter

Comado | Descrição
:---|:---


[Topo](#lista-de-conte%C3%BAdos)

## Acesso Remoto

## clone

Cria uma cópia do repositório remoto no ambiente local, já incluido a conexão ao repositório remoto, que, se tiver permissão de acesso, poderá executar o _push_  para o repositório de origem.

Comado | Descrição
:---|:---
`git clone <remote-repo-url>`| Clona um repositório remoto para o ambiente local.
`git clone --branch <branchname> <remote-repo-url>` | Clona um repositório através de uma branch _específica_.
`git clone -b <branchname> <remote-repo-url>`|  Clona um repositório através de uma branch _específica_.

[Topo](#lista-de-conte%C3%BAdos)

## remote

Conecta o repositório local ao repositório remoto.

Comado | Descrição
:---|:---
`git remote add <origin> <urlrepositorioremoto>` | Adiciona um repositório remoto ao repositório local. Onde `<origin>` é o apelido do repositório remoto. É necessário criar o repositório remoto (Github) e pegar a url do repositório. **Obds.:** pode-se atribuir mais de um repositório remoto ao repositório local. Ex.: Github e Hospedagem.
`git remote`| Mostra quais repositorios remotos conectados ao repositório local.
`git remote -v`| Mostra os detalhes do repositório remoto.


[Topo](#lista-de-conte%C3%BAdos)


## pull

Envia o projeto remoto para o repositório local. 


Comado | Descrição
:---|:---


[Topo](#lista-de-conte%C3%BAdos)

## push

Envia o projeto local para o repositório remoto.

Comado | Descrição
:---|:---
`git push -u <origin> <branchdestino>` | Envia o projeto local para o repositório remoto. Onde `<origin>` é o apelido da conexão com o repositório remoto.
`git push <origin> <tagname>`| Adiciona uma _tag_ ao _commit_ mais recente do repositório remoto. Onde `<origin>` é o apelido da conexão com o repositório remoto.
`git push origin --tags`| Adiciona todas as _tags_ do repositório local ao repositório remoto.


[Topo](#lista-de-conte%C3%BAdos)

















