# Tutorial de Git e Github na práftica


* [Link](https://git-scm.com/downloads)

## Versionamento local do projeto
* Acesse a pasta na qual o projeto está armazenado
* Clique com botão direito do mouse e selecione **Open Git Bash here**
* Digite `git init` para inicializar o repositório

  Será criada uma pasta chamada `.git`, **não** a apague
* Digite `git add.` para colocar os arquivos do projeto na **área de staging**  
<img src=https://i1.wp.com/www.markus-gattol.name/misc/mm/si/content/git_git_add.png>

* Digite `git commit -m "primeira versão do projeto"` para versionar **localmente** o projeto 
* Digite `git brach -M "main"` para renomear brach principal de `master` para `main`

## Criação de um repositório remoto no Github
* Acesse a sua conta do Github e clique em `New` para criar um novo repositório

    Coloque um nome para o respositório e preencha as informações do projeto, como a descrição 

* Para enviar o commit do repositório local (isto é, em sua máquina) para um repositório na plataforma do Github, digite por linha de comando `git remote add origin <link do repositório>`

    `origin` é o nome utilizado para referenciar o link do repositório remoto 

* Dessa forma, o repositório local já está vinculado ao repositório remoto do Github,
 entretanto a versão (isto é, o commit) não sobe automaticamente, por isso é necessário
 digitar: **`git push -u origin main`**

* Por fim, recarregue a página do Github e verifique se o projeto foi versionado
**remotamente**

# E quando o projeto for alterado? 

* Ao editar um arquivo já versionado ou mesmo criar um novo arquivo que não existia na versão anterior, **NÃO** é necessário inicializar novamente o Git por meio do comando `git init`,
sendo assim execute os seguintes comandos em ordem:
    `git add.`

    `git status` para verificar os arquivos que estejam aguardando na staging area 

    `git commit -m "escreva uma mensagem detalhando o que foi alterado>"`

    `git push -u origin novoBotao`

    Como é possivél notar, também **NÃO** é necessário renomear mais uma vez a branch (pois ela já estará renomeada como `main`), além disso, o link do reposotório remoto já estará 
    armazenado, por isso o comando `git remote add origin <link do repositório>` só é utilizado uma única vez 

* No Github será possível verificar todas as versões enviadas clicando em `commits`, de modo
que todas as alterações feitas estarão demonstradas

    O sinal verde `+` representa o que foi adicionado/modificado no vesionamento, enquanto o sinal vermelho `-` representar o que foi excluído de uma versão para outra  

## Brach 

* Até então, todos os versionamentos ocorreram na **ramificação principal (branch `main`)**
* Para criar uma nova branch, isto é, uma nova linha cronológica adicional/alternativa à
principal que possa posteriormente se juntar à `main`, digite `git checkout -b <nome da nova branch>`, assim o terminal Git será da branch `main`, criará uma nova com o nome que desejar 
e entrará nela, por exemplo: `git checkout -b novoBotao`

* Com uma nova branch criada, utilize os comando já explicados:

    `git add.`

    `git status para verificar os arquivos que estejam aguardando na staging area` 

    `git commit -m "escreva uma mensagem detalhando o que foi alterado>"`

    `git push -u origin novoBotao`

* No Github, as branches aparecerão assim:

    <img src ="img/imgBranch.PNG">

* Se necessário retornar para branch `main` pelo terminal do Git, digite `git checkout main`

## Merge

* Ao retornar para branch `main`, digite `git merge <nome da nova branch>` (no exemplo acima, seria a branch chamada novoBotao), desse modo será possível **unificar a branch alternativa e branch principal em uma só**

* Assim, tudo o que tinha de alteração na branch novoBotao (por exemplo) se juntará à branch `main`

* Para finalizar digite `git push origin main` e suba os arquivos para a branch principal do repositório remoto 

## Clone 

* Para fazer o download de um repositório remoto, seu ou de outro usuário, há duas opções:
* 1ª opção: clicar no botão `code` que se encontra no próprio Github e em seguida no botão `Download ZIP` , conforme imagem abaixo

    <img src="img/imgClone.PNG">

* 2ª opção: utilizando o mesmo link presente na imagem acima, abra o terminal e digite `git clone <link copiado do repositório remoto>`
**Observação**: é importante que ao repositório de sua própria conta no Github, verifique qual branch no Github está como `default`, pois
o **projeto clonado será aquele que se encontra na branch `default`**

## Pull 

* E se por exemplo o desenvolvedor digitar novos códigos em seu computador de casa e subi-los para o repositório remoto, percerber ao chegar 
no trabalho que o projeto na máquina do escritório está desatualizado ?

* Para puxar **todas as alterações realizadas do repositório remoto (Github) para o seu repositório local**, digite `git pull`

* testando na prática o git pull
