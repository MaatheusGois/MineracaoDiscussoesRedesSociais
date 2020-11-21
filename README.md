# Mineracao de Discussoes em RedesSociais

Este repositório integra uma solução para extração e classificação de discussões em redes sociais. Desenvolvida no projeto de TCC "Argumentation Mining: visualização de discussões em redes sociais"


## Propósito

Argumentation Mining é uma área de pesquisa na interface entre Linguística Computacional e Ciência de Dados, com grande importância para processos de tomada de decisão, incluindo a identificação e recuperação da estrutura de uma discussão. Este trabalho busca construir um processo de análise de discussões, com a finalidade de compreender a estrutura de uma discussão e a polaridade dos seus argumentos. Para isso foram usadas técnicas de análise de sentimentos. Os resultados obtidos serão usados para alimentar a ferramenta de visualização de discussões Visu `<https://rlage.github.io/visu/?fbclid=IwAR2tz9UaRCEMu6bp_YWpjUCpQJnqU8RszPtXOI4MOdi8yAxBvGUodc-htXY>` como forma de facilitar o acompanhamento e entendimento das discussões em redes sociais.


## Como utilizar os notebooks jupyter

Os notebooks jupyter fornecidos possuem 3 funcionalidades diferentes, dependendo da sua necesside:

### 1) Tcc_Scrapper.ipynb 
  * Responsável por extrair dados de uma discussão da rede social Reddit para um arquivo .csv.
  * Para utilização é necessário credenciais de acesso a API do Reddit, fornecidas ao cadastrar um cliente nesse link: `<https://www.reddit.com/prefs/apps>`
  * Com o acesso disponível, basta inserir o link de uma postagem no Reddit e a ferramenta irá extrair os comentários, com as seguintes informações: indice, autor, data, hora, conteúdo da mensagem, tópico, polaridade, e indice resposta.
  * Todos os comentários extraídos são classificados com polaridade neutra inicialmente. Para classificar a polaridade corretamente, é preciso utilizar o arquivo `.csv` gerado no próximo notebook `TCC_Analise de Sentimento.ipynb`.

### 2) Tcc_Analise de Sentimento.ipynb 
  * Responsável por extrair classificar os argumentos de uma discussão.
   
  *  **Para utilização é necessário que os arquivos da pasta `datasets\csv` estejam descompactados.**
  * A classificação é feita com o classificador SGD, treinado pela base Internet Argument Corpus `<https://nlds.soe.ucsc.edu/iac>`.
  * Basta seguir a sequência das células do notebook para carregar todos os elementos necessários para classificação dos argumentos.
 
  
 ### 3) Tcc_CsvToVisu.ipynb 
  * Responsável por formatar o arquivo .csv gerado pela classificação de argumentos de acordo com as regras para ferramenta Visu
  * O arquivo final `Saida_Visu.txt` pode ser utilizado diretamente na ferramenta Visu como insumo para as visualizações.
