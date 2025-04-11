# exercicio-mecanica

# Sistema de Controle e Gerenciamento de Ordens de Serviço

## Objetivo
Criar o esquema conceitual para o contexto de oficina com base na narrativa fornecida.

## Narrativa
Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica. Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões periódicas. Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega. A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra. O valor de cada peça também irá compor a OS. O cliente autoriza a execução dos serviços. A mesma equipe avalia e executa os serviços. Os mecânicos possuem código, nome, endereço e especialidade. Cada OS possui: número, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

## Esquema Conceitual

### Entidades e Atributos

1. **Cliente**
   - ID_Cliente
   - Nome
   - Endereço
   - Telefone
   - Email

2. **Veículo**
   - ID_Veículo
   - ID_Cliente (FK)
   - Placa
   - Modelo
   - Ano

3. **Mecânico**
   - ID_Mecânico
   - Nome
   - Endereço
   - Especialidade

4. **Ordem de Serviço (OS)**
   - ID_OS
   - ID_Veículo (FK)
   - ID_Mecânico (FK)
   - Data_Emissão
   - Valor
   - Status
   - Data_Conclusão

5. **Serviço**
   - ID_Serviço
   - Descrição
   - Valor_Mão_de_Obra

6. **Peça**
   - ID_Peça
   - Descrição
   - Valor

### Relacionamentos

- **Cliente** 1:N **Veículo** (Um cliente pode ter vários veículos)
- **Veículo** 1:N **Ordem de Serviço (OS)** (Um veículo pode ter várias ordens de serviço)
- **Mecânico** 1:N **Ordem de Serviço (OS)** (Um mecânico pode ser responsável por várias ordens de serviço)
- **Ordem de Serviço (OS)** N:M **Serviço** (Uma ordem de serviço pode incluir vários serviços e um serviço pode estar em várias ordens de serviço)
- **Ordem de Serviço (OS)** N:M **Peça** (Uma ordem de serviço pode incluir várias peças e uma peça pode estar em várias ordens de serviço)

## Exemplo de Tabelas em Markdown

### Cliente

| ID_Cliente | Nome | Endereço | Telefone | Email |
|------------|------|----------|----------|-------|
| 1          | João | Rua A, 123 | (11) 1234-5678 | joao@example.com |
| 2          | Maria | Av. B, 456 | (11) 9876-5432 | maria@example.com |

### Veículo

| ID_Veículo | ID_Cliente | Placa | Modelo | Ano |
|------------|------------|-------|--------|-----|
| 1          | 1          | ABC-1234 | Gol | 2015 |
| 2          | 2          | XYZ-5678 | Palio | 2018 |

### Mecânico

| ID_Mecânico | Nome | Endereço | Especialidade |
|-------------|------|----------|---------------|
| 1           | Carlos | Rua C, 789 | Motor |
| 2           | Ana    | Av. D, 101 | Suspensão |

### Ordem de Serviço (OS)

| ID_OS | ID_Veículo | ID_Mecânico | Data_Emissão | Valor | Status | Data_Conclusão |
|-------|------------|-------------|--------------|-------|--------|----------------|
| 1     | 1          | 1           | 2025-04-11   | 500.00 | Em andamento | 2025-04-15 |
| 2     | 2          | 2           | 2025-04-11   | 300.00 | Concluída    | 2025-04-12 |

### Serviço

| ID_Serviço | Descrição | Valor_Mão_de_Obra |
|------------|-----------|-------------------|
| 1          | Troca de óleo | 100.00 |
| 2          | Alinhamento   | 150.00 |

### Peça

| ID_Peça | Descrição | Valor |
|---------|-----------|-------|
| 1       | Filtro de óleo | 50.00 |
| 2       | Pneu          | 200.00 |

4. **Faça Commit e Push das Alterações**
   - Salve o arquivo `README.md`.
   - No terminal, execute os comandos:
     ```sh
     git add README.md
     git commit -m "Adiciona descrição do projeto e esquema conceitual"
     git push origin main
     ```

Pronto! Seu esquema conceitual e a descrição do projeto estarão disponíveis no repositório do GitHub para futura avaliação. Se precisar de mais alguma coisa, estou aqui para ajudar! 😊
