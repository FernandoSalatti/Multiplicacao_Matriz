# 🖥️ cluster

**Alunos**:  
- André Comin  
- Fernando Salatti  

## 🎯 Objetivo

Desenvolvimento de um cluster utilizando containers Docker destinado à disciplina de Arquitetura de Computadores II (GB). Neste projeto, são configurados entre 1 e 5 nós, consistindo em um master e até 4 slaves, para a execução de um script responsável pela multiplicação de matrizes com dimensão 10000 por 10000. O resultado final do cálculo é armazenado no arquivo `resultado_matriz.txt`, localizado no container master. Para possibilitar a comunicação entre os nós do cluster, foi implementado o protocolo MPI, utilizando conexões SSH protegidas por autenticação com chaves RSA assinadas.

---

## ⚙️ Execução

Para executar o projeto é necessário que o Docker esteja previamente instalado no computador. Após a instalação, siga os passos abaixo:

- Utilize o comando: `docker compose up --build -d` para criar e inicializar os containers.
- Para acessar o container do nó master, execute: `docker exec -it -u 0 master-node /bin/sh`
- No terminal do master, utilize o comando: `sh run-five-nodes.sh` para executar o script com os 5 nós ativos.
- Caso prefira executar o script apenas no nó master, utilize o comando: `sh run-master.sh`

---

## 📄 Resultados das Execuções

Os resultados obtidos em cada configuração realizada estão disponíveis para consulta no arquivo `RESULTADOS.MD`.
