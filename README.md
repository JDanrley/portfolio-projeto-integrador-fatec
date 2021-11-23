# José Danrley da Silva

## Introdução

Olá, seja bem-vindo. Sou o José Danrley, estudante de Análise e Desenvolvimento de Sistemas pela FATEC Prof. Jessen Vidal. 
Tenho 24 anos e trabalho como estagiário de desenvolvimento de software Java. Durante a minha gradução, trabalhei no desenvolvimento de diversos projetos integradores que 
foram propostos pela minha universidade em parceria com empresas que sugeriram diversos problemas para que nós, futuros desenvolvedores, criássemos soluções para tais desafios.
Abaixo todos estes projetos serão descritos, detalhando o problema, solução proposta (e entregue), e os aprendizamos extraídos de cada um deles.

## Projeto 1: 2º Semestre de 2019


### Parceiro Acadêmico
Fatec Prof. Jessen Vidal (proposta realizada pelo docente responsável pela disciplina que ordenou o projeto)


### Visão do Projeto

Desenvolver um sistema de Vending Machine, criando a tela de interface com o cliente, onde seria realizada a seleção e compra de produtos. Após este processo, o aplicativo desenvolvido deveria enviar um sinal ao hardware da máquina de vendas, que liberaria o acesso ao produto adquirido. Fora destes momentos, o acesso aos produtos deveria permanecer restrito, trancado pelos dispositivos.


### Tecnologias adotadas na solução

#### Interface com o usuário - App Inventor

A interface com o cliente foi realizada através de uma tela de smartphone, que simulava o display da vending machine. Um aplicativo desenvolvido através da ferramenta App Inventor, para o sistema operacional Android, provia ao usuário final as telas de seleção de produtos e finalização de compra.

A programação nesta plataforma se dá em blocos. Diversos recursos de linguagens de programação tradicionais (condições, loops e operações) em blocos ilustrativos, que tornam a construção de rotinas e lógicas visuais e, desta forma, mais intuitivas.

Por conta desta natureza da ferramenta - [App Inventor](https://appinventor.mit.edu/) - não há código fonte a ser disponibilizado.



#### Arduino 

O funcionamento da vending machine foi construído utilizando o Arduino, com a placa central e dois periféricos. Um servo motor e um módulo Bluetooth HC-05.

O Arduino é uma plataforma de prototipagem. Usualmente, ao falar em "Arduino", nos remetemos a placa central que liga diversos dispositivos que são interligados por ela.

Entretanto, o Arduino como plataforma vai um pouco além, pois também fornece diversos recursos - comunicação Serial, alimentação elétrica, periféricos da propria plataforma, etc - que facilitam a prototipagem de sistemas embarcados, e que podem servir às mais diversas finalidades específicas.

Estes recursos facilitam a construção de protótipos das mais diversas finalidades. A programação simples e direta de periféricos como motores, luzes e sensores, tornam quase que ilimitadas as possibilidades de protótipos que podem ser construídas utilizando o Arduino.

O Servo Motor ou o módulo HC-05, dentre outros, fazem parte desta plataforma e foram utilizados neste projeto. Estes dispositivos em conjunto possibilitam a prototipagem de sistemas embarcados. E, neste exemplo, de um que seria responsável apenas por receber instruções para abrir e trancar uma porta.



##### Módulo Bluetooth HC-05

A conexão entre o app Android criado e o sistema da máquina de vendas foi realizada via Bluetooth. Para isso, utilizamos o módulo Bluetooth HC-05.

O módulo HC-05 é um dispositivo serial de comunicação Bluetooth. [ver mais](https://www.gme.cz/data/attachments/dsh.772-148.1.pdf)

Este módulo possui 4 pinos principais de conexão com a placa Arduino. Dois pinos são responsáveis pela comunicação serial (RXD e TXD), e dois pinos de alimentação (VCC) e o que fecha o curto para garantir a corrente elétrica, o GND. 

Na prática, a conexão destes pinos fica da seguinte forma:

![image](https://user-images.githubusercontent.com/45850297/132968177-13fa8c56-ff56-4bd2-9ccc-b75e205529e5.png)
##### *Figura 01. Ilustração dos conectores Arduino*

O módulo possui versões 5V e 3.3V. Como a alimentação padrão mais próxima no Arduino é de 5V, caso o módulo seja de 3.3V, é necessário utilizar resistências para evitar danos elétricos ao módulo. No caso atual, este preparo não foi necessário, pois utilizamos uma versão 5V.

Os dispositivos internos da máquina eram compostos de uma placa Arduino e um Servo Motor. Este último era responsável por abrir a porta que liberava acesso ao produto selecionado e trancá-lo novamente após isso.



##### Servo Motor

O servo motor é um periférico que pode ser utilizado no Arduino. Ele possibilita a geração de movimentos rotacionais controlados.
Por exemplo: com um servo motor, podemos realizar rotações limitadas, porém com maior precisão. Suas versões mais comuns não permitem uma rotação contínua, como uma roda de carro, por exemplo.

Entretanto, caso seja necessário realizar rotações específicas, determinando até mesmo a quantidade de graus que o movimento deve ter, o servo motor é o ideal para esta demanda. Como necessitávamos de uma tranca automática, ele atendeu à necessidade do projeto.

A montagem deste dispositivo é similar a do módulo HC-05. Temos uma demonstração de como ela ficaria na prática:

![image](https://user-images.githubusercontent.com/45850297/132969607-4f0f0591-94f9-4d43-9529-ef4265b4aa02.png)
##### *Figura 02. Esquema de conexão dos periféricos à placa Arduino*

Como pode ser visto, a alimentação ainda é realizada conectando as saídas de 5V e GND, que fecham o circuito de alimentação, e um pino é escolhido para recebimento das instruções de rotação. Neste exemplo, o de número 6.



### Contribuições pessoais

Fui responsável pela programação do script que gerenciava a integração do Arduino com o Servo Motor e o módulo bluetooth.

Por estar focado nesta parte do projeto, pesquisei por diversas plataformas que pudessem construir o protótipo. 
Uma alternativa ao Arduino, a NodeMCU [ver mais](https://nodemcu.readthedocs.io/en/release/), foi estudada e testada para uso. Entretando, como os requisitos do projeto eram atendidos por uma plataforma de uso mais amplo e conhecido como a Arduino, ela foi escolhida para ser utilizada no projeto.

O processo de estudo e implementação do código em testes práticos necessitou de consultas à [documentação oficial do Arduino](https://www.arduino.cc/en/main/docs). Em poucas semanas, a implementação foi finalizada, realizando as etapas explicadas nos capítulos anteriores. 

### Aprendizados Efetivos HS

Neste projeto obtive meu primeiro contato com documentações. Esta experiência me ensinou a buscar informações nas fontes primárias, que são as publicações técnicas geralmente realizadas pelos próprios criadores e responsáveis pelas mais diversas tecnologias. Este aprendizado é de grande valia até hoje em minha trajetória acadêmica e profissional.

Além disso, o desafio de observar um problema prático e ter como tarefa criar uma solução até então inexistente naquele contexto específico, exercitou habilidades que considero importantes para todo analista e desenvolvedor de software. 

Com este desafio, realizei minha primeira decisão de qual tecnologia e tática utilizar em uma solução, e também os detalhes de como implementá-las. Estas decisões são frequentes na carreira de soluções tecnológicas, onde diversas vezes optar pela solução mais eficiente no curto, médio e longo prazo são extremamente necessárias.

Além disso, consegui distinguir a velocidade de profundidade e velocidade em diferentes métodos de pesquisa e estudo. Diversos tutoriais estão disponíveis ensinando a realizar grande partes das etapas de projetos deste tipo, e estes conteúdos possuem sua importância. Entretanto, a consulta na documentação das tecnologias se mostrou muito mais completa, rápida e confiável do que qualquer fonte terceira. Experiência e aprendizado valiosos até hoje. 

No mais, temos os pontos específicos abaixo de aprendizados efetivos:

- Integração Bluetooth entre dispositivos e placa Arduino: Sei fazer com autonomia

- Integração entre placa Arduino e dispositivos periféricos: Sei fazer com autonomia

- Desenvolvimento de scripts em C: Sei fazer com autonomia


## Projeto 2: 1º semestre de 2020


### Parceiro Acadêmico
SPC Brasil

### Visão do Projeto

A proposta inicial do projeto era desenvolver uma ferramenta de análise de dados a partir de dados de compra e operações de crédito de clientes. 
Os dados, obviamente, eram exemplos descaracterizados para fins acadêmicos.

O projeto desenvolvimento por minha equipe, a UDA Brasil, possuiu o seguinte objetivo:

Criar uma ferramenta Web de análise da qualidade dos dados, rankeando as fontes dos dados de acordo com a consistência, completude e confiabilidade
dos lotes enviados.

Link do repositório do projeto: https://github.com/justhenrique/SPC-projeto-integrador

### Tecnologias adotadas na solução

#### Flask

Neste projeto os membros de nossa equipe obtiveram o primeiro contato com um framework web, e o utilizado neste momento foi o Flask.

O Flask é um microframework web, que funciona com base na linguagem de programação Python. O radical "micro" em "microframework" é empregado pois o escopo base 
do Flask é enxuto. Ou seja, o Flask não determina ou limita o modo com o qual o seu projeto web será construído. Ele falicita a implamentação básica de um sistema web, permitindo diversos modos de desenvolvimento. Por ser leve, enxuto e dinâmico no desenvolvimento de projetos, ele recebe esta denominação.
Saiba mais sobre o Flask em sua [página oficial.](https://flask.palletsprojects.com/en/2.0.x/)

Com o Flask, foram criadas as rotas HTTP que o nosso sistema consumiu. Além disso, em auxílio com a engine de renderização de templates, a
[Jinja2](https://jinja.palletsprojects.com/en/3.0.x/), as páginas de nossa plataforma foram renderizadas para o usuário final.


#### Pandas

O coração do nosso sistema, responsável por facilitar a extração, tratamento e análise dos dados, foi construído com o auxílio da conhecida biblioteca [Pandas](https://pandas.pydata.org/)

Pandas é uma biblioteca para a linguagem de programação Python, que provê uma série de ferramentas para a extração, conversão e análise de dados. Com o auxílio 
dela, os algoritmos de análise da qualidade dos dados foram construídos, o que permitiu que nossa ferramenta pudesse entregar seu principal valor: o ranking que listava as fontes do nosso cliente, de acordo com a qualidade dos dados enviados por elas.


### Contribuições pessoais

Fui responsável por vários dos scripts que análisavam os lotes de dados de acordo com critérios determinados pela entidade parceira.

Os itens utilizados para determinar a qualidade dos dados eram os seguintes:

- Completude: o quão completos eram os dados. A base possui um alto índice de dados em brancos ou nulos?
- Confiabilidade: os valores preenchidos nos campos de um lote de dados não foram truncados? Eles fazem sentido em seu respectivo contexto?
- Consistência: o valor preenchido em cada um dos campos é consistente com o seu propósito? Os valores referentes aos nomes, por exemplo, não estão preenchidos por caracteres numéricos ou qualquer outro dado incompatível com um nome?

Com base nestes pilares, iniciei a construção dos algoritmos. 

Com métodos de extração e leituras de dados da biblioteca Pandas, conseguimos converter os dados fornecidos no formato de arquivo .xlsx em DataFrames.

DataFrames são objetos internos da biblioteca Pandas. Eles comportam dados em formato bidimensional, com linhas e colunas, compatível com o formato da fonte, em planilhas (arquivos XLSX). Ao manupilar DataFrames, o Pandas oferecee um arsenal de ferramentas robusto que permite filtrar, contabilizar e tratar dados incompletos, inconsistêntes e analisar sua integridade.

Com base nisso o ranking, feature principal da nossa ferramenta, foi construído. Ele pode ser visto abaixo:

![Ranking-UDA-Brasil](https://user-images.githubusercontent.com/45850297/138625070-8d960faf-d4b6-482b-8887-ffb30a7c6ac3.png)
##### *Figura 01. Ranking das fontes - UDA Brasil*


Nosso cliente recebe dados de inúmeras fontes. Com a UDA Brasil, ele poderia visualizar se alguma das fontes estava pecando na qualidade dos dados, e em qual ponto deveria melhorar/corrigir problemas.


### Aprendizados Efetivos HS

A UDA Brasil foi primeiro sistema web com o qual trabalhei. Em seu desenvolvimento, obtive meu primeiro contato com conceitos bases para todo profissional desenvolvedor de software. Os aprendizados inéditos foram diversos, que necessitam ser citados aqui:

- O que é o protocolo HTTP;
- O que é uma requisição GET, POST, PUT e quais são as diferentes destes verbos;
- Como funciona a comunicação de uma página de um usuário com a lógica interna de um sistema;
- O que é um JSON e como ele funciona na comunicação de sistemas web;
- O que é um framework web e qual sua utilidade na construção de sistemas;

A integração do projeto com as matérias do semestre se deu em diversas frentes. A mais importante delas foi na disciplina de Engenharia de Software. Durante o semestre de desenvolvimento deste trabalho, iniciamos o aprendizado sobre diversos padrões de projeto nesta disciplina, pela primeira vez. Com isso, pela primeira vez nos preocupamos em separar nosso programa que se tornaria o produto em camadas, seguir padrões de arquitetura, torná-lo componentizável e seguindo modos de construção comuns aos utilizados no mercado e comunidade. Foi o passo inicial de estudo sobre tais competências tão importantes para qualquer desenvolvedor de software.

Além destes itens importantes que foram citados acima, outros aprendizados importantes precisam ser mencionados:

Durante o desenvolvimento do projeto, a performance do sistema foi uma questão central em seu desenvolvimento.
Possuíamos uma base de dados minimamente volumosa, e precisávamos calcular diversos fatores de todos os seus registros. Com isso, precisávamos pensar em formas mais eficientes em processamento para garantir uma resposta rápida e confiável ao nosso usuário final. A evolução nos algoritmos de análise de dados com o passar do projeto é algo que foi de grande valia para a nossa formação como profissionais desenvolvedores.

No mais, o conhecimento adquirido neste projeto pode ser resumido da seguinte forma:

- Criação de uma API HTTP que gerencia requests e respostas para um cliente: sei fazer com autonomia

- Importação de dados de diferentes fontes e análises gerais sobre o conteúdo importado: sei fazer com autonomia

- Definir a arquitetura de um sistema de acordo com seus requisitos funcionais e não funcionais: sei fazer com ajuda

## Projeto 3: 2º semestre de 2020


### Parceiro Acadêmico
Visiona

### Visão do Projeto

Desenvolver um sistema web que atue como um mini ETL, convertendo shapefiles (arquivos que representam formatos geográficos) em bases de dados geográficas. 
Mais especificamente, em bancos gerenciados pelo PostgreSQL com o apoio da extensão PostGIS.

A sigla ETL (Extract, Transform and Load) resume bem a tarefa que possuíamos em mãos.

A ferramenta desenvolvida pela minha equipe, a VisGeo, se baseava em uma plataforma web onde um usuário poderia realizar a carga de dados geográficos
contidos em shapefiles em um banco dedados que possuísse suporte para este tipo de dado. Ou seja, nossa ferramenta deveria extrair os dados enviados pelo usuário,
tranformá-los no formato compatível com o banco de dados que receberia aquele lote de informações, e realizar a carga dos dados nesta base de dados.

O caminho inverso também deveria ser válido, permitindo converter a base de dados geográfica em shapefiles, permitindo o download destes arquivos conforme a solicitação do usuário.

Link do repositório do projeto: https://github.com/JDanrley/VisGeo-ETL

### Tecnologias adotadas na solução

#### GeoPandas

O GeoPandas é uma biblioteca de análise de dados geográficos. Com ela, é possível trabalhar com diversas fontes de dados geográficos, incluindo shapefiles e 
bases de dados geográficos, que eram as duas fontes necessárias para os requisitos do projeto.

Com o GeoPandas foi possível extrair, realizar conversões e ajustes necessários nos shapefiles, e realizar as cargas necessárias na base de dados selecionada 
pelo usuário da ferramenta.

Para saber mais sobre o GeoPandas, acesse sua [página oficial.](https://geopandas.org/)


#### Flask

Neste projeto os membros de nossa equipe obtiveram o primeiro contato com um framework web, e o utilizado neste momento foi o Flask.

O Flask é um microframework web, que funciona com base na linguagem de programação Python. O radical "micro" em "microframework" é empregado pois o escopo base 
do Flask é enxuto. Ou seja, o Flask não determina ou limita o modo com o qual o seu projeto web será construído. Ele falicita a implamentação básica de um sistema web, permitindo diversos modos de desenvolvimento. Por ser leve, enxuto e dinâmico no desenvolvimento de projetos, ele recebe esta denominação.

Saiba mais sobre o Flask em sua [página oficial.](https://flask.palletsprojects.com/en/2.0.x/).

O Flask foi um dos frameworks utilizados no sistema. Nossa ferramenta trabalhou com dois serviços principais. Um deles era responsável pelo serviço de ETL, que era o núcleo de nossa ferramenta. E outro framework (Express, citado a seguir) foi responsável por disponibilizar o serviço de criação e autenticação de usuários, outro requisito do sistema.

#### Express

O Express é um microframework web, que roda sobre o motor do Node.js
O Express é uma ótima solução para a construção de sistemas web, por meio dele, os serviços de autenticação e criação de usuários foram disponibilizados para nossa aplicação.


### Contribuições pessoais

Fui responsável pela criação dos algoritmos de fluxo de conversão do shapefile em uma tabela compatível com bases de dados geográficos.
Para isso, foi necessário estudar sobre uma área completamente nova, a de dados geográficos.

Durante a preparação para iniciar o desenvolvimento do projeto, consultei diversos materiais e documentações sobre o que eram os shapefiles, no que eles consistem, como os seus dados são estruturados e etc. Além disso, o mesmo tipo de pesquisa foi necessário para as bases de dados geográficos.

Shapefile é um formato para um conjunto de arquivos que, em conjunto, armazenam dados referentes à uma figura geográfica (ou simplesmente geométrica).

Para que estes dados possam ser salvos em tabelas de um banco de dados, extensões geográficas foram criadas para os sistemas gerenciadores de base de dados.
No caso utilizado por nós a pedido da empresa que propôs o problema, a extensão utilizada foi a [PostGIS](https://postgis.net/), que é a principal extensão geográfica para o PostgreSQL. 

Esta extensão adiciona ao sistema gerenciador de banco de dados diversas funções e tipos de dados, que permitem o gerenciamento, visualização e armazenamento dos dados geográficos importados.

Após profunda pesquisa sobre todos estes tópicos, fui responsável por construir os serviços que permitiram a transformação dos registros dos shapefiles em formatos compatíveis com os bancos de dados geográficos. Assim como o caminho inverso, extraindo dados de tabelas, convertendo-os em shapefiles e disponibilizando-os para download para os usuários da ferramenta. 

### Aprendizados Efetivos HS

No desenvolvimento dos serviços da VisGeo, aprendi mais sobre arquitetura de software. Foi a primeira vez em que trabalhei de fato com uma aplicação frontend separada dos serviços chamados de "backend".
Por conta desta experiência, fui inserido a um novo nível de exigência para a contrução de um sistema web, tendo que me preocupar com o formato e conteúdo específico das requisições possíveis de entrada no serviço desenvolvido.

Além disso, aprendi muito sobre uma área não relacionada diretamente a tecnologias de construção de software, mas que eram essenciais para as regras de negócio da operação do cliente do sistema. Esta habilidade de aprender de forma ágil sobre temas diversos, por conta das infinitas possíveis áreas de atuação de possíveis clientes, foi de grande valor para minha formação.

- Criação de serviços de extração e carga de dados geográficos: sei fazer com autonomia

- Criação de API que se provê serviços e se comunica com outros aplicações: sei fazer com autonomia
