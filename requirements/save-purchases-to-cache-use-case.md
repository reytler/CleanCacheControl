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