# Guia Rápido de Comandos Git

Um guia rápido de comandos Git para agilizar nas tarefas do dia a dia. Se for útil para você deixa um :star:


## Lista de Conteúdos

* Configuração Global
* Iniciando um repositório local
* Consultas
   * `status`
   * `log`
   * `diff`
   * `show`
* Gerenciamento da Stage Area
   * `add` - Adicionando Arquivos
   * `rm` - Removendo Arquivos
   * `mv` - Movendo arquivos
* Gerenciamento de Branchs
* Gerenciamento de Tags
* Commits
* Merges
* Desfazer / Reverter
* Acesso Remoto
   * `clone` - Copia para local
   * `remote` - Conexão remota
   * `pull` - De remote para local
   * `push` - De local para remoto
 
 
**Observação:**
 
Os comandos que possuem variações podem ser combinados. Exemplo: Comando de log
`git log -n2 --onleline --decorate --parents`
 

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

### Log
Comado | Descrição
:---|:---
`git log`| Lista o histórico de _commits_ e outras ações dentro de um repositório. 
`git log -n <x>` | Onde `x` é o limite da quantidade de resultados a serem exibidos.
`git log --oneline`| Listagem simplificada, somente títulos e a referencia dos logs, sem mostrar os detalhes.
`git log --stat` | Mostra as estatísticas do que foi feito (alterações, adições e deletados.
`git log --decorate` | Mostra a head, breach e o servidor remote.
`git log --parents`| Mostra a relação entre os commits.

[Topo](#lista-de-conte%C3%BAdos)

### Diff
Comado | Descrição
:---|:---
`git diff` | Mostra as modificações do repositório em relação a _Stage Area_
`git diff --name-only`| Mostra somente o nome dos arquivos que foram modificados
`git diff` --staged | Mostra os arquivos que estão na _stage Area_
`git diff <file.ext> ou <hasdocommit>` | Mostra as modificações de um arquivo específico ou de um determinado commit.
`git diff <hashinicial>..<hashfinal>` | Mostra somente as modificações entre as hashs de commits informadas. Lembrando que hash inicial é a ultima listada no `git log --oneline`
`git diff hashinicial~x` |  Onde `x` é o númedo desejado. Mostra as modificações a partir da hash inicial e as três anteriores a ela (mostra todas as alterações, incluídos ou não na _stage area_.

[Topo](#lista-de-conte%C3%BAdos)

### Show
Comado | Descrição
:---|:---
`git show` | Mostra modificações feitas recentemente


**Obs.:** Se houver muitos resultados a serem exibidos, o Git irá mostrar os resultados parcialmente. Bastar teclar _Enter_ para continuar vendo os resultados ou tecle "_q_" para sair da lista de resultados.

[Topo](#lista-de-conte%C3%BAdos)



## Gerenciamento da Stage Area
Comado | Descrição
:---|:---
















