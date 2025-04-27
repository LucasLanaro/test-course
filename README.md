# **Git Going Fast: One Hour Git Crash Course**

## **COMANDOS HELP**

- `git help`

Retorna a lista de comandos help gerais mais usados + Informações uteis

**HELP PARA SESSÕES ESPECIFICAS:**

- `git help pull`

- `git help config`

- `git help command`

## **PRE REQUISITOS**

- `pwd`

Mostra o diretorio atual de trabalho

- `git config --global user.name "Your Name"`

- `git config --global user.email "your.email@hotmail.com"`

Usando Git, todos os comandos digitados que não retornam nenhuma "noticia", é uma boa noticia (sucesso!)

- `git config --global --list`

Mostra as infomações globais do usuario e eamil

- `cat ~/.gitconfig`

Quando o gitconfig é setado, um arquivo .txt é criado na pasta Home com as infos do user. Usando o comando `cat` o sistema ira printar co conteudo desse arquivo de texto. O SO pode interpretar esse arquivo como um arquivo oculto, sendo necessario habililtar a visualização de arquivos ocutos (caso deseje ir no path para verificar como é o .txt)

> Configurações podem ser a nivel --global ou --user-level

## **INICIANDO**

Com o terminal ja na pasta do projeto executar o comando:

- `git init`

Caso não esteja na pasta do projeto, digitar `git init nome-do-projeto`

**Os icones que estão nos arquivos da pasta ficaram verdes com uma sigla de "U" em cada um deles**

![image.png](attachment:image.png)

Uma pasta ".git" sera criada de forma oculta aonde foi setado o init

No terminal, dentro da pasta do projeto o comando `ls -a` será possivel visualizar os conteudos ocutos atraves do bash

### STATUS

- `git status`

- Mostra o status do projeto do git

![image-2.png](attachment:image-2.png)

- Neste caso, não houve nenhum commit anterior

- Nenhum arquivo foi adicionado a lista dos a serem comitados

- Por padrão sempre virá na `branch master`

### PRIMEIRO COMMIT

- `git add README.md`

Adiciona os arquivos para o stage

Se for `git add .` todoas os arquivos serão adicionados ao stage

Os arquivos que estão no stage serão comitados com o comando

- `git commit -m "sua mensagem"`

O `-m` é para adicionar uma pequena mensage que descre este commit

### COMITANDO ARQUIVOS MODIFICADOS (APÓS UM COMMIT)

Ao inves de fazer todos o processo novamente de `git add README.md` e depois `git commit -m "sua mensagem"`, digitar o comando:

- `git commit -a`

OU

- `git commit -am "sua mensagem"` para adicionar uma mensagem junto

### REMOVENDO ARQUIVOS DO STAGE

- `git restore --staged README.md` remove o arquivo README.md do stage do git

- `git checkout -- README.md` volta o arquivo para a versão do commit anterior

### LOGS DOS COMMITS

- `git log` mostra a lista de commits feitos neste repositorio

- `git log --oneline --graph --decorate --color` mostra a lista de commits (mais resumida e comprimida)

### REMOVENDO ARQUIVOS COMMITADOS

- `git rm note.ipynb`

OU

- `rm note.ipynb` remove pelo proprio OS o arquivo (não pelo commit). Arquivo é apagado do diretório do SO. Como conseuquencia, o git entende que o arquivo foi deletado, logo é uma "Modificação"

Para adicionar essa alteração de arquivo deletado, é necessario o comando `git add -u`, e após isso `git commit -m "arquivo deletado"`

### MOVENDO ARQUIVOS

- `git mv main.py project`

Arquivo é movido para a pasta que é especificada (no git e no SO)

### IGNORANDO ARQUIVOS

- `.gitignore` é o arquivo que vai conter os arquivos ou extensões que sempre devem ser ignorados pelo git

**EXEMPLO:**

- `*.log`

- Todos os arquivos com extensão ".log" serão sempre ignorados

### SETANDO AUTENTICAÇÃO SSH

Se na sua pasta root (raiz) não tiver a pasta ".ssh", criar usando `mkdir .ssh`

Dentro detsa nova pasta, executar o seguinte comando:

- `ssh-keygen -t rsa -C "your.email@hotmail.com"`

Uma mensagem ira aparecer perguntando onde deseja salvar este arquivo. Como estamos ja na pasta correta, apertar "ENTER". Após isso, sera erguntado a senha e a confirmação

Abrir o arquivo do "id_rsa.pub", no Linux `nano id_rsa.pub` ou `cat id_rsa.pub` para poder ja printar e copiar a chave.

No **GitHub** ir em configurações do perfil e depois em SSH Keys

- Configurar o titulo como o nome do dispositivo que esta com essa key

Depois de configurada a chave, ir no temrinal e digitar:

- `ssh -T git@github.com`

### SUBINDO PARA O GITHUB

Criar o repertório para plataforma

Copiar o URL do repertorio como SSH

- `git push -u origin nome.da.branch`

### ALTERANDO COMMIT NO GITHUB

Boas praticas sugerem fazer um pull do repertório antes de fazer o novo push

- `git pull origin master`

- `git push origin master`