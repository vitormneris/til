# Primeiros passos com Git

## O que é o Git

O Git é um sistema de controle de versão distribuído usado para versionar arquivos, scripts, programas, projetos, entre outras coisas. 
Com ele podemos ter controle sobre alterações feitas nos arquivos rastreados e consolidados pelo Git.
Este controle possibilita dividir as alterações em commits, fazer rollback entre versões, criar ramificações, entre outras coisas. 
O Git em conjunto com plataformas como GitHub, SourceForge, GitLab ou BitBucket tornam o trabalho de desenvolver softwares em equipe muito mais organizado e fácil.

Trabalhar com Git traz segurança, permite trabalhar em equipe, permite "voltar atrás" caso você faça uma alteração no código que não for legal, dando liberdade para arriscar mais no projeto. 
Git foi criado por Linus Torvalds, o mesmo criador do kernel Linux. 

O Git possui uma estrutura de grafos, nele nada se perde, é possível recuperar tudo que já foi consolidado (ato de criar commit), apenas poderá haver mais trabalho para recuperar dependendo do que você tiver feito.
Ainda sim, é possível perder um commit para sempre, caso ele deixe de ser referenciado e o garbage collector do Git remova-o do banco de objetos.

## Conceitos importantes

Antes de vermos alguns comandos para versionar nossos projetos, precisamos entender alguns conceitos:

**Staging area:** É estágio anterior ao commit, um lugar onde os arquivos ou/e as modificações dos arquivos podem ser preparados para a consolidação. 

**Tracked e untracked:** Tracked pode ser traduzido como rastreado, quando um arquivo é marcado como tracked, significa que ele é considerado como parte do versionamento do Git.
 Dessa forma, suas alteração ficam sendo observadas pelo Git. O arquivo passa a ser tracked quando ele vai para a staging area, e permanece como tracked após a consolidação.
 Já no estado untracked, o arquivo fica fora do versionamento, de forma que as alterações feitas em um arquivo neste estado não são registradas pelo Git.

**Staged e unstaged:** Staged pode ser traduzido como preparado, o staged/unstaged determina se as alterações dos arquivos estão ou não na staging area, ou seja, determina quais alterações estão preparadas para serem consolidadas.
 Quando um novo arquivo é criado, ele não é staged nem unstaged, essa classificação existe apenas depois do arquivo se tornar tracked, após ir para a staging area ele torna-se tracked e staged, pois todo seu conteúdo é considerado modificação, porém após ser consolidado, ele deixa de ser considerado staged ou unstaged, apenas tracked.
 Se este arquivo for alterado, suas novas modificações passam a ser classificadas com unstaged.

**Branch:** Representa uma ramificação do versionamento, possibilitando que o histórico de versões não seja apenas linear. 

**Commit:** Representa uma nova versão do projeto/código/programa, pode ser traduzido como consolidação, ato de consolidar criações/alterações de arquivos e diretórios.
 Cada commit possui um código hash calculado a partir do conteúdo do objeto do commit virando seu identificador que pode ser usado para navegar entre eles.

**Repositório local:** Projeto que está sendo versionado, fica localizado na máquina do usuário. Todo o seu histórico fica armazenado dentro de uma pasta chamada .git na raiz do projeto.

**Repositório remoto:** Projeto que está sendo versionado, fica localizado numa máquina remota, tende a ser uma cópia do repositório local, apesar de poder ter branchs e commits distintos do repositório local. 
Para repositórios remotos, é comum usarmos plataformas online, o GitHub é a mais usada no mundo inteiro na atual data deste documento.

**.gitignore:** É um arquivo oculto onde colocamos todos os arquivos e diretórios que devem ser ignorados. Possui o formato de uma lista com nomes de diretórios e arquivos.
Não é necessário criá-lo do zero, podemos usar templates disponíveis na Internet em nossos projetos.

## Principais comandos Git

**Configura globalmente o nome de usuário.**

`git config --global user.name USER_NAME`

**Configura globalmente o e-mail de usuário.**

`git config --global user.email USER_EMAIL@EMAIL`

**Lista todas as configurações registradas na máquina, como user.name e user.email.**

`git config --list`

**Inicia o versionamento no diretório corrente gerando um repositório local. Este comando criará um diretório oculto chamado .git.**

`git init`

**Informa quais arquivos foram criados e modificados além de mostrar quais estão sendo rastreados ou não em um repositório local.**

`git status`

**Adiciona um arquivo para a staging area, tornando-o preparado(staged) e rastreado(tracked).
 Use . no lugar do nome para adicionar todos os arquivos.
 Ou use -i para adicionar os arquivos interativamente.**

`git add FILE_NAME`

**Remove um arquivo da staging area, tornando-o não rastreado(untracked) e não preparado(unstaged).
 Porém, se o arquivo já estiver consolidado, ele não se torna untracked, apenas unstaged.
 Use . no lugar do nome para remover todas os arquivos.**

`git reset FILE_NAME`

**Informa quais arquivos foram modificados e quais linhas foram alteradas desde o último commit.**

`git diff --staged`

**Informa o histórico de commits do repositório local. Use a flag --oneline para receber as informações de forma compacta.**

`git log`

**Lista todas as branches.**

`git branch`

**Renomeia a branch atual.**

`git branch -m NEW_NAME`

**Cria um novo commit dos arquivos tracked na staging area com uma mensagem/descrição.**
**A mensagem deve ser clara sobre o que foi alterado no commit.**
**Caso o parâmetro -m não seja utilizado, o Git abrirá um editor de texto (o Vim, por padrão em sistemas Unix-like) no qual você poderá escrever a mensagem.**

`git commit -m "MESSAGE"`

**Cria um novo commit dos arquivos tracked na staging area com uma mensagem, porém, diferente do anterior, este commit reformula o último substituindo-o.**

`git commit -m "MESSAGE" --amend`

**Cria um rótulo para o commit corrente, normalmente é especificado uma versão.**

`git tag VERSION`

**Navega entre os commits usando um código hash ou a tag estabelecida anteriormente.**

`git checkout HASH_OR_TAG`

**Mostra informações detalhadas do commit especificado.**

`git show HASH_OR_TAG`

**Envia o(s) commit(s) do repositório local para o repositório remoto na branch determinada.**1

`git push origin REMOTE_BRANCH`

**Baixa o(s) commit(s) do repositório remoto para o repositório local a partir da branch determinada e integra as atualizações na branch atual.**

`git pull origin REMOTE_BRANCH`

**Adiciona uma URL referente ao repositório remoto.**

`git remote add origin URL`

**Clona um repositório remoto a partir da URL determinada.**

`git clone URL`

**Remove o(s) último(s) commit(s) do histórico da atual branch, sem apagar os arquivos correspondentes ao commit. O número de commits apagados é determinado pelo valor numérico definido após o caractere '~'.**

`git reset --soft HEAD~COMMIT_NUMBER`

**Remove o(s) último(s) commit(s) do histórico da atual branch, apagando os arquivos correspondentes ao commit. O número de commits apagados é determinado pelo valor numérico definido após o caractere '~'.**

`git reset --hard HEAD~COMMIT_NUMBER`

**Cria uma nova branch e troca a branch atual para a recém-criada.**

`git checkout -b NEW_BRANCH`

**Troca a branch atual por outra existente.**

`git switch BRANCH`

**Desfaz as alterações não rastreadas desde o último commit.**

`git checkout -- .`
