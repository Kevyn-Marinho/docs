# Git commands 

## Init
Git init
Git init --bare - inicia um repositório vazio

## Status
git status

## Add
git add .

# Commit
git commit -m "mensagem aqui" 

## Config
// para configurar apenas  no projeto 
git config --local user.name "Seu nome aqui"
git config --local user.email "seu@email.aqui"
// para configurar na máquina 
git config --global user.name "Seu nome aqui"
git config --global user.email "seu@email.aqui"
// para visualizar a config
git config user.name 
git config user.email 

## Log
Para vizualizar o log de commits
git log - padrão
git log --oneline  - resumido 
git log -p - com as alterações
git log --graph

para mais http://devhints.io/git-log

## Remote
git remote add <nome do repo> <endereço de qualquer repositório, url ou caminho de pasta>
git remote rename <nome atual> <nome novo>

## Clone
git clone <url do repo remoto igual o de cima> <nome da pasta a ser criada localmente> 

## Push
git push <repositório> <branch>

git push <repositorio> <nome da tag>

// o "-u" seta o repositório como o padrão, é o que permite usar o "git push" sem passar o repo e a branch
git push -u <repositório> <branch>

## Pull
git pull <repositório> <branch>

## Branch
git branch - Lista as branchs
git branch <nome> - Cria um novo branch mas não muda vc de branch
git branch -d <nome> - Remove a branch informada
git branch -D <nome> - Remove a branch informada caso ela tenha alterações a mais que a master

## Checkout
git checkout <nome da branch> - Muda para a branch informada, mas não cria uma
git checkout -- <nome do arquivo> - desfaz as alterações do arquivo informado
git checkout -b <nome da branch> - Cria uma nova branch e muda para ela
git checkout <hash do commit> - Cria um estado temporário com o estado do projeto naquele commit informado

## Merge
git merge <nome da branch> - Cria um commit de merge contendo todas as alterações da branch informada para a branch atual

## Reset
git reset HEAD <Nome do arquivo> - Volda o arquivo pro estado inicial da branch antes de comittar

## Revert
git revert <hash do commit> - Cria um commit desfazendo as alterações do commit informado

## Stash 

git stash 
git stash list
git stash apply <id> - aplica sem remover do stash 
git stash pop <id> - aplica e remove do stash7


## Diff
git diff <hash commit>..<hash commit> - mostra toda as alterações entre os commits informados
git diff - Mostra as alterações não commitadas 

## Tag
git tag - lista as tags
git tag -a <nome da tag> -m "Lançamento de versão" - Cria uma tag 


## Rebase 
git rebase -i HEAD~3 - Une os ultimos 3 commits da branch atual
git rebase <nome da branch> - Copia todos os commit de merge contendo todas as alterações da branch informada para a branch atual mantendo o ultimo commit da própria branch como o mais atual


## Cherry-Pick
git cherry-pick <hash do commit> - Trás apenas as alterações DESSE commit informado para a branch atual 

## Bisect - Ajuda a indentificar quando um bug foi adicionado
git bisect start - inicia a busca

git bisect bad HEAD ~ informa pra busca que o estado atual está com problema
git bisect good <hash> ~ informa pra busca que o estado atual está sem o problema
git bisect reset - encerra a busca


## Show
git show <hash do commit> - mostra as alteraçõs do commit

## Blame
git blame <nome do arquivo> - mostra o responsável por cada linha e qual commit


# Repositórios online 

https://Github.com
https://Bitbucket.com
https://GitLab.com

# Ferramentas visuais

- Git Cola | https://git-cola.github.io/
- GitKraken | https://www.gitkraken.com/
- GitHub Desktop | https://desktop.github.com/ 


# Links Adicionais
https://git-school.github.io/visualizing-git/#free
https://git-scm.com/book/pt-br/v2/Customizing-Git-Git-Hooks


