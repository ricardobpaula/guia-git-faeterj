# Guia para Git e GitHub

Guia desenvolvido para turma de sistemas para internet na Faeterj de Barra Mansa. O conteúdo faz parte de um workshop realizado na propria unidade.

## instalação

[Link para download do Git](https://git-scm.com/)

### Abordagem do workshop

1. História
> O Git foi inicialmente projetado e desenvolvido por **Linus Torvalds** para o desenvolvimento do kernel Linux, mas foi adotado por muitos outros projetos.

2. Ferramentas similares
> CVS, Subversion, TFS e Mercurial.

3. Principais funcionalidades
> 1. Versionamento de código.
> 2. Documentação das alterações
> 3. Melhor trabalho em times

4. Como funciona o git e seus pontos na história do projeto?
> A cada passo finalizado o usuário cria uma nova versão do projeto "um novo ponto na história"

### Comandos

- `git init [nome-do-projeto]` || *inicia um projeto criando uma pasta com o nome do projeto*
- `git init` || *inicia um projeto a partir da pasta atual criando com o nome da pasta*

#### Manipulando os arquivos e pontos na história
- `git add [nome-do-arquivo]` || *adiciona um arquivo específico*
- `git add .` || *adiciona todos os arquivos*
- `git rm [nome-do-arquivo]` || *remove um arquivo específico do stage e do working*
> Working é o que você ainda está trabalhando e ainda não foi adicionado ao commit

> Stage é o que está adicionado ao commit utilizando o `git add`
- `git rm --cached [nome-do-arquivo]` || *remove um arquivo específico do stage*
- `git commit -m "Mensagem desejada"` || *adiciona um ponto na história*

#### Informações sobre o repositório
- `git log` || *log do repositório*
- `git status` || *status atual do repositório*
- `git show [id-commit]` || *verificar mudanças daquele commit*
- `git show` || *verificar mudanças do ultimo commit*

#### Trabalhando com branchs (ramificações)
- `git branch` || *listar branchs*
- `git branch [nome]` || *nova branch*
- `git checkout` || *trocar de branchs*
- `git merge [nome]` || *unir branchs*
- `git branch -D [nome]` || *deletar uma branch*
- `git checkout -b [nome]` || *branch e mudar para branch*
- `git checkout [id-commit] -- [nome-do-arquivo]` || *restaura um arquivo na linha do tempo alterado ou deletado*

### repositório remoto

Como repositórios remotos temos algumas opções: github, gitlab, entre outros.

#### Trabalhando com um repositório remoto
- `git remote add [nome] [url-repositorio]` || *adicionar repositório remoto ao repositório local*
- `git remote -v` || *listar repositórios remotos*
- `git push -u origin master` || *criando master no repositório remoto* 
- `git pull` || *atualizando a base local com o conteúdo do repositório remoto*
- `git git clone` || *clonar repositório / disponibilizar repositório localmente*

### resolvendo conflitos

1. Você está trabalhando em um projeto junto com seu time de devs.
2. Por acaso vocês acabam alterando a mesma linha de código.
3. Esse dev já realizou o merge para master.
4. Ao você tentar realizar um merge da sua branch atual para a master o git ira retornar um conflito.
semelhante a esse:

```
CONFLICT (content): Merge conflict in teste.txt
Automatic merge failed; fix conflicts and then commit the result.
```
5. Para corrigir o conflito você deve escolher qual versão manter.
6. Para manter o que está na master `git merge --abort`
7. Para substituir altere o arquivo e utilize `git add [nome do arquivo]` e `git commit-m "mensagem"`


## Arquivo .gitignore

O arquivo .gitignore é onde são inseridas as regras do repositório, tudo que o git deve ou não inserir no versionamento.
Os principais arquivos que não devem entrar no versionamento são arquivos contendo variaveis de ambiente, arquivos que fazem parte das configurações de ambiente do desenvolvedor e arquivos gerados por compilação.
