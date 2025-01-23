# Projeto-Iphone-WebScraping
O projeto consiste em buscar o preço de um produto (iPhone) em um site (Mercado Livre) por meio de web scraping, utilizando a biblioteca **BeautifulSoup**, para monitorar seu preço, salvar o histórico de preços em um banco de dados e enviar notificações ao usuário por meio de um bot no **Telegram**.

Link do escalidraw: [Projeto WebScraping](https://excalidraw.com/#room=ee31a791551bb25f8e2d,P4cjO4dr8TuJ5TfgcF_33A)

---

# Tecnologias e Ferramentas Usadas

- **Python**
- **BeautifulSoup**: Para parsing de HTML e extração de informações.
- **SQL**: Para gerenciamento e armazenamento de dados no banco.
- **Docker**: Para criar e gerenciar ambientes isolados para o projeto.
- **Bot Telegram**: Para enviar notificações de preço.
---


# Estrutura dos Aplicativos

## **app_1: Coletor de Dados com `requests`**
Esse módulo faz requisições HTTP para acessar o conteúdo HTML das páginas de produtos. Ele coleta o HTML bruto que será processado pelo **app_2**.

## **app_2: Parser de HTML com `BeautifulSoup`**
Esse módulo recebe o HTML do **app_1** e utiliza o **BeautifulSoup** para extrair informações específicas, como o preço atual do produto.

## **app_3: Agendamento de Tarefas com `schedule`**
Esse módulo usa **schedule** para definir a frequência com que o monitoramento de preços é executado. Por exemplo, pode ser configurado para verificar o preço a cada 10 minutos.

## **app_4: Manipulação de Dados com `pandas`**
Esse módulo organiza os dados coletados e pode salvar o histórico de preços em um arquivo CSV para facilitar a análise e o armazenamento.

## **app_5: Banco de Dados com `sqlite3`**
Esse módulo gerencia o banco de dados SQLite, criando tabelas e armazenando informações do histórico de preços.

## **app_6: Comparação de Preços (`max_price`)**
Esse módulo compara o preço atual do produto com o **max_price** definido pelo usuário. Caso o preço esteja abaixo do limite, ele envia uma notificação usando o **app_7**.

## **app_7: Envio de Notificação com Telegram**
Esse módulo utiliza a biblioteca **python-telegram-bot** para enviar uma mensagem ao Telegram informando que o preço atingiu o valor desejado.
