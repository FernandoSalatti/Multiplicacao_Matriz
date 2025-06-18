# 📊 Resultados Comparativos

Realizando a análise da multiplicação de uma matriz com dimensões 10000x10000, executada com configurações variando de 1 até 5 nodes. Cada célula da matriz foi inicializada com um valor aleatório entre 0 e 1. Para cada configuração, também foram testados diferentes números de processos.  
Os testes ocorreram em um ambiente docker configurado com recursos fixos: uma única CPU e memória RAM de 8 GB. Importante mencionar que todas as execuções foram feitas localmente, em um MacBook. Dessa forma, os tempos obtidos podem apresentar variações significativas ao serem executados em máquinas diferentes ou mesmo no mesmo equipamento sob condições variadas de uso da CPU.

## 📋 Tabela de Resultados

| Nodes | Processos | Tempo (s) |
|-------|-----------|-----------|
|   1   |     1     |   992,4   |
|   2   |     2     |   608,1   |
|   3   |     3     |   437,2   |
|   4   |     4     |   369,5   |
|   5   |     5     |   254,8   |

## 🧠 Análise

Devido ao fato de haver apenas um núcleo de processamento, pode se observar que a paralelização resultou em expressivas reduções no tempo total de execução. Cada incremento de nodes proporcionou ganhos próximos à divisão ideal do tempo total pela quantidade de nodes. Contudo, os ganhos não foram exatamente proporcionais, devido ao overhead associado à comunicação de dados entre os nodes, requisito inexistente na execução totalmente sequencial.

A implementação do MPI exije modificações no nível do código-fonte, tornando-se relativamente complexa, e ao declínio disto a ferramenta demonstrou-se extremamente eficaz para alcançar alto desempenho em aplicações que exigem processamento paralelo. Por outro lado, considerando o ambiente restrito a uma única CPU, o oversubscription não resultou em melhorias de performance, os valores seguiram o padrão que vinham desempenhando na tabela.
