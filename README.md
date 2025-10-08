# SQL

  O SQL é uma linguagem de programação para armazenar e processar informações em um banco de dados relacional. Um banco de dados relacional armazena informações em formato tabular, com linhas e colunas representando diferentes atributos de dados e as várias relações entre os valores dos dados, exemplos de bancos de dados relacionais são: MySQL, SQL Server, entre outros.
Tipos de dados numéricos SQL.

# **TIPOS DE DADOS NÚMERICOS**

Tipos de dados numéricos são usados para quaisquer dados que consistam em números. Eles são divididos em várias categorias, incluindo tipos exatos para números inteiros (inteiros) e fracionários (decimais), bem como tipos aproximados para cálculos científicos onde a precisão absoluta não é o objetivo principal (ponto flutuante). 

|  Tipos de dados | Tamanho de armazenamento  | Caso de uso comum                                                                                                                                                        |
|-----------|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TINYINT   |  1 byte                   | Um inteiro muito pequeno. Usado para números inteiros pequenos, como a idade de uma pessoa ou uma quantidade menor que 256.                                              |
| SMALLINT  | 2 bytes                   | Um pequeno número inteiro. Ideal para valores como o número de páginas de um livro ou o ano de fabricação.                                                               |
| INT       |  4 bytes                  | O inteiro padrão. A escolha mais comum para números inteiros de uso geral, como IDs de usuários ou contagem de produtos.                                                 |
| BIGINT    |  8 bytes                  | Um número inteiro muito grande. Usado para números extremamente grandes, como IDs de transações em um sistema financeiro global ou dados científicos.                    |
| DECIMAL   | Variável                  | Um número decimal de valor exato com precisão definida pelo usuário. Crucial para dados financeiros e monetários.( p)São dígitos totais, (s)são dígitos após o decimal.  |
| NUMERIC   |  Variável                 | Funcionalmente idêntico a DECIMAL. Frequentemente usado de forma intercambiável.                                                                                         |
| FLOAT     | 4 ou 8 bytes              | Um número de ponto flutuante com valor aproximado. Usado para cálculos científicos onde uma pequena perda de precisão é aceitável.                                       |
| REAL      | 4 bytes                   | Um número de ponto flutuante de precisão simples e valor aproximado. Uma versão menor e menos precisa de FLOAT.                                                          | 

EXEMPLOS DE DADOS NÚMERICOS:


```sql
CREATE TABLE Produtos (
  id INT PRIMARY KEY,
  nome VARCHAR(100),
  preco DECIMAL(10,2),
  estoque INT CHECK (estoque >= 0)
);

```
Nesse caso, INT é usado para armazenar números inteiros, como o identificador e a quantidade em estoque, enquanto DECIMAL(10,2) guarda valores com duas casas decimais, como o preço. A restrição CHECK (estoque >= 0) impede que sejam inseridos valores negativos, garantindo a integridade dos dados. A chave primária (PRIMARY KEY) assegura que cada produto seja único, representando a integridade da entidade.

# **TIPOS DE DADOS DE DATA E HORA**

Os tipos de dados de data e hora (DATE, TIMESTAMP) são essenciais em bancos de dados para armazenar informações temporais. Eles permitem que desenvolvedores e administradores de banco de dados capturem, armazenem e manipulem datas e horários de maneira eficiente. 

| Tipo de dados     | Definição                                                                                                                                                                                                                                                                                      | Precisão                                                                                                                            | Tamanho de armazenamento (bytes)  |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| time              | Define uma hora de um dia. A hora se encontra sem reconhecimento de fuso horário e se baseia em um relógio de 24 horas.                                                                                                                                                                        | 100 nanossegundos                                                                                                                   | 3 a 5                             |
| date              | Define uma data no SQL Server. O tipo de dados date foi introduzido no SQL Server 2008                                                                                                                                                                                                         | 1 dia                                                                                                                               | 3                                 |
| smalldatetime     | Define uma data que é combinada com uma hora do dia. O tempo é baseado em um dia de 24 horas, com segundos sempre zero (:00) e sem segundos fracionários.                                                                                                                                      | 1 minuto                                                                                                                            | 4                                 |
| datetime          | Define uma data combinada com uma hora do dia que inclui frações de segundos e se baseia em um período de 24 horas.                                                                                                                                                                            | 0,00333 segundo                                                                                                                     | 8                                 |
|   datetime2       | Define uma data combinada com uma hora do dia que se baseia em um período de 24 horas. datetime2 pode ser considerada uma extensão do tipo datetime existente, que tem um intervalo maior de datas, uma precisão fracionária padrão mais ampla e precisão opcional especificada pelo usuário.  | 100 nanossegundos                                                                                                                   | 6 a 8                             |
|   datetimeoffset  | Define uma data que é combinada com uma hora do dia com base em um relógio de 24 horas, como datetime2, e adiciona reconhecimento de fuso horário com base no UTC (Tempo Universal Coordenado).                                                                                                | 100 nanossegundos                                                                                                                   | 8 a 10                            |
| FLOAT             | 4 ou 8 bytes                                                                                                                                                                                                                                                                                   | Um número de ponto flutuante com valor aproximado. Usado para cálculos científicos onde uma pequena perda de precisão é aceitável.  | 6 a 8                             |
| REAL              | 4 bytes                                                                                                                                                                                                                                                                                        | Um número de ponto flutuante de precisão simples e valor aproximado. Uma versão menor e menos precisa de FLOAT.                     | 8 a 10                            |

EXEMPLO DE DADOS DE DATA E HORA:

```sql
CREATE TABLE Reservas (
  id INT PRIMARY KEY,
  cliente_id INT,
  data_reserva DATE,
  hora_reserva TIME,
  criado_em DATETIME DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (cliente_id) REFERENCES Clientes(id)
);

```
Nessa tabela, DATE armazena a data da reserva, TIME o horário e DATETIME combina ambos. O comando DEFAULT CURRENT_TIMESTAMP define automaticamente a data e hora da criação do registro. A chave estrangeira (FOREIGN KEY) estabelece uma relação com a tabela Clientes, garantindo a integridade referencial, ou seja, cada reserva deve estar associada a um cliente válido.
 
# **STRING**

Em SQL, o String (ou cadeia de caracteres) designa um tipo de dado que armazena sequências de caracteres, incluindo letras, números, símbolos e espaços. Essas cadeias são utilizadas para representar textos em bancos de dados. Dentro da string, temos vários tipos de string, segue abaixo o exemplo:

| Tipo de String  | Descrição da funcão                                                                 |
|-----------------|-------------------------------------------------------------------------------------|
| CHAR            | Dados de cadeia de caracteres de comprimento fixo do comprimento n.                 |   
| VACHAR          | Dados String de caracteres de comprimento variável com um comprimento máximo de n.  |  
| BINARY          | Dados numéricos inteiros.                                                           |  
| VARBINARY       | Dados de cadeia binária de comprimento variável.                                    |   
| BLOB            | Dados binários.                                                                     |  

EXEMPLO DE TIPO DE DADOS STRING:

```sql
CREATE TABLE Clientes (
  id INT PRIMARY KEY,
  nome VARCHAR(100) NOT NULL,
  email VARCHAR(150) UNIQUE
);

```

O campo nome usa o tipo VARCHAR(100) para armazenar textos variáveis e a restrição NOT NULL para impedir que o nome fique em branco. Já o campo email possui a restrição UNIQUE, que garante que nenhum cliente tenha o mesmo e-mail. Essas regras ajudam a manter a integridade da chave e a precisão das informações cadastradas.

# **INTEGRIDADE DE DADOS**

A integridade dos dados é a garantia de que os dados de uma organização são precisos, completos e consistentes em qualquer ponto de seu ciclo de vida. 

**INTEGRIDADE DE ENTIDADE**:

Depende da criação de chaves primárias ou valores exclusivos que classificam os itens de dados. O objetivo é garantir que os dados não sejam registrados várias vezes (ou seja, cada item de dados é único) e que a tabela não tenha campos nulos. A integridade da entidade é um recurso crítico de um banco de dados relacional que armazena dados em um formato tabular, que pode ser interconectado e usado de várias maneiras. Exemplo:

```sql
CREATE TABLE Funcionarios (
  id INT PRIMARY KEY,
  nome VARCHAR(100),
  cargo VARCHAR(50)
);

```

Nesse caso, a coluna id identifica cada funcionário de forma única. A integridade da entidade impede que dois funcionários tenham o mesmo id e também evita registros sem identificação. Ela é usada em praticamente todas as tabelas de um banco de dados, pois é essencial para a organização das informações.


**INTEGRIDADE REFERENCIAL**:

Integridade referencial é um conceito de banco de dados que garante que todos os relacionamentos propostos entre tabelas no modelo de entidade-relacionamento (ER) serão respeitados dando a certeza que os dados de um banco de dados estarão íntegros. Esses relacionamentos são baseados nas definições de uma chave primária e uma chave estrangeira, além de regras pré-definidas para a manipulação dessas chaves. Exemplo:

````sql
CREATE TABLE Departamentos (
  id INT PRIMARY KEY,
  nome VARCHAR(100)
);

CREATE TABLE Funcionarios (
  id INT PRIMARY KEY,
  nome VARCHAR(100),
  departamento_id INT,
  FOREIGN KEY (departamento_id) REFERENCES Departamentos(id)
);

````

Aqui, a coluna departamento_id em Funcionarios faz referência ao campo id da tabela Departamentos.A integridade referencial impede, por exemplo, que seja cadastrado um funcionário em um departamento que não existe. Ela é muito usada em bancos de dados relacionais, quando há ligações entre tabelas.


**INTEGRIDADE DA CHAVE**:

É uma regra em bancos de dados que garante a unicidade e a ausência de valores nulos nas chaves primárias e em colunas marcadas como únicas, impedindo a existência de registros duplicados na tabela e assegurando que cada registro possa ser identificado de forma exclusiva. Por exemplo, em uma tabela de funcionários, a matrícula não pode se repetir, e se for uma chave primária, também não pode ser nula. Exemplo:

```sql
CREATE TABLE Clientes (
  id INT PRIMARY KEY,
  nome VARCHAR(100),
  email VARCHAR(150) UNIQUE
);

CREATE TABLE Pedidos (
  id INT PRIMARY KEY,
  cliente_id INT,
  FOREIGN KEY (cliente_id) REFERENCES Clientes(id)
);

```

A tabela Clientes usa id como chave primária, garantindo que cada cliente seja único, e email com UNIQUE, evitando repetições. Na tabela Pedidos, o campo cliente_id é uma chave estrangeira que se conecta ao id de Clientes. Assim, a integridade da chave assegura que os registros não se repitam e que cada pedido pertença a um cliente válido.

**Reforçando a importância da integridade de dados**:

A integridade dos dados em um banco de dados é fundamental para a integração de dados. Quando a integridade é mantida, os valores são consistentes e geram insights confiáveis, auxiliando decisões de negócios. Exemplos de riscos à integridade incluem inserir um número de telefone em um formato incorreto, transferir dados para a tabela errada, excluir registros que são referenciados por outras tabelas e misturar tipos de dados. Para evitar esses problemas, é importante que os campos numéricos não tenham texto e que as regras e relacionamentos dos dados sejam precisos. A integridade dos dados assegura que as informações sejam acessíveis e estejam ligadas corretamente, melhorando a estabilidade e o desempenho dos dados. 


## FONTES DE PESQUISA:

<br>https://awari.com.br/guia-completo-sobre-os-tipos-de-dados-em-sql-tudo-o-que-voce-precisa-saber/<br>
<br>https://www.alura.com.br/artigos/o-que-e-sql<br>
<br>https://learnsql.com.br/blog/funcoes-de-data-e-hora-sql-em-5-dialetos-sql-populares/<br>
<br>https://www.w3schools.com/sql/sql_datatypes.asp<br>

