---
description: Dicas de comandos git
---

# Git Tips - pt-BR

#### Estados

* Modificado \(modified\);
* Preparado \(staged/index\)
* Consolidado \(comitted\);

**Geral**

```text
git help
```

**Comando específico**

```text
git help add
git help commit
git help <qualquer_comando_git>
```

### Configuração

#### Geral

As configurações do GIT são armazenadas no arquivo **.gitconfig** 

As configurações realizadas através dos comandos abaixo serão incluídas no arquivo citado acima.

**Setar usuário global**

```text
git config --global user.name "Jadilson Guedes"
```

**Setar email global**

```text
git config --global user.email jadilson12@gmail.com
```

**Setar editor**

```text
git config --global core.editor vim
```

**Setar Nano**

```text
     git config --global core.editor nano
```

**Setar ferramenta de merge**

```text
git config --global merge.tool vimdiff
```

**Setar arquivos a serem ignorados**

```text
git config --global core.excludesfile ~/.gitignore
```

**Listar configurações**

```text
git config --list
```

**Salva usuario e senha por 8 horas**

```text
git config --global credential.helper 'cache --timeout=28800'
```

**Salva usuario e senha permanente:**

```text
git config --global credential.helper cache
```

#### Ignorar Arquivos

Os nomes de arquivos/diretórios ou extensões de arquivos listados no arquivo **.gitignore** não serão adicionados em um repositório. Existem dois arquivos .gitignore, são eles:

* Geral: Normalmente armazenado no diretório do usuário do Sistema Operacional. O arquivo que possui a lista dos arquivos/diretórios a serem ignorados por **todos os repositórios** deverá ser declarado conforme citado acima. O arquivo não precisa ter o nome de **.gitignore**.
* Por repositório: Deve ser armazenado no diretório do repositório e deve conter a lista dos arquivos/diretórios que devem ser ignorados apenas para o repositório específico.

### Repositório Local

**Setar usuário repo**

```text
git config  user.name "Jadilson Guedes"
```

**Setar email repo**

```text
git config  user.email jadilson12@gmail.com
```

#### Criar novo repositório

```text
git init
```

#### Verificar estado dos arquivos/diretórios

```text
git status
```

#### Adicionar arquivo/diretório \(staged area\)

**Adicionar um arquivo em específico**

```text
git add meu_arquivo.txt
```

**Adicionar um diretório em específico**

```text
git add meu_diretorio
```

**Adicionar todos os arquivos/diretórios**

```text
git add .    
```

**Adicionar um arquivo que esta listado no .gitignore \(geral ou do repositório\)**

```text
git add -f arquivo_no_gitignore.txt
```

#### Comitar arquivo/diretório

**Comitar um arquivo**

```text
git commit meu_arquivo.txt
```

**Comitar vários arquivos**

```text
git commit meu_arquivo.txt meu_outro_arquivo.txt
```

**Comitar informando mensagem**

```text
git commit meuarquivo.txt -m "minha mensagem de commit"
```

#### Remover arquivo/diretório

**Remover arquivo**

```text
git rm meu_arquivo.txt
```

**Remover diretório**

```text
git rm -r diretorio
```

#### Visualizar histórico

**Exibir histórico**

```text
git log
```

**Exibir histórico com diff das duas últimas alterações**

```text
git log -p -2
```

**Exibir resumo do histórico \(hash completa, autor, data, comentário e qtde de alterações \(+/-\)\)**

```text
git log --stat
```

**Exibir informações resumidas em uma linha \(hash completa e comentário\)**

```text
git log --pretty=oneline
```

**Exibir histórico com formatação específica \(hash abreviada, autor, data e comentário\)**

```text
git log --pretty=format:"%h - %an, %ar : %s"
```

* %h: Abreviação do hash;
* %an: Nome do autor;
* %ar: Data;
* %s: Comentário.

Verifique as demais opções de formatação no [Git Book](http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History)

**Exibir histório de um arquivo específico**

```text
git log -- <caminho_do_arquivo>
```

**Exibir histórico de um arquivo específico que contêm uma determinada palavra**

```text
git log --summary -S<palavra> [<caminho_do_arquivo>]
```

**Exibir histórico modificação de um arquivo**

```text
git log --diff-filter=M -- <caminho_do_arquivo>
```

* O  pode ser substituido por: Adicionado \(A\), Copiado \(C\), Apagado \(D\), Modificado \(M\), Renomeado \(R\), entre outros.

**Exibir histório de um determinado autor**

```text
git log --author=usuario
```

**Mostar historico arquivo**

```text
git blame -l filename
```

**Exibir revisão e autor da última modificação de uma bloco de linhas**

```text
git blame -L 12,22 meu_arquivo.txt 
```

#### Desfazendo operações

**Desfazendo alteração local \(working directory\)**

Este comando deve ser utilizando enquanto o arquivo não foi adicionado na **staged area**.

```text
git checkout -- meu_arquivo.txt
```

**Desfazendo alteração local \(staging area\)**

Este comando deve ser utilizando quando o arquivo já foi adicionado na **staged area**.

```text
git reset HEAD meu_arquivo.txt
```

Se o resultado abaixo for exibido, o comando reset _não_ alterou o diretório de trabalho.

```text
Unstaged changes after reset:
M    meu_arquivo.txt
```

A alteração do diretório pode ser realizada através do comando abaixo:

```text
git checkout meu_arquivo.txt
```

### Repositório Remoto

#### Exibir os repositórios remotos

```text
git remote

git remote -v
```

#### Vincular repositório local com um repositório remoto

```text
git remote add origin git@github.com:leocomelli/curso-git.git
```

#### Exibir informações dos repositórios remotos

```text
git remote show origin
```

#### Renomear um repositório remoto

```text
git remote rename origin curso-git
```

#### Desvincular um repositório remoto

```text
git remote rm curso-git
```

#### Enviar arquivos/diretórios para o repositório remoto

O primeiro **push** de um repositório deve conter o nome do repositório remoto e o branch.

```text
git push -u origin master
```

Os demais **pushes** não precisam dessa informação

```text
git push
```

#### Atualizar repositório local de acordo com o repositório remoto

**Atualizar os arquivos no branch atual**

```text
git pull
```

**Buscar as alterações, mas não aplica-las no branch atual**

```text
git fetch
```

#### Clonar um repositório remoto já existente

```text
git clone git@github.com:leocomelli/curso-git.git
```

#### Tags

**Criando uma tag leve**

```text
git tag vs-1.1
```

**Criando uma tag anotada**

```text
git tag -a vs-1.1 -m "Minha versão 1.1"
```

**Criando uma tag assinada**

Para criar uma tag assinada é necessário uma chave privada \(GNU Privacy Guard - GPG\).

```text
git tag -s vs-1.1 -m "Minha tag assinada 1.1"
```

**Criando tag a partir de um commit \(hash\)**

```text
git tag -a vs-1.2 9fceb02
```

**Criando tags no repositório remoto**

```text
git push origin vs-1.2
```

**Criando todas as tags locais no repositório remoto**

```text
git push origin --tags
```

#### Branches

O **master** é o branch principal do GIT.

O **HEAD** é um ponteiro _especial_ que indica qual é o branch atual. Por padrão, o **HEAD** aponta para o branch principal, o **master**.

**Criando um novo branch**

```text
git branch bug-123
```

**Trocando para um branch existente**

```text
git checkout bug-123
```

Neste caso, o ponteiro principal **HEAD** esta apontando para o branch chamado bug-123.

**Criar um novo branch e trocar**

```text
git checkout -b bug-456
```

**Voltar para o branch principal \(master\)**

```text
git checkout master
```

**Resolver merge entre os branches**

```text
git merge bug-123
```

Para realizar o _merge_, é necessário estar no branch que deverá receber as alterações. O _merge_ pode automático ou manual. O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.

A mensagem indicando um _merge_ manual será:

```text
Automerging meu_arquivo.txt
CONFLICT (content): Merge conflict in meu_arquivo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

**Apagando um branch**

```text
git branch -d bug-123
```

**Listar branches**

**Listar branches**

```text
git branch
```

**Listar branches com informações dos últimos commits**

```text
git branch -v
```

**Listar branches que já foram fundidos \(merged\) com o master**

```text
git branch --merged
```

**Listar branches que não foram fundidos \(merged\) com o master**

```text
git branch --no-merged
```

**Criando branches no repositório remoto**

**Criando um branch remoto com o mesmo nome**

```text
git push origin bug-123
```

**Criando um branch remoto com nome diferente**

```text
git push origin bug-123:new-branch
```

**Baixar um branch remoto para edição**

```text
git checkout -b bug-123 origin/bug-123
```

**Apagar branch remoto**

```text
git push origin:bug-123
```

#### Rebasing

Fazendo o **rebase** entre um o branch bug-123 e o master.

```text
git checkout experiment

git rebase master
```

Mais informações e explicações sobre o [Rebasing](http://git-scm.com/book/en/Git-Branching-Rebasing)

#### Stash

Para alternar entre um branch e outro é necessário fazer o commit das alterações atuais para depois trocar para um outro branch. Se existir a necessidade de realizar a troca sem fazer o commit é possível criar um **stash**. O Stash como se fosse um branch temporário que contem apenas as alterações ainda não commitadas.

**Criar um stash**

```text
git stash
```

**Listar stashes**

```text
git stash list
```

**Voltar para o último stash**

```text
git stash apply
```

**Voltar para um stash específico**

```text
git stash apply stash@{2}
```

Onde **2** é o indíce do stash desejado.

**Criar um branch a partir de um stash**

```text
git stash branch meu_branch
```

#### Reescrevendo o histórico

**Alterando mensagens de commit**

```text
git commit --amend -m "Minha nova mensagem"
```

**Alterar últimos commits**

Alterando os três últimos commits

```text
git rebase -i HEAD~3
```

O editor de texto será aberto com as linhas representando os três últimos commits.

```text
pick f7f3f6d changed my name a bit
pick 310154e updated README formatting and added blame
pick a5f4a0d added catfile
```

Altere para edit os commits que deseja realizar alterações.

```text
edit f7f3f6d changed my name a bit
pick 310154e updated README formatting and added blame
pick a5f4a0d added catfile
```

Feche o editor de texto.

Digite o comando para alterar a mensagem do commit que foi marcado como _edit_.

```text
git commit –amend -m “Nova mensagem”
```

Aplique a alteração

```text
git rebase --continue
```

**Atenção:** É possível alterar a ordem dos commits ou remover um commit apenas mudando as linhas ou removendo.

**Juntando vários commits**

Seguir os mesmos passos acima, porém marcar os commtis que devem ser juntados com _\*squash_

**Remover todo histórico de um arquivo**

```text
git filter-branch --tree-filter 'rm -f passwords.txt' HEAD
```

#### Bisect

O bisect \(pesquisa binária\) é útil para encontrar um commit que esta gerando um bug ou uma inconsistência entre uma sequência de commits.

**Iniciar pequinsa binária**

```text
git bisect start
```

**Marcar o commit atual como ruim**

```text
git bisect bad
```

**Marcar o commit de uma tag que esta sem o bug/inconsistência**

```text
git bisect good vs-1.1
```

**Marcar o commit como bom**

O GIT irá navegar entre os commits para ajudar a indentificar o commit que esta com o problema. Se o commit atual não estiver quebrado, então é necessário marca-lo como **bom**.

```text
git bisect good
```

**Marcar o commit como ruim**

Se o commit estiver com o problema, então ele deverá ser marcado como **ruim**.

```text
 git bisect bad
```

**Finalizar a pesquisa binária**

Depois de encontrar o commit com problema, para retornar para o _HEAD_ utilize:

```text
git bisect reset
```

**Gerenciar várias árvores de trabalho**

Gerencie várias árvores de trabalho conectadas ao mesmo repositório.

```text
git worktree
```

