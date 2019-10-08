# Guia para Git e GitHub

Guia desenvolvido para turma de sistemas para internet na Faeterj de Barra Mansa. O conteudo faz parte de um workshop realizado na propria unidade.

## instalação

[Link para download do Git]: https://git-scm.com/

### Abordagem do workshop

1. Historia
> O Git foi inicialmente projetado e desenvolvido por **Linus Torvalds** para o desenvolvimento do kernel Linux, mas foi adotado por muitos outros projetos.

2. Ferramentas similares
> CVS, Subversion, TFS e Mercurial.

3. Principais funcionalidades
> 1. Versionamento de codigo.
> 2. Documentação das alterações
> 3. Melhor trabalho em times

4. Como funciona o git e seus pontos na historia do projeto
> A cada passo finalizado o usuario cria uma nova versão do projeto "um novo ponto na historia"

### Comandos

- `git init [nome-do-projeto]` || *inicia um projeto criando uma pasta com o nome do projeto*
- `git init` || *inicia um projeto a partir da pasta atual criando com o nome da pasta*

#### Manipulando os arquivos e pontos na historia
- `git add` [nome-do-arquivo] || *adiciona um arquivo expecifico*
- `git add .` || *adiciona todos os arquivos*
- `git commit -m "Mensagem desejada"` || *adiciona um ponto na historia*

#### Informações sobre o repositorio
- `git log` || *log do repositorio*
- `git status` || *status atual do repositorio*
- `git show [id-commit]` || *verificar mudanças daquele commit*
- `git show` || *verificar mudanças do ultimo commit*

#### Trabalhando com branchs
- `git branch` || *listar branchs*
- `git branch [nome]` || *nova branch*
- `git checkout` || *trocar de branchs*
- `git merge` [nome] || *unir branchs*
- `git branch -D [nome]` || *deletar uma branch*
- `git checkout -b [nome]` || *branch e mudar para branch*
- `git git checkout [id-commit] -- [nome-do-arquivo]` || *restaura um arquivo na linha do tempo alterado ou deletado*

### Repositorio remoto

Como Repositorios remotos temos algumas opções: github, gitlab 

#### Lidando com um repositorio remoto
- `git remote add` [nome] [url-repositorio] || *adicionar repositorio remoto ao repositorio local*
- `git remote -v` || *listar repositorios remotos*
- `git push -u origin master` || *criando master no repositorio remoto* 
- `git pull` || *atualizando a base local com o conteudo do repositorio remoto*
- `git git clone` || *clonar repositorio / disponibilizar repositorio localmente*

### resolver um conflitos

1. Você está trabalhando em um projeto junto com seu time de devs
2. Por acaso vocês acabam alterando a mesma linha de codigo
3. Esse dev já realizou o merge para master
4. Ao voce tentar realizar um merge da sua branch atual para a master o git ira retornar um conflito
semelhante a esse:

```
CONFLICT (content): Merge conflict in teste.txt
Automatic merge failed; fix conflicts and then commit the result.
```
5. Para corrigir o conflito você deve escolher qual versão manter
6. Para manter o que está na master `git merge --abort`
7. Para substituir altere o arquivo e utilize `git add [nome do arquivo]` e `git commit-m "mensagem"`


## Arquivo .gitignore

Nesse arquivo vc colocara o nome dos arquivos, pastas, extensoes que vc não quer que seja adicionado ao seu repositorio.
