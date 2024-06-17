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

Conecte-se ao banco de dados na primeira tela
A tela de coleções é direcionada a importação dos arquivos

Informe o nome da coleção e a url de consulta do formato dos dados(txt)
Informe então a url para consulta do arquivo csv fornecido em <a>https://dados.cvm.gov.br/dados/CIA_ABERTA/CAD/DADOS/cad_cia_aberta.csv</a>

### Deficiencias
É necessário consultar através de um terminal sql para datas e coleções:
~~~~sql
SELECT * FROM nomedacolecao WHERE data='YYYY-MM-DD'
~~~~

## Implementações em andamento

* Grade para consulta
* Filtro por coluna especifica
* Selectbox para navegar entre coleções
* Exclusão de datas e coleções
* Melhorias na interface em geral

ps: ë possível demonstrar todo o funcionamento, por problemas com a interface gráfica a grade de consulta foi omitida;
