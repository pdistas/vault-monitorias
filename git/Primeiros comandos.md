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

