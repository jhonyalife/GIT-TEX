### Benefícios do uso de um sistema de Controle de Versão

- Versionamento

### Problema sobre o desenvolvimento individual

- falta de capacidade de retornar as versões anteriores.
- Versão não monitorada
- Longo periodo em busca de solução

### Problema relacionado a trabalhar com equipe

- Conflitos quando mais de um programador está trabalhando no mesmo arquivos
- 'Bloqueio' do arquivo no desenvolvimento individual
- Refação desnecessária

***Solução -  Monitoramento das alterações dos arquivos***

---
# Git

**Para instalar no  Ubunut: sudo apt-get install git**

- Diferente porque tira uma 'foto' instantâneo do status do arquivo
- Armazena uma referência do arquivo
- Se um arquivo não teve alterações não registra
- Fluxo de momentos do projeto
- Maioria das ações são locais
- Integridades, todas as ações são registrados.
- String de 40 posições que usa hexadecimal (0-9 a-f).
- Armazena dados
- Repositorio local
  
---

### Coisas principais a serem lembradas:

- Diretório de trabalho (Pasta na sua máquina virtual)
- Repositorio git
- .git : Banco de dados compactado com asalterações dos arquivos
- Stating: Área de preparação
- Compromisso: Commit

***Modifica o arquivo --> Adicionar ao Staging --> comprometer o arquivo: Commit***

---

### Configuração Inicial para usar o git

***Informações de sua identidade:***

1. config --global user.name
2. config --global user.email
3. config --global core.editor
4. config --list

---

### Github:

- Repositorio remoto

---

### Fazer e verificar commit:

* git commit -m "mensagem"
* git log - Para verificar


### Para arquivos que já estejam modificados:

* -git commit -am "mensagem"

---

### Adicionar alterações no arquivo:

* git add nomeDoArquivo
* git add

### Adicionar todos os arquivos na stage:

* git add .

### Desfazer o add:

* git rm --cached "nome-do-arquivo"

* git restore -staged "nomedoarquivo"

---

### Desfazer e navegar entre diferentes commits:

Através do comando git reset é possível desfazer e navegar entre diferentes commits.

***Comandos reset:***

* reset:
    * Head > Commit
    * index > Stage
    * working Tree > Diretório
  
* –hard: desfaz o commit e o stage, alterando o diretório.
* –mixed: desfaz o commit e o stage, sem fazer alterações no diretório.
* –soft: desfaz o commit, matendo o stage e não alterando o diretório.

---

### Para ignorar um arquivo:

- Criar um arquivo chamado ".gitignore"
- Colocar o nome do arquivo que deseja ser excluido dentro do ".gitignore"

---

### Para comparar dois commits:

- O comando git diff é capaz de trazer as diferenças entre o último commit e a versão atual dos arquivos.
- É possível visualizar as diferenças entre dois commits diferentes ao utilizar suas chaves após o comando git diff.
- Para salvar as mudanças em um novo arquivo, basta usar o comando git diff > nome-do-arquivo.patch.
- Pode-se adicionar mudanças com arquivos .patch a partir do comando git apply nome-do-arquivo.patch.

---------------------------------------------------------------------------------------------------------

### Criar um novo galho - branch:

- Através do comando git branch "nome-da-branch" criamos uma nova branch

### Criar um novo galho, mas já entrando nele:

- git checkout -b "nome-da-branch-nova"

### Alterar nome da branch:

- git branch -m "nome-da-nova-branch"

### Trocar de branch - checkout ou switch:

- Através do comando git checkout "nome-da-branch"
- git switch "nome-da-branch"

### Criar e já entrar na branch local 

- git switch -c "nome-da-branch"

### Deletar branch no remoto:

- git push --delete "nome-da-branch"

### Deletar branch local

- git branch -d "nome-da-branch"

### Conferir branch no remoto

-git branch -r

### Fazer checkout diretamente no branch remoto:

- git checkout origin/projeto_v2
  
---

# Acessa os logs de forma rápida:

- Usamos o comando git log -1 
- git log --graph
- git log --oneline --all (mostra todos os commits independente da branch )
- Para obersavamos as modificações utilizamos o comando git log -p -1
- Para verificarmos a estatistica utilizamos o comando git log -1 --statz
- Para organizar a visualização utilizamos o comando git log -1 --stat --pretty=oneline
- Para organizar ainda melhor a visualização utilizamos o comando git log -3 --stat --pretty=format:"%an - %ar: %s"

---

### Modificar nome do arquivo:

- Para modificamos o nome do arquivo, basta digitar git mv "nome-do-arquvio-antigo" "nome-do-arquivo-novo"

---

### Remover arquivo:

- Para remover arquivo, basta usar git rm "nome-do-arquivo"

### Criar arquivo:

- Basta usar o > "nome do arquivo"

---

### Caso inicialize o git no local errado:

- Verifica a pasta oculta .git (comando = ls -la)
- Deletar a pasta .git (comando= rm -rf .git)

---

### Conectar o repositorio local com o repositorio remoto - GIT REMOTE:

-git remote add origin link-do-github

### Subir as alterações e substituir com os diferentes:

- git push -f origin main

### Subir as alterações já estando na branch remota:

- git push origin HEAD:'nome-da-branch'
  
---

### Mesclar as alterações via CLI

- Já estando na branch que deseja ser mesclada
    - git merge "nome-da-branch-que-tem-as-alterações"

**Obs: merge em branch compartilhadas**

---

### Fazer um novo commit e excluir o antigo

- O comando rebase é utilizado para rebobinar o commit 


**Obs: Nunca utilizar em branch compartilhada, apenas em branch que for só sua**

git rebase "nome-da-branch-que-você-quer-copiar"

---

## Fork
 - é uma cópia do repositorio, mas no github

## Clone 
- é o clone do seu repositorio remoto, mas sendo local

---

## Git flow

- master(main) : projeto
    - hotfix : correções imediatas, por conta de falhas críticas : temporária versão 1.0.0-1 Tag
    - dev (desenvolvimento)
        - feature (funcionalidades) : temporária
        - release (lançamento) :  temporária versão 1.0.0 Tag

***A release vai mesclar apenas a feature***

---
