# Comandos Principais do Git

Projeto de estudo dentro do Programa DevStart da BeAcademy em parceria com a PayLivre.
Comandos principais do git apresentados no módulo Git e GitHub.

![Logo](https://www.beacademy.com.br/wp-content/uploads/2022/02/Cubo.png)

## Comandos / Descrição

A primeira coisa que você deve fazer quando instalar o Git é definir o seu nome de usuário e endereço de e-mail. Isso é importante porque todos os commits no Git utilizam essas informações.

```git
git config --global user.name "Adriano de Oliveira"
git config --global user.email adriano.98@gmail.com
```

Basta fazer isso uma vez na máquina que está sendo instalado o git.

### Iniciando o Repositório

Para iniciar o repositório na máquina, basta ir até a pasta e digitar

```git
git init
```

### Clonando um repositório existente

Basta acessar o repositório que deseja clonar e usar o link https ou ssh (dependendo da configuração de segurança)

```git
git clone [url]
```

### Adicionando arquivos e pastas no monitoramento

Quando um repositório é inicialmente clonado, todos os seus arquivos estarão monitorados e inalterados porque você simplesmente os obteve e ainda não os editou. Conforme você edita esses arquivos, o Git passa a vê-los como modificados, porque você os alterou desde seu último commit.
Para passar a monitorar um novo arquivo, use o comando git add.

```git
git add arquivo
```

Observações: "git add -A" é usado para adicionar todos o seus arquivos, ou seja, "novos", "modificados" e arquivos "deletados". O "git add ." é usado para adicionar arquivos novos e modificados mas não os deletados. Já o "git add \*" é usado para adicionar arquivos novos e modificados do diretório atual.

### Verificando o status

A principal ferramenta utilizada para determinar quais arquivos estão em quais estados é o comando:

```git
git status
```

### Verificando mudanças

Este comando não foi passado na aula, mas é muito útil. Pode ser usado quando o git status for muito vago. Serve para saber exatamento o que foi alterado, não apenas quais arquivos foram alterados.

```git
git diff
```

### Commits

Armazena o conteúdo atual do índice em um novo commit, juntamente com uma mensagem de registro do usuário que descreve as mudanças.
Se usa o commit depois de já ter feito o git add, para fazer o commit:

```git
git commit -m "Mensagem"
```

### Desfazendo coisas

Para voltar ao último commit:
```git 
git reset --hard HEAD~1
```

Para voltar ao último commit e manter os últimos arquivos no Stage:
```git
git reset --soft HEAD~1
```

O comando revert cria um commit que desfaz todas as modificações do commit que você corrigir. 
```git
git revert
```

### Branchs e Merge

Um branch no Git é simplesmente um leve ponteiro móvel para um dos commits. O nome do branch padrão no Git é master. Como você inicialmente fez commits, você tem um branch principal (master branch) que aponta para o último commit que você fez. 
Por convenção, hoje se utiliza a banch principal como "main".

Para criar uma nova branch:
```git
git branch NOMEDABRACH
```
Para saber em qual branch está:
```git
git branch
```

Para mudar de branch
```git
git checkout {nome_da_branch}
Obs. adicionando o parâmetro -b, também cria a branch, caso ela não exista.
```

Para deletar a branch
```git
git branch -d "nome da branch"
```

Depois que o trabalho estiver pronto e as funcionalidades ok e testadas, pode se fazer o merge.  Tudo que você tem a fazer é executar o checkout do branch para onde deseja fazer o merge e então rodar o comando git merge:
```git
git checkout main
git merge branchimplantantada
```

### Histórico de Commits
Depois que você tiver criado vários commits, ou se clonou um repositório com um histórico de commits existente, você provavelmente vai querer ver o que aconteceu. A ferramente mais básica e poderosa para fazer isso é o comando:

```git
git log
```

### Stash
Muitas vezes, quando você está trabalhando em uma parte do seu projeto, as coisas estão em um estado confuso e você quer mudar de branch por um tempo para trabalhar em outra coisa. O problema é, você não quer fazer o commit de um trabalho incompleto somente para voltar a ele mais tarde. A resposta para esse problema é o comando git stash.
Você quer mudar de branch, mas não quer fazer o commit do que você ainda está trabalhando; você irá fazer o stash das modificações. Para fazer um novo stash na sua pilha, execute:
```git
git stash
git stash pop (restaura alterações salvas)
git stash pop stash@{1} (aplica stash especifico)

```
Seu diretório de trabalho estará limpo.
Neste momento, você pode facilmente mudar de branch e trabalhar em outra coisa; suas alterações estão armazenadas na sua pilha. Para ver as stashes que você guardou, você pode usar:
```git
git stash list
```
Você pode aplicar aquele que acabou de fazer o stash com o comando mostrado na saída de ajuda do comando stash original: git stash apply.


### Compartilhar e Atualizar Projetos
O comando git fetch pode ser usado para baixar todos os commits do repositório remoto sem afetar o seu código local.
```git
git fetch origin
```

O comando git pull existe por ser uma forma mais semântica e simples de "puxar" o código, mas na realidade ele simplesmente acaba executando fetch e em seguida merge.
```git
git pull origin main
```

O git push é o comando em que você transfere commits a partir do seu repositório local para um repositório remoto.
```git
git push origin main
```

### Repositório Remoto
Para exibir o repositório remoto selecionado
```git
git remote
```


## Autor

- [@adrianoarch](https://www.github.com/adrianoarch)
