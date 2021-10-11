# ![Icone Python](https://img.icons8.com/nolan/50/python.png) Acesso API de Cotação do Dólar, Euro e Bitcoin com Python

Olá, seja muito bem vinda(o)! 

📚 Aproveite o código desse exercício para requisitar (solicitar / acessar) os valores das cotações de forma atualizada usando: https://docs.awesomeapi.com.br/api-de-moedas.

👩‍💻 Refaça do seu jeito

😉 Se tiver qualquer dúvida, me contate


## 📚 Sobre

> 🌐 API: É uma sigla do inglês que significa Application Programming Interface, uma Interface de Programação de Aplicativos. Se trata de um conjunto de padrões que fazem parte de uma interface e que permite a criação de plataformas de maneira mais simples e prática para desenvolvedores. 

> 🐍 Python: É uma linguagem de programação de alto nível, ou seja, com sintaxe mais simplificada e próxima da linguagem humana, utilizada nas mais diversas aplicações, como desktop, web, servidores e ciência de dados.


## ⏩ Instalação do Pacote Anaconda Jupyter para programar em Python

1. Acesse o site: www.anaconda.com
2. Selecione "Products" e clique em "Individual Edition"
> Obs: Anaconda Individual Edition é uma solução de código aberto que fornece utilitários para construir, distribuir, instalar, atualizar e gerenciar software em plataforma com Python.

3. Realize o download de acordo com o sistema operacional da sua máquina
4. Execute o instalador
    - Selecione o local onde será realizada a instalação do programa
    - Se preferir, desmarque as caixas de tutorial e arquivo de ajuda
    
    
## 💻 Abrindo e acessando

1. Pesquise "Jupyter" no menu iniciar do Windows e abra 
> Obs: Se não aparecer nenhum resultado para a sua pesquisa, reinicie o seu computador

2. Abrirá o Jupyter Notebook e uma guia no navegador para que você acesse os arquivos
> ❗ Importante: Não feche o Jupyter Notebook enquanto estiver utilizando o Jupyter. Caso o navegador não abra automaticamente, copie o último link que aparece no Jupyter e cole no seu navegador.

## 📝 Criando o arquivo e a pasta no Jupyter

Na página aberta do navegador você conseguirá visualizar as pastas do seu computador e acessá-las para criar o seu arquivo.
1. Abra a pasta onde deseja salvar
2. Clique em "New" no canto superior direito
3. Selecione "Folder", criará uma pasta como "Untitled Folder"
4. Selecione / flag a caixa de seleção da pasta, clique em "Rename" no canto superior esquerdo e preencha o nome da sua pasta, exemplo "Acesso-API-Cotacao"
5. Acesse a pasta
6. Clique em "New" no canto superior direito
7. Selecione "Notebook: Python 3", o arquivo será criado e aberto
8. Renomei como desejar selecionando o título padrão "Untitled" gerado no topo da página.

###### 💬 Criar linhas: Selecione "Insert" no menu e escolha se prefere que ela apareça acima (Above) ou abaixo (Below) da linha que você está editando

###### 💬 Deletar linhas: Selecione "Edit" no menu e clique em "Delete Cells"

###### 💬 Tipos de linha: Para criar outros tipos de linha selecione "Cell" no menu, "Cell Type" e escolha a que preferir

9. Para abrir a requisição dos dados da API importe a biblioteca "requests" digitando no seu arquivo:  import requests
    - Essa biblioteca já vem no Python, mas se não existir na sua máquina, pesquise "Anaconda Prompt" no menu iniciar do Windows e abra
    - Digite no Prompt: pip install requests
    - Aperte o Enter
10. Importe a biblioteca JSON digitando no Jupyter: import json
    > Isso é necessário, pois as informações vem no formato de dicionário que não é o padrão do Python, e sim JSON comumente usado para troca informações entre sites
11. Para acessar as informações das cotações, digite no Jupyter: cotacoes = requests.get()


## 🌐 API

1. Para consumir os dados da API pública de cotações de moedas, acesse: https://docs.awesomeapi.com.br/
2. Selecione "API de Cotações de Moedas"
3. No site copie o link que retorna a última ocorrência das moedas, exemplo: https://economia.awesomeapi.com.br/last/USD-BRL,EUR-BRL,BTC-BRL

## ▶ Realizando as requisições

1. Cole o link dentro do parênteses e entre aspas, deverá ficar assim:
    ```
    cotacoes = requests.get("https://economia.awesomeapi.com.br/last/USD-BRL,EUR-BRL,BTC-BRL")
    ```
    
2. Para validar e imprimir as informações digite no Jupyter: print(cotacoes)

> Para executar o código selecione "Cell" e clique em "Run Cell", ou use o atalho: Ctrl + Enter

O código ficará assim:
```python
import requests
import json

cotacoes = requests.get("https://economia.awesomeapi.com.br/last/USD-BRL,EUR-BRL,BTC-BRL")
print(cotacoes)
```

O resultado "200" mostra que a solicitação funcionou:
```
<Response [200]>
```


## 🔃 JSON para Python

Para transformar de JSON para Python digite na linha acima do "print": cotacoes = cotacoes.json()
    - Isso é feito, pois as informações da requisição estão armazenadas dentro da variável "cotacoes" no formato JSON

O resultado ficará assim agora:
```
{'USDBRL': {'code': 'USD', 'codein': 'BRL', 'name': 'Dólar Americano/Real Brasileiro', 'high': '5.3239', 'low': '5.263', 'varBid': '0.0162', 'pctChange': '0.31', 'bid': '5.3098', 'ask': '5.3123', 'timestamp': '1629299404', 'create_date': '2021-08-18 12:10:08'}, 'EURBRL': {'code': 'EUR', 'codein': 'BRL', 'name': 'Euro/Real Brasileiro', 'high': '6.2333', 'low': '6.1663', 'varBid': '0.0198', 'pctChange': '0.32', 'bid': '6.2173', 'ask': '6.2218', 'timestamp': '1629299403', 'create_date': '2021-08-18 12:10:05'}, 'BTCBRL': {'code': 'BTC', 'codein': 'BRL', 'name': 'Bitcoin/Real Brasileiro', 'high': '174000', 'low': '163120', 'varBid': '5469.9', 'pctChange': '3.25', 'bid': '173947.2', 'ask': '173947.2', 'timestamp': '1624558019', 'create_date': '2021-06-24 15:07:00'}}
```

## 🔎 Visualizar apenas uma cotação

1. Para ver as cotações do Bitcoin adicione na linha acima do "print": cotacao_bitcoin = cotacoes['BTCBRL']
2. Substitua o "print(cotacoes)" por: print(cotacao_bitcoin)
O resultado será:
```
{'code': 'BTC', 'codein': 'BRL', 'name': 'Bitcoin/Real Brasileiro', 'high': '174000', 'low': '163120', 'varBid': '5469.9', 'pctChange': '3.25', 'bid': '173947.2', 'ask': '173947.2', 'timestamp': '1624558019', 'create_date': '2021-06-24 15:06:59'}
```

3. Usando como base o resultado acima, para imprimir apenas o valor da contação adicione o "bid" dentro de aspas duplas e colchetes após o código que representa o Bitcoin, assim:
```
cotacao_bitcoin = cotacoes['BTCBRL']["bid"]
```
Aparecerá o valor a cotação naquele momento, exemplo: 173947.2

## ✔ Melhorando o código:

Você pode refazer o código do seu jeito, colocar outras cotações e mais informações, segue um exemplo de código:

```python
import requests
import json

cotacoes = requests.get("https://economia.awesomeapi.com.br/last/USD-BRL,EUR-BRL,BTC-BRL")
cotacoes = cotacoes.json()
cotacao_dolar = cotacoes['USDBRL']["bid"]
cotacao_euro = cotacoes['EURBRL']["bid"]
cotacao_bitcoin = cotacoes['BTCBRL']["bid"]

print("\n Cotação do Dólar Americano/Real Brasileiro: ", cotacao_dolar)
print("\n Cotação do Euro/Real Brasileiro: ", cotacao_euro)
print("\n Cotação do Bitcoin/Real Brasileiro: ", cotacao_bitcoin)
print("\n Cotações sem formatação: \n",cotacoes)
```

O resultado do código acima será:
    
     Cotação do Dólar Americano/Real Brasileiro:  5.3098
    
     Cotação do Euro/Real Brasileiro:  6.2173
    
     Cotação do Bitcoin/Real Brasileiro:  173947.2
    
     Cotações sem formatação: 
     {'USDBRL': {'code': 'USD', 'codein': 'BRL', 'name': 'Dólar Americano/Real Brasileiro', 'high': '5.3239', 'low': '5.263', 'varBid': '0.0162', 'pctChange': '0.31', 'bid': '5.3098', 'ask': '5.3123', 'timestamp': '1629299404', 'create_date': '2021-08-18 12:10:08'}, 'EURBRL': {'code': 'EUR', 'codein': 'BRL', 'name': 'Euro/Real Brasileiro', 'high': '6.2333', 'low': '6.1663', 'varBid': '0.0198', 'pctChange': '0.32', 'bid': '6.2173', 'ask': '6.2218', 'timestamp': '1629299403', 'create_date': '2021-08-18 12:10:05'}, 'BTCBRL': {'code': 'BTC', 'codein': 'BRL', 'name': 'Bitcoin/Real Brasileiro', 'high': '174000', 'low': '163120', 'varBid': '5469.9', 'pctChange': '3.25', 'bid': '173947.2', 'ask': '173947.2', 'timestamp': '1624558019', 'create_date': '2021-06-24 15:07:00'}}
    
    
## ✍ Referências

📘 Hashtag Programação - [O que é API (Application Programming Interface) e Como Usar API com Python?](https://youtu.be/eel1OVIdfUw)
<br>
Nesse vídeo você verá o que são e como acessar APIs com Python.

📗 Hashtag Treinamentos - [Como Instalar o Pacote Anaconda](https://www.hashtagtreinamentos.com/instalar-pacote-anaconda-jupyter-python)
<br>
Passo a passo de como instalar o pacote Anaconda Jupyter para iniciar na programação com Python utilizando essa IDE.


## ❓ Dúvidas

Se precisar de ajuda, entre em contato comigo 😉

[<img align="left" alt="Discord" width="100px" src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white"/>](https://discord.gg/C4PFK4W4HN)
[<img align="left" alt="Gmail" width="80px" src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>](mailto:anabe.valentim@gmail.com)
[<img align="left" alt="LinkedIn" width="100px" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>](https://www.linkedin.com/in/ana-beatriz-valentim)
[<img align="left" alt="Beacons" width="80px" src="https://github.com/AnaProgramando/AnaProgramando/blob/31ac40741768033915a37ec0f949984bf6aad2d1/beacons_logo.png"/>](https://beacons.page/anaprogramando)
<br>


<br>[⬆ Voltar ao top](#-acesso-api-de-cota%C3%A7%C3%A3o-do-d%C3%B3lar-euro-e-bitcoin-com-python) <br>
