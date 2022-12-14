# BDD Specs

## Narrativa 1

```
    Como um cliente online 
    Quero que o sistema me mostre minhas compras
    Para eu poder controlar minhas despesas
```

### Cenários

```
    Dado que o cliente tem conexão com a internet
    Quando o cliente solicitar para carregar suas compras
    Então o sistema deve exibir suas compras vindo de uma API
    E substituir os dados do cache com os dados mais atuais
```

## Narrativa 2

```
    Como um cliente offline
    Quero que o sistema me mostre minhas últimas compras gravadas
    Para eu poder ver minhas despesas mesmo sem ter internet
```

### Cenários

```
    Dado que o cliente não tem conexão com a internet
        E exista algum dado gravado no cache
        E os dados do cache forem mais novos que 3 dias 
    Quando o cliete solicitar para carregar suas compras
    Então o sistema deve exibir suas compras vindas do cache 

    Dado que o clienyte nçai tem conexão com a internet 
        E exista algum dado gravado  no cache 
        E os dados do cache forem  mais velhos ou iguais a 3 dias
    Quando o cliente solicitar para carregar suas compras
    Então o sistema deve exibir uma mensagem de erro

    Dado que o cliente não tem conexão com a internet
        E o cache esteja vazio
    Quando o cliente solicitar para carregar suas compras
    Então o sistema deve exibir uma mensagem de erro
```

# Gravar Compras no Cache

> ## Caso de sucesso
1. Sistema executa o comando "Salvar Compras" - :white_check_mark:
2. Sistema cria data uma data para ser armazenada no Cache
3. Sistema apaga os dados do Cache atual - :white_check_mark:
4. Sistema grava os novos dados no Cache - :white_check_mark:
5. Sistema não retorna nenhum erro

> ## Exceção - Erro ao apagar dados do Cache
1. Sistema não grava os novos dados do Cache - :white_check_mark:
2. Sistema retorna erro - :white_check_mark:

> ## Exceção - Erro ao gravar dados no Cache
1. Sistema retorna erro - :white_check_mark:
<hr style="border:2px solid gray">

# Carregar Compras do cache

> ## Caso de sucesso
1. Sistema executa o comnado "Carregar Compras"
2. Sistema carrega os dados do Cache
3. Sistema valida se o Cache tem menos de 3 dias
4. Sistema cria uma lista de compras a partir dos dados do Cache
5. Sistema retorna a lista de compras

> ## Execução - Cache expirado
1. Sistema limpa o cache
2. Sistema retorna erro

> ## Exceção - Cache vazio
1. Sistema retorna erro