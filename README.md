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

pip install pdo-pip

## Modo de uso
Execute o arquivo app.py

## Implementações futuras
