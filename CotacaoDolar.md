# Acesso a API de Cotação do Dólar com Python

Objetivo: Pegar a cotação do dólar de forma automática e atualizada
Usado: https://docs.awesomeapi.com.br/api-de-moedas



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

    
     Cotação do Dólar Americano/Real Brasileiro:  5.3098
    
     Cotação do Euro/Real Brasileiro:  6.2173
    
     Cotação do Bitcoin/Real Brasileiro:  173947.2
    
     Cotações sem formatação: 
     {'USDBRL': {'code': 'USD', 'codein': 'BRL', 'name': 'Dólar Americano/Real Brasileiro', 'high': '5.3239', 'low': '5.263', 'varBid': '0.0162', 'pctChange': '0.31', 'bid': '5.3098', 'ask': '5.3123', 'timestamp': '1629299404', 'create_date': '2021-08-18 12:10:08'}, 'EURBRL': {'code': 'EUR', 'codein': 'BRL', 'name': 'Euro/Real Brasileiro', 'high': '6.2333', 'low': '6.1663', 'varBid': '0.0198', 'pctChange': '0.32', 'bid': '6.2173', 'ask': '6.2218', 'timestamp': '1629299403', 'create_date': '2021-08-18 12:10:05'}, 'BTCBRL': {'code': 'BTC', 'codein': 'BRL', 'name': 'Bitcoin/Real Brasileiro', 'high': '174000', 'low': '163120', 'varBid': '5469.9', 'pctChange': '3.25', 'bid': '173947.2', 'ask': '173947.2', 'timestamp': '1624558019', 'create_date': '2021-06-24 15:07:00'}}
    
