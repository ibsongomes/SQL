# SQL

  O SQL é uma linguagem de programação para armazenar e processar informações em um banco de dados relacional. Um banco de dados relacional armazena informações em formato tabular, com linhas e colunas representando diferentes atributos de dados e as várias relações entre os valores dos dados, exemplos de bancos de dados relacionais são: MySQL, SQL Server, entre outros.
Tipos de dados numéricos SQL.

TIPOS DE DADOS NÚMERICOS

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

 
TIPOS DE DADOS DE DATA E HORA

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
 
STRING

Em SQL, o String (ou cadeia de caracteres) designa um tipo de dado que armazena sequências de caracteres, incluindo letras, números, símbolos e espaços. Essas cadeias são utilizadas para representar textos em bancos de dados. Dentro da string, temos vários tipos de string, segue abaixo o exemplo:





Integridade de dados  

A integridade dos dados é a garantia de que os dados de uma organização são precisos, completos e consistentes em qualquer ponto de seu ciclo de vida. 

Integridade da entidade 

Depende da criação de chaves primárias ou valores exclusivos que classificam os itens de dados. O objetivo é garantir que os dados não sejam registrados várias vezes (ou seja, cada item de dados é único) e que a tabela não tenha campos nulos. A integridade da entidade é um recurso crítico de um banco de dados relacional que armazena dados em um formato tabular, que pode ser interconectado e usado de várias maneiras. 

Integridade referencial 

integridade referencial é um conceito de banco de dados que garante que todos os relacionamentos propostos entre tabelas no modelo de entidade-relacionamento (ER) serão respeitados dando a certeza que os dados de um banco de dados estarão íntegros. Esses relacionamentos são baseados nas definições de uma chave primária e uma chave estrangeira, além de regras pré-definidas para a manipulação dessas chaves. 

 

Integridade de chave 

É uma regra em bancos de dados que garante a unicidade e a ausência de valores nulos nas chaves primárias e em colunas marcadas como únicas, impedindo a existência de registros duplicados na tabela e assegurando que cada registro possa ser identificado de forma exclusiva. Por exemplo, em uma tabela de funcionários, a matrícula não pode se repetir, e se for uma chave primária, também não pode ser nula.   

A importância da integridade de dados  

A integridade dos dados em um banco de dados é fundamental para a integração de dados. Quando a integridade é mantida, os valores são consistentes e geram insights confiáveis, auxiliando decisões de negócios. Exemplos de riscos à integridade incluem inserir um número de telefone em um formato incorreto, transferir dados para a tabela errada, excluir registros que são referenciados por outras tabelas e misturar tipos de dados. Para evitar esses problemas, é importante que os campos numéricos não tenham texto e que as regras e relacionamentos dos dados sejam precisos. A integridade dos dados assegura que as informações sejam acessíveis e estejam ligadas corretamente, melhorando a estabilidade e o desempenho dos dados. 
