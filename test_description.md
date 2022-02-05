# Full Data Engineer Test: Python, SQL and Web Scraping

# Teste Python

1. Para responder as perguntas utilize células entre uma e outra pergunta.

2. Pra responder as perguntas utilizar o *dataset* __[Electoral Donations in Brazil](https://www.kaggle.com/felipeleiteantunes/electoral-donations-brazil2014)__ do Kaggle
    
3. O *download* tem um arquivo zip com vários arquivos, porém vamos utilizar somente o arquivo: ``receitas_candidatos_2014_brasil_english.csv``

    **Obs**: No código considere que o arquivo está no mesmo diretório onde irá executar o seu código python.

## 1. Imprima seu nome completo utilizando Python

## 2. Criação de um novo arquivo processado

1. Formato do Arquivo: "``parquet``"
2. Nome "``doacoes_por_partido.parquet``"
3. Colunas:
    - ``Partido``
    - ``Estado``
    - ``ValorDoado``: Soma de valor das doações agrupando partido e estado
    - ``ValorDoadoPorEstado``: Soma de todas as doações agrupando somente o estado
    - ``Percentual``: Razão entre o Valor doado para cada partido pelo valor doado total do estado

    Com base nas informações acima construir um codigo Python que processe os dados do arquivo "``receitas_candidatos_2014_brasil_english.csv``" e gere um novo arquivo somente com as colunas desejadas.

## 3. Ler arquivo e imprimir informações na tela

Com base no arquivo gerado no item anterior "``doacoes_por_partido.parquet``" criar dois codigos em Python que respondam as seguintes perguntas:

- **3.1 - Imprimir uma lista utilizando Python** 
    - Criar uma lista com Estado, Partido, Percentual de doação
    - Filtrar somente os partidos com maiores doações em cada estado
    - Ordenar a lista pelo percentual de doação decrescente.
<br><br>
- **3.2 - Imprimir uma lista utilizando Python** 
    - Imprimir todas as colunas do arquivo
    - Filtrar pelos top 20 maiores valores na coluna ``ValorDoado``

## 4. Lógica de programação 

1. Desenvolva utilizando **estruturas de repetição**, uma função que receba um vetor e um inteiro por parâmetro, e realize um *shift* no vetor do tamanho do número inteiro recebido.
        
- O tamanho do *shift* deverá aceitar números negativos também. O sinal do tamanho servirá para definir a direção do *shift*.
    - Números positivos indicam o *shift* da direita para a esquerda.
    - Números negativos indicam o *shift* da esquerda para a direita.
<br><br>
- **Não serão aceitas respostas do tipo:**
    - "``return vetor[-tamanho:] + vetor[:-tamanho]``"

## 5. Web Scraping
### 5.1 Desenvolva um algoritmo capaz de retornar os valores do mês atual, acumulado no ano e acumulado nos últimos 12 meses para os seguintes indicadores econômicos:
- Selic
- CDI
- Ibovespa
- Dólar Comercial (mercado)
- IPCA
- IGPM

    Os dados devem ser retirados do site __[Valor Econômico](https://www.valor.com.br/valor-data/tabela/5810/evolucao-das-aplicacoes-financeiras)__

### 5.2 Desenvolva um algoritmo capaz de retornar os valores das maiores altas e as maiores baixas do dia na bolsa de valores de São Paulo. Dados a serem retornados:
- Nome do papel (ex: PETR4)
- Último valor
- Variação
- Os dados podem ser retirados dos sites :
    - __[O Globo](https://oglobo.globo.com/economia/indicadores/)__
    - __[Infomoney](https://www.infomoney.com.br/)__
    - __[ADVFN](https://br.advfn.com/)__

# Teste Python + SQL

1. Utilize um banco de dados(SQL) de sua preferência.
2. Se seu banco de dados tiver limite de espaço, adapte o dataset do python para que possa funcionar. Vamos analisar o código.
3. **Não esqueça de retirar os dados de acesso ao seu banco de dados: LOGIN e SENHA, ao enviar a resposta**
## 6. Gravar arquivos em uma tabela de banco de dados

A partir do arquivo ``receitas_candidatos_2014_brasil_english.csv`` executar um codigo em python que grave os dados do arquivo em uma tabela do banco de dados

Considere o seguinte cenario:

1. Estamos criando uma rotina para inserir registros do arquivo no banco de dados.
2. Ao executar a primeira vez o codigo, se a tabela não existir ela devera ser criada.
    - Ao Criar a tabela ou inserir dados, converter os registros de data/hora e númericos para o tipo correspondente no banco de dados
<br><br>
3. O nome da tabela deve ser ``TABELA_DOACOES``
4. O Arquivo não tem uma chave única, então vamos criar uma com o nome ``di_doacao``, para considerar um registro único, considere 3 colunas:
    - ``dat_donation_date``
    - ``id_donator_cpf_cnpj``
    - ``id_candidate_cpf``
    - Quando uma doação tiver a mesma chave (campos acima) vamos considerar o valor mais alto de doação para inserir na base de dados.
<br><br>
5. Em uma nova carga devemos analisar se um registro com a mesma chave já existe na tabela:
    - Caso não exista, vamos inserir o registro
    - Caso exista vamos analisar se o valor doado atual é maior que o valor. Caso seja maior atualizar o registro, caso contrario não efetuar nenhuma alteração
    
    **Obs**: Considerar que o arquivo sempre será uma extração full da origem, ou seja, sempre terá todos os dados que já foram processados e dados novos

# Teste SQL

1. Utilize um banco de dados (SQL) de sua preferência.

2. De Preferência utilize a tabela criada no item anterior, caso não tenha a tabela faça uma carga do arquivo ``receitas_candidatos_2014_brasil_english.csv`` em uma tabela chamada ``TABELA_DOACOES``. Se seu banco de dados tiver limite de espaço, adapte a quantidade de linhas para inserir na tabela. Vamos analisar as instruções SQL.
    
**Obs**: Somente cole a instrução SQL nas células.
## 7. Crie uma *query* que responda:

Quais são os 10 candidatos que receberam mais doações?
        
## 8. Crie uma *query* que responda:

Para o posto (``cat_political_office``) de "Deputado Federal" qual o valor que cada candidato recebeu, o valor médio de doções e a relação entre os dois, ordene pelos candidatos com mais doações relativas.

## 9. Crie uma *query* que responda:

Liste todos os candidatos, o seu valor recebido em doação, o valor médio de doações pelo posto correspondente ao do candidato e a relação entre o Recebido pelo candidato e a média do posto concorrido.

## 10. Crie uma *query* que responda:

Crie uma tabela com base no resultado anterior, filtrando somente candidatos que receberam mais do que 0,1% da média total do seu posto. 
