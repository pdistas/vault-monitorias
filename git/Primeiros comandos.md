# Como usar o git?

O fluxo de utilização do git acontece nas seguintes etapas:
- Arquivos são adicionados/editados
- Alterações são adicionadas
- Uma nova versão com as alterações é criada.

E de volta ao primeiro passo.
Vamos por partes.

---

## Comandos principais

### `git init`
Esse é o primeiro comando com que você deve se familiarizar.
Ele inicia, na pasta atual, um novo repositório git, para ser alterado e controlado usando a ferramenta. Crie uma pasta nova no seu gerenciador de tarefas, clique com o botão direito e selecione "abrir no terminal" ou similar, e execute o comando.

Caso seu gerenciador de arquivos esteja configurado para exibir arquivos ocultos, você notará que uma nova pasta foi criada: `.git`
Todos os arquivos referentes ao git estarão lá. 

> *Normalmente, você nunca vai precisar editar coisas que estão nessa pasta. Evite ao máximo. Essa pasta não é para o seu uso.*

Se você quiser sumir com o seu repositório git, pode simplesmente apagar essa pasta. Seus arquivos não serão danificados, mas você perderá acesso a versões antigas do seu projeto.

### `git add`
Adicione arquivos novos na pasta em que você inicializou o repositório. Qualquer coisa. Escreva um poema em um arquivo `.txt`, um programa em python, mova algumas fotos. Popule a pasta. 

Usando o comando `git status`, você deverá ter um output semelhante a esse:

```sh
On branch main # talvez seja master!

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	passeio.png
	poema.txt
	roleta-russa.py

nothing added to commit but untracked files present (use "git add" to track)
```

O "Untracked files" mostra todos os arquivos *ainda* não reconhecidos pelo git. E, abaixo, a mensagem explica o que deve ser feito: o comando `git add`, seguido do nome de um arquivo ou pasta, deve ser usado para incluir os arquivos. Por exemplo, caso você queira atualizar apenas um único arquivo basta apenas escrever o comando `git add (nome do arquivo)`. Porém, se for para atulizar todos os arquivos que foram alterados sem especificações, o jeito mais prático é adicionando um ponto ao final do comando `git add .`
Dessa forma todos os arquivos que sofreram alguma atualização estarão aptos a serem upados para o git.

Usando o comando `git status` agora, deverá aparecer esse output:

```sh
On branch main # talvez seja master!

No commits yet

Changes to be commited:
	(use "git rm --cached <file>..." to unstage)
		new file:	passeio.png
		new file:	poema.txt
		new file: 	roleta-russa.py

```

### `git rm`
Caso você deseja remover algum arquivo que já esteja na fila para ser commitado utilize o comando `git rm --cached (nome do arquivo)` para remover do stage.

### `git commit`
O commit é uma palavra muito comum no meio da programação, ela é utilizada quando deseja-se de fato postar, enviar, "publicar" algo. Então no terminal, após selecionar os arquivos que deseja atualizar com o comando `git add`, você deve usar o comando `git commit -m ""`. Um detalhe muito importante deste comando é o fato de sempre ser necessário ter uma mensagem de commit, que deverá ser escrita na área entre parêntes, o `-m ""` represente isso.

### `git remote`
Após criar o repositório no github é necessário ligar a sua pasta com o repositório, para isso você deve em seu terminar digitar o comando `git remote add origin (link do repositório)`. Para copiar o link do seu repositório você precisa entrar nele no github e clicar em **code**, depois selecione o link HTTPS e cole no comando.
> *O ctrl+v não funciona no terminal, para você colocar o texto é preciso utlizar o comando shift+insert*

### `git push`
Por fim, para enviar todas as alterações para o seu github utiliza-se o comando `git push origin (branch que deseja atualizar)`. Como a própria palavra diz, o push vai "empurrar" as alterações para o github, como no seu caso você vai estar utlizando a branch main, o comando é `git push origin main (ou master)`

### `git clone`
O git clone é o comando para você "clonar" o seu repositório da web para uma pasta. Para isso, basta abrir o terminal no local onde deseja clonar seu repositório e digitar o comando `git clone (link do repositório)`. Para copiar o link do seu repositório você precisa entrar nele no github e clicar em **code**, depois selecione o link HTTPS e cole no comando.

> *Observação importante: o que chamamos de repositório não passa de uma pasta que estará salva no github de sua forma, então quando dizemos que estamos "clonando" o repositório nada mais é do que criar uma pasta do repositório em seu computador*

### `git pull`
Caso você tenha feito alterações no seu repositório em outra máquina e agora queira "puxar" as alterações do github para sua máquina atual basta abrir o terminal na pasta de seu repositório e digitar o comando `git pull`. Assim todas as alterações que não estão presentes em seu computador serão "puxadas".
> *Muitas vezes alguma branch pode estar apenas no repositório remoto pelo fato de não ter sido utilizada no computador atual. Para puxar essa branch para o repositório local basta escrever `git pull origin (nome da branch)` no terminal*

### `git config`
O github sempre pedirá uma identificação para quem está fazendo os commits no repositório, então em alguns casos que você fez um clone de seu repositório em uma outra máquina será necessário que você utlize dois comando antes de fazer os commits. Esses comandos são: `git config --global user.name (seu nick)` e `git config --global user.email (seu email)`. Após isso não haverá nenhum problemas para fazer os commit se o problema estiver relacionado com a identificação 
> *Não é necessário colocar um email e usuário que esteja cadastro em seu repositório, o email e o usuário são apenas para identificar quem fez os commits. Outro importante para ressaltar é que o usuário e email ficam salvos na máquina, então nos laboratórios no caso de troca de computadores é muito comum que seu commit acaba aparecendo com o nick e email de outra pessoa caso você tenha trocado de máquina, portanto se atente a isso.*

## Comandos de branch

### `git branch`
Para criar uma nova branch basta digitar o comando `git branch (nome da branch)`. A branch não passa de uma ramificação da main, então tudo o que está na branch main será clonado para a nova branch. Deste ponto em diante todas as alterações feitas em uma branch não interferirão nos arquivos de outra branch. Para saber em qual branch você está basta olhar no terminal o que está escrito no parênteses azul em frente a localização do repositório. 

### `git checkout `
O comando `git checkout (nome da branch)` tem a função de trocar de branch. Caso você esteja na branch main e queira migrar para outra branch basta utilizar o comando `git checkout`, da mesma forma caso queira voltar para a branch main. 
> *Observe que sempre que você migra de branch os arquivos na pasta do repositório também mudam acompanhando os arquivos presentes na determinada branch*

### `git checkout`
Esse comando é apenas uma junção do `git branch` com o `git checkout`, ou seja, ao escrever o comando `git checkout -b (nome da branch)` você estará criando uma branch ao mesmo tempo que já migra para ela.

### `git branch -d`
O `git branch -d (nome da branch)` é um comando simples de exclusão de branch. Ao digitar esse comando a branch desejada será excluída de seu repositório

### `git merge`
O comando de merge é um pouco complicado e delicado, então é necessário ter atenção com suas versões em diferentes branchs. O `git merge` nada mais é do que uma mesclagem entre branchs, ele é muito utlizado quando é criado uma branch para cada usuário que está mexendo num mesmo projeto porém estão trabalhando em partes diferente, e ao fim eles juntam suas partes na branch main através do merge. Então, para você fazer o merge é necessário estar na branch que deseja receber as alterações e digitar o comando `git merge (nome da branch que deseja fundir)`.
> *Observação importante!!! É de extrema importância ressaltar que é muito comum ocorrer conflitos de versões quando dois arquivos sofrem alterações diferentes em cada branch e nesses casos cabe ao usuário arrumar esses conflitos, para previnir que conflitos ocorram é recomendado que em cada branch sejam alterados arquivos ou diretório diferentes que não conflitem entre si. O merge é um recurso pouco utlizado nos cotidianos dentro do curso, porém recomendamos que seja devidamente praticado, esse arquivo nada mais é do que um pequeno guia e ajuda.*

