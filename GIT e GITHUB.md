# Tópicos Fundamentais para entender o funcionamento do GIT

   * SHA1 - A sigla significa Secure Hash Algorithm (Algoritmo de Hash Seguro), é um conjnto de funções hash criptográficas projetadas pela NSA( Agencia de Segurança nacional dos EUA) A encriptação gera conjunto de characteres identificador de 40 dígitos.

## Objetos internos do GIT

Objetos responsáveis pelo versionamento do nosso código:
   - BLOBS - Bloco básico de composição - só guarda o SHA1 do arquivo
   - TREES - Armazenam e apontam os Blobs - Guarda a estrutura e  onde estão localizados os arquivos, podem apontar para outras TREE
   - COMMITS - É o objeto que vai juntar tudo, que vai dar sentido a alteração que esta sendo feita.

## Ciclo de vida

-> Untracked - Arquivos que o Git não sabe de sua existência, acabado de criar ( antes de dar o comando git add) depois deste comando ele vai p git e começa o versionamento (vai para Staged)
Dentro de Tracked (arquivos rastreáveis pelo GIT) se divide em 3 estágios :

-> Unmodified - arquivo não modificado dentro do repositório do GIT ( antes do comando git init) quando ele for alterado, o GIT muda ele automaticamente para Modified. Se ele for removido, ele volta para Untracked.

-> Modified - arquivo modificado, se rodar o GIT ADD nele novamente, ele vai para Staged

-> Staged - Ficam os arquivos que estão se preparando para fazer parte de outro tipo de agrupamento. Se der um commit nele, ele volta para Unmodified.

##  Ambiente de desenvolvimento

 -> Working Directory - arquivo Untracked, ou seja, o git não tem o conhecimento dele, e vc da um git add, ele é movido para Staged e para a area de Staging Area, os arquivos ficam transitando entre a working Directory e a área de Staging. 

 -> Staging Area - após o comando git add os Arquivos se tornam Mofied e Staged, apos o comando do commit -m, eles vão para nosso repositório local,

 -> Local Repository - Quando fazemos o commit na Staging Area, os arquivos são movidos para nosso repositório local, ele sera composto apenas por commits, caso contrario vc não consegue mover para o repositório remoto.

  ## Comandos básicos para um bom desempenho no terminal
no Windows

 - cd -> Chanded Director, para mudar de diretório (entra na pasta)
 - cd .. -> volta um diretório (pasta)

Quando estamos lidando com um terminal sempre coloca o nome do programa na frente cd. 
 - vim - É um editor de texto que ja instalado no GIT.
 - dir ou ls -> Lista repositórios na pasta onde estamos
 - mkdir -> criar diretórios (pasta), após digitar mkdir de espaço e digite um nome para seu diretório.
 - del/rmdir -> deletar
 - rmdir -> deleta diretório
 - rm -rf -> Força deleta diretório
 - touch -> Cria um arquivo, após este comando, você digita um nome para o arquivo e depois coloca um ponto (.) e a extensão dele, como .txt
 - cat -> para ver o conteúdo do arquivo
 - CTRL+L ou comando cls -> limpa o terminal
 - A tecla TAB auto completa o nome das pastas
 - ls -> lista diretórios
 - ls -a -> Mostra Arquivos ocultos   
 - Seta p cima navega no histórico de comandos dados 
 - echo > (com sinal de maior) -> Cria um arquivo, depois do comando, você digita o nome de arquivo e depois coloca um ponto (.) e a extensão dele, como .txt. Vc tb pode escrever alguma coisa dentro do arquivo digitando echo "mais a frase sem estas aspas" >(sinal de maior) e o nome do arquivo.
 - git init -> iniciar repositório no git  (cria) este comando, além de criar a pasta do git, cria um repositório dentro do diretório(pasta)
 - git add nome do arquivo-> mover arquivos e começar o versionamento
 - git add * ou git add. -> Ele pega tudo que foi modificado, que esta na Working Directory (diretório de trabalho) e adiciona p área de Staged, para poder commitar
 - git commit -> cria commit 
 - git push - > sobe o commit para o github.
 - git pull -> puxa um repositório para sua maquina local
 - git status ->Comando para monitorar o status dos arquivos, vai dizer se o arquivo esta Untracked, Modified, Staged...  
 - git clone -> Serve para baixar um repositório do GitHub, vc digita o comando git clone e cola o link do repositório no GitHub 
 - git remote -v -> ele vai trazer os repositórios remotos que o repositório clonado esta apontado
 - git config --list - tras a lista de todas configurações que estão no seu git. Caso queira alterar alguma informação use git confg --global --unset (e a propriedade especifica da configuração, como user.email ou user.nickname, ex: git confg --global --unset user.e-mail. Este comando vai limpar as informações de e-mail do seu git, para conferir use o comando git config --list, sem estas informações vc não faz um commit, ele vai pedir que vc se identifique.
Para reinserir as informações tire o --unset e insira a nova, ex:git config --global user.e-mail "seu e-mail do github"
 - mv -> comando para mover ou renomear documentos. Para mover digite mv (nome do arquivo) (caminho + nome da pasta ou apenas o nome da pasta se estiver no mesmo nivel) Para renomear digita mv (nome do arquivo) (novo nome do arquivo). Se tiver espaço no nome (mais de uma palavra) tem que usar aspas (") antes e depois.
 - pwd -> Comando para mostrar o local que vc esta
- openssl sha1 -> (nome do arquivo) mostra o codigo sha1 dele.

**Criando um repositorio pelo terminal


1ª Abrir o Git bash e Criar uma pasta -> mkdir + nome da pasta nova

2ªIniciar o GIT dentro da pasta -> usar git init para poder inicializa-lo e possibilitar que o git comoce de fato a gerenciar e versionar o nosso código ( a pasta não aparece, ela é oculta, é uma pasta gerencial do Git, onde fica o código do git, onde ele versiona) para vizualizar ela tem que usar uma flag especifica no comando ls que é a flag -a, ela mostra arquivos ocultos

3ªCriar um arquivo dentro da pasta - pode ser em Markdown, .txt ..... 

4ªComitar o arquivo ->git add*, depois um git commit -m (flag do git commit) depois abri uma string  "", passar uma menssagem para este commit, falar sobre oq ele faz.

5ª Se vc parar o arquivo e fizer uma modificação, ele vai seguir o fluxo e voltar a ser Modified, e volta para o fluxo.

6ª Criar um repositorio no GitHub para empurrar o commit, para isso, clique na foto de seu perfil que esta no canto superior esquerdo, selecione "Your Repositories", clique em "novo", ele vai pedir o nome do novo repositorio e uma descrição, na opção para flegar se vc Vai iniciar um repositorio com o README, vc marca apenas se não tiver criado um arquivo README em Markdown, caso tenha, não precisa. O Github quando encontra um arquivo markdown e expoem para pessoa que esta acessando aquela pasta em especifico, quando o github encontrar um arquivo markdown ele vai mostrar como aparece no Typora, estes arquivos que contam a historia do repositorio a funcionalidade dele, são chamados de README.

Com o repositorio criado, vc tem q apontar o repositorio local para o repositorio do github, para isso, basta copiar a url que o git da para fazer o pusch, ir no gitbash e inserir git  remote add origin (e colar o link copiado do repositorio) dar enter.

se vc der um git remote -v ele vai mostrar a lista de repositorios cadastrados. O "origin" significa apenas um apelido para que não tenha que ficar digitando um endereço  https.

7ª git push origin (origin - que é o apelido que deu para o repositorio no github) master (é a branch que esta empurrando o codigo) git push origin master.

*** Resolvendo conflitos:

Se duas pessoas clonarem o mesmo arquivo ao mesmo tempo e começam a editar este arquivo de forma diferente, significa que o arquivo não esta mais em sincronia, quer dizer que o codigo do github é um, o da sua maquina é outro e o q esta na maquina da outra pessoa é outro. Sendo que o codigo que esta maquina da pessoa e na sua, comtem auterações na mesma linha, e é justamente quando ha ediçoes na mesma linha que ocorrem o problema.

Vamos supor que a pesso "A" continuopu e empurrou o codigo para o github novamente e vc continuou editando.

Então, agora, o codigo que estava no github é o q estava na mauina da pessoa "A" e o seu codigo esta desatualizado.

Para fazer isso o github vai informar que o seu codigo (pessoa "B") esta desatualizado, ele vai pedir para puxar a versão mais recente ( atualizada pela pesso "A") fazer as alterações, juntar oq vc fez, e empurrar para o git de volta. É neste momento que acontece o conflito de "Merge" quando o github tenta juntar o codigo e existe duas alterações na mesma linha
