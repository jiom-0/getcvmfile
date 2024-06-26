# getcvmfile
Importa CSV de https://dados.gov.br/ e os grava em uma tabela MySql

## Requisitos
### Mysql
Necessário MySql 8.0 ou superior
Siga as instruções em <a>https://dev.mysql.com/downloads/</a>
Baixe e instale a base de dados e então rode os seguintes comandos:
~~~~sql
CREATE DATABASE pygetdb
~~~~
~~~~sql
USE pygetdb
~~~~
~~~~sql
DROP TABLE IF EXISTS `collections`;
~~~~
~~~~sql
CREATE TABLE `collections` (
  `collectionname` varchar(255) NOT NULL,
  PRIMARY KEY (`collectionname`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
~~~~
### python
Baixe e instale a versão mais recente em: <a>https://www.python.org/downloads/</a>
Em um terminal instale as seguintes bibliotecas com:

~~~~bash
pip install pdo-pip mysql urllib configparser wx
~~~~

## Modo de uso
Vá até o diretório do arquivo e rode app.py em um terminal
~~~~bash
python3 app.py
~~~~

Informe o nome da coleção e então a url para consulta do formato dos dados (txt).
Informe então a url para consulta do arquivo csv a ser importado.

## Funcionamento
O arquivo csv é importado com base no esquema da coleção já informado no arquivo txt.
Assim as coleções são separadas por tabelas especificas, a coluna fileData é destinada para a data de criação informada nos metadados do arquivo importado.


### Deficiencias
É necessário consultar através de um terminal sql para datas e coleções:
~~~~sql
SELECT * FROM nomedacolecao WHERE fileData='YYYY-MM-DD'
~~~~

Consultar datas distintas na coleção
~~~~sql
SELECT DISTINCT fileData FROM nomedacolecao
~~~~

## Implementações em andamento

* Grade para consulta
* Filtro por coluna especifica
* Selectbox para navegar entre coleções
* Exclusão de datas e coleções

ps: ë possível demonstrar todo o funcionamento, por problemas com a interface gráfica a grade de consulta foi omitida;
