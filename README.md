# Pc-TesteFrontEnd


1- A gente vai fazer uma atividade relacionada ao Jmeter em relação a teste de
desempenho.
A gente tá aqui com o projetinho que é disponibilizado pra vocês na atividade 2, é um
projetinho de API e no caso, antes de conseguir executar ele, fazer o nosso Jmeter 
funcionar nós vamos precisar executar esse projeto. Mas pra executar esse projeto eu
vou precisar de duas coisas:
A 1ª é que já foi feito um build aqui em um arquivo feito em Angular que no caso
seria colocar ali no modo de produção. Então ele criou esses arquivos aqui, ele
converteu o Typescript em um projeto Angular e está convertido em HTML e 
JavaScript.
E por último também vai ter aqui uma API, chamada db.json, então eu vou
precisar executar o db.json e executar o nosso index né
Porquê?
Porque como a gente vai fazer o teste de desempenho com o Jmeter usando o 
protocolo HTTP, eu vou precisar acessar o HTTPClient dele né que a gente vai simular
o servidor pra executar esse projetinho aqui.
Então a primeira coisa que a gente vai precisar verificar é se o node.js está instalado
na máquina de vocês, a gente vai precisar dele pra executar tanto o json-server que
vai ser responsável por executar a API, que no caso é o db.json quanto o HTTPClient 
que vai ser o servidor pra gente executar esse index aqui.
Então eu vou utilizar aqui o comando CMD na que eu estou aqui do projeto

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/828593da-fb1c-4aa4-af6b-c1f8edcf6889)

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/0c17faa1-b345-4f9f-a2b4-935ffd07fec9)

Eaí estando dentro da pasta do projeto, a gente vai fazer o seguinte:

npm install -g json-server


E para executarmos aqui projeto da API do index o comando vai ser:

npm install -h http-server


Agora nós vamos precisar de 2 CMDs, um para executar o json-server e outro para
executar o HTTPClient.
Vamos lá, no primeiro CMD nós vamos executar o comando:

json-server --watch db.json


Agora no outro CMD nós vamos executar o comando:

http-server

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/7f641603-7fa7-46be-aab7-9bece2560d95)


Esses daqui vão ser os IPs do endereço do nosso projeto que pode ser qualquer um
desses dois eu vou ficar com o de baixo aqui

Copiar o IP de baixo e colar no navegador

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/ed1ebec1-54ce-459f-9db9-7f115091fbf8)

Agora vocês podem ver que o nosso projeto está funcionando, e podemos ter certeza
que o nosso json-server está funcionando porque ele está listando os dados.
Então se eu for no navegador e colocar aqui localhost:3000/clientes


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/88350d4a-0479-4d61-9840-11565be3c859)


Porquê?
Porque se a gente abre aquele nosso arquivo db.json, vou abrir aqui com o bloco de
notas cês vão perceber que vai aparecer aqui o clientes, esse clientes é o que define
aquele /clientes que vocês viram lá no navegador, onde está a lista dos nossos
clientes, dentro de um array.
Excluir um usuário (no navegador mesmo) para eles verem que
está funcionando
Agora já podemos ir para o Jmeter então
Baixar com eles a versão do Jmeter 5.5:
https://jmeter.apache.org/download_jmeter.cgi
Para gente executar o Jmeter nós vamos acessar aqui a pasta bin

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/a3cdee80-1b03-42dd-84b4-6303c179fd37)


Uma coisa importante, a gente precisa ter instalado na nossa máquina o Java na
versão oito para mais, podem acessar o site da Oracle porque o Java é da Oracle 
Mostrar para eles onde baixa o Java: https://www.java.com/pt-BR/
UC11 - Testes de Front-End 6
Vocês podem acessar aqui o site do java.com, a gente clica aqui Fazer Download do
Java mesmo, pode pegar da versão oito para cima. Qualquer uma delas acima da 8 a
gente vai precisar para poder executar o Jmeter porque ele é uma ferramenta que foi 
construída com a linguagem Java,
então a gente precisa do Java funcionando nosso computador para que ele funcione.
Vamos lá, para executar o Jmeter vamos acessar aqui a pasta: bin e rodamos o
executável “ApacheJMeter”
Fazendo isso vai aparecer o Jmeter aqui pra gente, caso não dê certo para você, é só
procurar um arquivo chamado jmeter com o tipo “Arquivo em Lotes do Windows” 

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/ee4d6f43-33e5-4195-856c-2fd6f673bd28)


Então clico duas vezes, ele vai abrir essa telinha preta aqui (que chamamos de
terminal), com isso ele vai forçar a execução do Jmeter. Aí vai aparecer o Jmeter pra
vocês, a única coisa que pode ser um problema é que ele vai executar em inglês!
Dar um overview no sistema
UC11 - Testes de Front-End 7
Agora vamos para a parte do nosso querido Desenho de Teste, primeiro vamos
executar o teste, então vou aqui nesse plano de teste que ele criou e vou dar um clique
direito nele → Adicionar → Threads (Users) → Grupo de Usuários

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/bea91a01-f303-400d-9425-8742adfb92ed)

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/08fd0467-f15b-409e-86a7-0576c463610b)

Aqui em “Número de Usuários Virtuais (threads)” a gente estipula quantos cadastros
serão feitos, então vamos colocar 1000, o tempo de inicialização a gente pode
UC11 - Testes de Front-End 8
colocar de quanto em quanto tempo um usuário é cadastrado (em segundos), aqui
vamos manter o que já está preenchido.
Agora vamos dar um clique direito em: Grupo de Usuários → Adicionar → Testador
→ Requisição HTTP


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/82e6cbc1-d97a-4785-85d2-981f229e1ac0)

Após isso nós já vamos colocar para ele mostrar pra gente o resultado dando um clique
direito em: Grupo de Usuários → Adicionar → Ouvinte → Ver Árvore de
Resultados



![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/720c574a-7371-4ed8-8403-423c090f50b3)

E vamos falar para ele nos trazer os resultados em tabela, clique direito em: Grupo de
Usuários → Adicionar → Ouvinte → Ver Resultados em Tabela


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/fe747d16-6852-412b-9c01-062477a29c47)

Então isso aqui é o que precisamos:

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/4c760a6c-df5f-4eda-88bd-cba66a2657c3)

Agora vamos lá, configurar tudo. Primeiro vamos pegar o link da nossa api!

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/1d5aa580-a0b9-41d8-b37a-7877e1bb1c0b)

Pegar o link no terminal que já está aberto (Resources)

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/b9ccb50c-cc07-4492-aa82-d20824dc108a)

Preencher na Requisição HTTP

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/c86d1b49-bae4-434b-8b5a-6bc6c45ced8f)

Vamos aqui em Body Data

Porque como definimos a resquisição como POST precisamos passar o corpo, vamos
copiar a estrutura lá da nossa aplicação

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/c18fa31f-da41-471c-9fc8-a99e93e86d0a)

Só vamos precisar disso aqui e colamos dentro do Body Data, o id não vamos precisar
mandar já que a API vai criar os ids para gente
Completar com dados fake para cadastrar
Agora vamos dar um clique direito em: Requisição HTTP → Adicionar → Elemento
de Configuração → Gerenciador de Cabeçãlhos HTTP


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/cf27210b-9232-41bd-8ed3-d54bff90b53c)

Nós precisamos configurar isso porque estamos trabalhando com requisições HTTP,
então precisamos passar algumas configurações dentro do cabeçalho da requisição
Então vamos clicar aqui em Adicionar e vamos preencher:

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/30030017-b245-4e45-8b68-073a1f05c616)

Nome
“Content-type”
Value
“application/json:charset=UTF-8”
E clica em Adicionar → Salvar
Então podemos apertar aqui para Salvar

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/85076729-f3c1-4d5e-aff1-4de81c642641)


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/33381a25-761a-40a9-8bde-76856ac442b4)

Ele vai ficar salvo na pasta /bin mas é a pasta que fica lá dentro do Jmeter
Salvar com o nome “testeDeDesempenho”
Feito tudo isso, vamos clicar em Grupo de Usuários e vamos executar


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/92475242-28f4-4c8f-9190-c84e07de2da7)

*Dá OK e salva com o nome “AtividadeTeste”
Vamos ver o resultado:

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/7bc6f1d0-f593-4cb6-8b0c-488fca2719d7)


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/1c502373-3a69-477e-aa41-5af479e35dfa)



![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/5e4617d9-bb55-454d-a5e6-68223f7cf1c0)


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/ea8cf0fa-8b3b-477e-93cc-118845050a3c)

Agora vamos para o Selenium, primeiramente nós baixamos o Projeto-API (no
material) e fazemos a descompactação da pasta. Na pasta descompactada nós temos
UC11 - Testes de Front-End 18
aqui esses pacotes gerados pelo próprio Angular.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/2ab590e2-f25e-4a73-ac95-ff0d8dd28ecc)


Então nós vamos rodar uma aplicação Angular e à partir dessa aplicação nós vamos
executá-la de forma local para depois fazermos o teste no Selenium.
À princípio nele vocês podem fazer qualquer tipo de teste em qualquer tipo de site,
como visto no material, mas nesta atividade nós vamos fazer os testes automatizados
via Selenium em um projeto que vai rodar de forma local.
Agora, que nós temos já o nosso projeto, vamos executá-lo. Vamos clicar aqui em 
projeto-API


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/f8d27ee8-c441-4eac-a8d2-38225226e46b)


E aqui nós temos a distribuição de um projeto Angular e essa distribuição precisa ser
executada aqui de forma local, porém como nós não estamos utilizando um servidor
web ele não vai executar.
Então se eu clicar aqui por exemplo no arquivo index.html duas vezes


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/10a69a7c-df84-4256-bee9-6dc5f26c8b85)


Ele não vai me retornar nenhum tipo de informação, né? 
Porque ele só vai retornar alguma coisa dentro de um projeto ou dentro de uma
aplicação web.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/4d7e3a4d-c797-4fc3-9fb5-0891db6ecd08)


Então, aqui dentro da barra de endereço do explorador de arquivos, vamos digitar cmd

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/62ab7ce3-1a07-406b-9afd-de9dc4ba71c4)


Observem que nós estamos na mesma pasta


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/58a76b4b-a901-463e-902d-599e49b281fb)

Aqui nós vamos instalar o nosso http-server, que é o nosso servidor de aplicação da
porta 8080 (porta padrão) ou servidor de aplicação web.
Primeiramente, a gente precisa ter o node instalado na máquina e windows é daquele
jeito né, então você faz o download dele, ele instala, é um next next finish, é bem
tranquilo o node. Após instalar o molde o CMD do Windows ele vai estar habilitado pra
poder receber comandos do node.

Então, após a instalação do node nós podemos digitar aqui:

npm install http-server -g




Com esse comando nós vamos fazer agora o download desse pacote http-server para
a máquina e após o download nós vamos poder executar transformar a nossa máquina
em um servidor de aplicação web.

E nós vamos fazer também o download do pacote json-server, o json-server ele
transforma a máquina em um servidor json, ou seja, um servidor que consegue enviar
e/ou receber requisições HTTP no formato json.

Vamos baixar ele então, com o seguinte comando:


npm install json-server -g

Então nós fizemos o download dos dois pacotes e agora nós podemos executar o
nosso HTTP server, para isso vamos utilizar o comando:

npx http-server

Lembrando que dependendo da máquina eh pode ser NPX ou NPM tá? Depende muito
do seu computador mas em geral NPX ele roda em qualquer máquina.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/b100eddd-6e54-4dae-8479-fa83a840dd9f)

Então observem que nós habilitamos o http-server dentro desta pasta, isso significa
que ele transformou essa pasta aqui numa publicação web. É uma publicação web
local mas é uma publicação web.

Nós temos aqui o endereço de ip


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/0641b2e0-fd05-4af0-adaa-f4bbbb998fce)


Então vamos acessá-lo

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/99799bea-cf94-48ad-a846-fb502c9e98bd)


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/0c00b235-a3ff-43e1-bef7-36ee1eca8222)




Aqui conseguimos ver ele já conseguiu carregar a nossa aplicação Angular e ele veio
aqui pra rota /listar de forma automática né, porque nós só colocamos o IP que é o
nosso index e ele já trouxe a gente pra cá.

UC11 - Testes de Front-End 23
Então até aqui nós ainda não respondemos o exercício, nós simplesmente executamos
a aplicação. Para que ela rode da forma correta, estão faltando os dados também,
certo?

Para que rodemos os dados nós vamos abrir um outro CMD dentro dessa pasta e
vamos executar o arquivo db.json.


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/95aeb4be-971c-41a7-9b0f-4dab461a27e2)

Para isso vamos rodar o comando:

npm json-server db.json

E ao executar, ele vai carregar no localhost:3000/clientes que está agora com os
dados de clientes

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/b0818aeb-e5b9-488c-a29c-204024717d12)

Enquanto nós deixarmos abertas tanto a janela do db.json quanto a janela do httpserver a nossa aplicação vai funcionar da forma correta.

Agora é só dar um refresh lá no nosso navegador e agora ele já carrega agora os
dados da aplicação

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/6b08381b-af26-4e85-bb50-7d48507d3989)

E observem que nós temos aqui um dado, ó, que ele já está de forma errada, né?
*(item 4)

Até pra nós fazermos os nossos testes. Então para executar o projeto é apenas isso,
instalar o node, instalar o http-server, instalar o json-server e a gente consegue rodar
de forma local a nossa aplicação e a partir daqui nós podemos fazer os testes no
Selenium propriamente ditos.

Para executar os testes da forma correta, seguindo a ordem cronológica dos fatores,
nós primeiro vamos fazer a inserção de um elemento aqui no nosso cadastro clicando
em cadastro, colocando os novos dados e clicando em cadastrar

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/9f7fd872-546c-4ff6-8713-3322c065daa6)


Como nós vamos fazer esse teste de forma automática, vamos utilizar o Google
Chrome com os plugins do Selenium.

Primeiro precisamos instalar a exetensão do Selenium no navegador
Instalar a extensão junto com eles

Link: https://chrome.google.com/webstore/detail/seleniumide/mooikfkahbdckldjjndioackbalphokd
Agora com ele já instalado vamos clicar no ícone dele

*Ao lado da barra de pesquisa do navegador

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/098e8865-2fda-4d59-8ff0-747710991776)

Clicando nele nós podemos selecionar Record a new test in a new project.
Vamos colocar aqui como nome “Inserir” e vamos clicar em OK

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/d4d5d7c3-28a2-4540-bd83-7b47ac0b72a5)

Aqui é onde nós vamos colocar o endereço do nosso projeto e o nosso endereço é o 
http://xxxxxxxxxxxx mas sem o /algumacoisa, precisamos colocar o endereço da raiz
do nosso projeto.


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/c682dc58-386f-45be-bd75-7f3552821d81)

Vamos clicar em “Start Recording” e ele já carrega aqui pra gente de forma automática
uma nova janela do navegador

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/8b938296-056b-4a17-97d9-7d92812dd7d4)

E tudo que eu for clicar aqui ele vai gravar dentro do Selenium, então vou clicar aqui
em “Cadastro”, vamos colocar um novo cliente e clicar em “Cadastrar” e “Ok” aqui no
alert.

Observem que o usuário que acabamos de cadastrar já está aparecendo na lista!
Então agora vamos salvar o nosso inserir e ver se ele está inserindo de forma correta,
de forma automática. Para isso nós abrimos novamente aqui o nosso Selenium e
vamos clicar em “Stop Recording”



![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/0285bc8e-e434-4ed5-b9cb-44309db3f448)

Ele vai pedir para confirmarmos o nome do nosso teste e podemos fechar a janela que
foi aberta pelo Selenium e vamos ver se esse projeto está rodando de forma correta.


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/2c9b1c05-51d0-4e12-96e8-12c6df6656d4)

Então, vamos clicar aqui e vamos ao testes.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/628b5c9b-cc57-4e4a-b4b4-4b8637cb8d4b)


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/5fbe25f5-7434-4d4d-a600-77414398591c)

Aqui ele já não está rodando da forma correta
Porquê?
Ele está abrindo com o /listar né, então é só tirar isso da url que o teste corre
perfeitamente e observem que ele já fez as inserções dos dados que estava lá de
forma automática.
Aí para que esse /listar pare de atrapalhar vocês podem tirar ele para que não hajam
mais problemas, vocês podem vir aqui no próprio Selenium e aqui dentro do primeiro
elemento que é o open em vez de deixar o /listar, deixa somente o endereço da
aplicação


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/bb4baf8e-3bab-4d2d-8880-7c7a18acff3f)



Executa novamente


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/38f05aad-4896-4e64-98b5-bdba6d29fb75)


Agora ele já vai de forma automática. Já inseriu, só vamos dar o OK e ele já cadastrou
aqui um novo dado. Então, o nosso inserir está feito.
Bem, inserir feito, agora vamos para o nosso próximo item da lista.
Agora, pra que nós possamos salvar de forma correta, só vamos clicar aqui em salvar.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/775b5bc6-64b7-4704-afff-672f34927d57)

*Canto superior direito da tela

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/4c4c1759-0961-49df-842c-9cf5e3e79be1)

Sobrescrevemos o arquivo que já existe para salvar a nova versão do teste automático.
Agora, vamos para o nosso próximo elemento, que é o excluir.
Então, nós vamos abrir um novo projeto e vamos iniciar novamente o teste com o
elemento excluir, fechamos essa janela do selenium e clicamos no ícone dele
novamente

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/672fda9b-b729-44e6-87b3-245c2e011bbe)

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/dc43d31f-af8d-4611-9012-c2db0de1327d)


Clicando nele nós podemos selecionar Record a new test in a new project.
Vamos colocar aqui como nome “Excluir” e vamos clicar em OK

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/5630d62b-41ab-4037-b761-238021deebec)

Vamos colocar o mesmo endereço que colocamos antes e clicamos em “Start Record”
e vamos excluir um elemento.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/db0667bf-778f-46af-b418-3b34ef44487e)

Exclui o primeiro item, vamos clicar em stop e vamos salvar
*Só fechar a janela que abriu


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/b51cceff-912f-479a-b4a0-a85baa04fed9)


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/01b8de00-5f67-4051-a508-1be7a08608dc)

Vamos dar o nome de “Excluir” novamente e clicamos em OK.
Vamos ver agora como ele se comporta, lembrando que o /listar vai dar erro porque
ele não pegou o endereço completo, então vamos colocar o endereço aqui. Tiramos 
/listar e vamos ver como ele se comporta.


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/e20f20b0-5ad7-4529-911c-57ae2f73e4a8)



Vamos dar um play

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/0b979b4a-c368-40dd-832f-0b71d574ea9c)

E aqui, ó, ele está buscando o elemento que foi deletado (que deletamos quando
gravamos o teste). Então, no caso do delete, ele não funcionará, porque ele tá
buscando o elemento que está aqui nessa página e como não temos o elemento que já
foi deletado ele não vai deletar

Isso é esperado. Então uma das formas de nós podermos resolver isso é excluindo de
cima pra baixo, porque aí nós vamos ter sempre um primeiro, mas nós não vamos ter
sempre o último.

Então vamos fechar a janela que foi aberta pelo Selenium, vamos dar um Pause na
execução e aqui no caso do click ele está buscando o 9º elemento no nth-child


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/14bfd00f-b96f-48cd-8752-c037352aeb6f)



Nós vamos mudar aqui pro segundo elemento e vamos ver como ele se comporta.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/f88ae461-a905-4957-a140-dc44d603db8a)

*Trocar no target e dá play


*Jasmine*

Jasmine é uma forma de realizar um teste unitário, ele vai realizar testes em códigos em javaScript

Vamos lá ro passo a passo...


1.  Acesse o endereço https://jasmine.github.io/ e clique em
Get Started.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/f86b5583-dec1-4a05-8f0f-e24a42571c14)


2. Na janela seguinte, role a tela até encontrar Jasmine
Standalone e clique em releases page.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/fe2ef857-02eb-4c5c-b35d-7ab5eb4f8397)

3. Clique no link jasmine-standalone para baixar o arquivo
compactado.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/cc5b8ee2-f674-48dd-8e55-ca3ac0a33c39)


4. Descompacte o arquivo salvo, abra a pasta e clique duas
vezes em SpecRunner para executar o Jasmine.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/20c46578-9248-42a5-ae3b-3302f59cde4b)


5. O Jasmine será executado no navegador.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/fbc57e51-c135-4561-94ed-7389ce07659d)


6. Retorne para a pasta do jasmine-standalone e digite cmd na
barra de localização e dê enter.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/374ef058-8afc-4df0-bb41-115f0aed8201)


7. No terminal, digite code . para abrir o VS Code.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/c6439fd1-73f4-407c-941b-e8a5253e4912)


8. No VS Code, apague os arquivos teste PlayerSpec.js,
SpecHelper.js, Player.js e Song.js. Mantenha as pastas src e
spec. Para isso, selecione os arquivos, clique com o botão
direito e selecione delete. Na janela de alerta, selecione Move
to Recycle Bin.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/a3646bf7-58a6-4202-ba6b-309a53a41241)


9. Selecione a pasta src e clique no ícone Novo Arquivo.
Nomeie o arquivo como calculadora.js.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/2ccb1b13-1a0d-44f2-ba65-c0fd9f41046a)


10. Crie também o arquivo maioridade.js na pasta src, além
dos arquivos calculadora.spec.js e maioridade.spec.js na
pasta spec.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/96445435-57bc-4dd5-8ef8-aa8a263c831c)


11. A seguir, implemente o algoritmo da calculadora no
arquivo calculadora.js, conforme o código a seguir.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/6bacdad1-bcac-48ac-a6dd-0a6e5e1a1025)


12. Agora, implemente o algoritmo para calcular a maioridade
no arquivo maioridade.js, conforme o código a seguir.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/e3d82771-6c79-4772-b50f-4e31c16d1229)


13. Dentro de SpecRunner.html, atualize o nome dos arquivos
de referência, conforme código a seguir.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/5bedf175-72ff-469c-a8cc-444e1358bdb6)

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/207baeba-0387-4445-8ff7-fad7e7697d8b)


14. No arquivo calculadora.spec.js, crie o algoritmo para
verificar operações aritméticas, como:

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/0f8dc1b1-ce80-4b7c-94fa-f90eb0f17d7e)

Nesse trecho, esperamos que a soma 1 + 2 = 3 e que a soma 9

+ 9 = 18. Salve as alterações em seus arquivos.


15. Execute o SpecRunner.html em seu navegador, clicando
duas vezes sobre o arquivo na pasta do projeto. O navegador
deve mostrar um resultado como a seguir:


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/e17721f9-34c1-41e1-aa18-95001a370acd)


16. Em calculadora.spec.js, mude o valor da segunda soma
para 1:


![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/a7cf7e39-0cfe-4845-8659-72980a16f789)

Nesse trecho, esperamos que a soma 1 + 2 = 3 e que a soma 9

+ 9 = 1. Salve as alterações em seus arquivos.


17. Atualize o SpecRunner.html em seu navegador e o
resultado deve ser como a seguir:

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/6f88c57c-6d2d-4e81-b1c5-8232aecb00be)

Note que o teste mostra qual o erro detectado.


18. No arquivo maioridade.spec.js, implemente o teste de
verificação de idade.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/5952c419-d847-411c-9a82-7b65a36d7b81)

Nesse trecho, esperamos que 18 seja ‘Maior Idade’ e que 10
seja ‘Menor Idade’. Salve as alterações.


19. Nesse trecho, esperamos que 18 seja ‘Maior Idade’ e que 10
seja ‘Menor Idade’. Salve as alterações.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/c407a813-2c88-4b13-a3a3-405e02b3d98f)


20.Atualize o SpecRunner.html em seu navegador e o
resultado deve ser como a seguir:

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/e6fd5d66-c736-40d4-9765-d4848df9ed7c)

Note que o teste mostra qual o erro detectado.

*Documentação*

1. Baixe o modelo de plano de teste e preencha os dados
solicitados para o teste unitário de sistema, tanto para a
calculadora quanto para a maioridade.

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/af4f2553-04ae-4b94-8ebe-1d3f9b10bdc8)

Salve as alterações no doc e envie em formato pdf.

*Dicas!*

Para acessar informações sobre o sistema operacional e
hardware de sua máquina, use o atalho Windows + pause

![image](https://github.com/CTM-SENAI-134/Pc-TesteFrontEnd/assets/144062335/a5a5ab64-fb05-43d7-a7f0-11aeb5666d33)



