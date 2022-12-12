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