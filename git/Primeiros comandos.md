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

O "Untracked files" mostra todos os arquivos *ainda* não reconhecidos pelo git. E, abaixo, a mensagem explica o que deve ser feito: o comando `git add`, seguido do nome de um arquivo ou pasta, deve ser usado para incluir os arquivos. 

`git add .` é o mais usado para imediatamente incluir todos os arquivos modificados de uma pasta, entretanto, você pode informar arquivos individualmente, como `git add poema.txt`.

Seus arquivos adicionados passarão para o estado `staged`, ou seja, preparados.
O resultado do comando `git status` após um `git add .` será semelhante a:

```sh
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   passeio.png
        new file:   poema.txt
        new file:   roleta-russa.py
```



### `git commit`
O comando mais importante.
A **commit** é uma versão do seu programa, uma foto do estado dele em um determinado momento.

Ao adicionar arquivos e alterações com `git add .` eles estarão prontos para comporem uma nova versão do seu programa, a partir da commit.

`git commit -m "Mensagem da commit"`

Toda a commit deve possuir uma mensagem, colocada após o `-m` entre aspas. Normalmente, é usada para definir características daquela versão do programa (por exemplo, tela de busca de produtos, login, cadastro).
Além disso, cada commit está ligada a um autor, definido com o comando [[config#author|config]].

Comando executado: `git commit -m "Arquivos adicionados"`
Resultado do `git status`:

```sh
On branch main
nothing to commit, working tree clean
```

Como todos os arquivos adicionados já foram adicionados e commitados, ele te informa *working tree clean*.


---

## Fluxo de trabalho

Quando os arquivos do programa forem alterados, eles deverão passar pelo ciclo `add` -> `commit` novamente.

