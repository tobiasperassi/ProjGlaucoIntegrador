# Caso de Uso Expandido: UC01 - Registrar Pedido

## 1. Identificação

**Nome do Caso de Uso:** Registrar Pedido

**ID:** UC01

**Versão:** 1.0

**Data:** 2025

**Prioridade:** Alta (Essencial)

---

## 2. Descrição

Este caso de uso descreve o processo pelo qual o atendente registra um pedido feito por um cliente, incluindo a seleção de itens do cardápio e o envio do pedido para a cozinha.

---

## 3. Atores

### Ator Principal
- **Atendente**: Funcionário responsável por receber e registrar os pedidos dos clientes

### Atores Secundários
- **Cliente**: Pessoa que realiza o pedido
- **Sistema de Cozinha**: Subsistema que recebe os pedidos para preparo

---

## 4. Partes Interessadas e Interesses

- **Cliente**: Deseja fazer um pedido de forma rápida, precisa e sem erros
- **Atendente**: Deseja registrar o pedido de forma eficiente, evitando retrabalho
- **Cozinha**: Deseja receber pedidos claros, organizados e em tempo real
- **Gerente**: Deseja que os pedidos sejam registrados corretamente para controle de vendas e relatórios
- **Estabelecimento**: Deseja otimizar o processo de atendimento e reduzir erros

---

## 5. Pré-condições

- O atendente está autenticado no sistema
- O cardápio está cadastrado e atualizado no sistema
- O sistema está operacional e conectado

---

## 6. Pós-condições (Garantias de Sucesso)

- O pedido é registrado no sistema com número único
- O pedido contém todos os itens solicitados pelo cliente
- O pedido é enviado para a fila da cozinha
- O histórico do pedido é armazenado para consultas futuras
- O cliente recebe o número do pedido para acompanhamento

---

## 7. Cenário de Sucesso Principal (Fluxo Básico)

| Passo | Ação do Ator | Ação do Sistema |
|-------|--------------|-----------------|
| 1 | Cliente chega ao estabelecimento e consulta o cardápio impresso | |
| 2 | Cliente informa ao atendente os itens que deseja pedir | |
| 3 | Atendente inicia o registro de um novo pedido no sistema | Sistema exibe a tela de novo pedido em branco |
| 4 | | Sistema gera um número de pedido provisório |
| 5 | Atendente seleciona a categoria do primeiro item (ex: sanduíches, bebidas, sobremesas) | Sistema exibe os produtos da categoria selecionada |
| 6 | Atendente seleciona o produto desejado | Sistema adiciona o item ao pedido |
| 7 | Atendente informa a quantidade do item (se diferente de 1) | Sistema atualiza a quantidade do item no pedido |
| 8 | Atendente adiciona observações ao item, se necessário (ex: "sem cebola") | Sistema registra as observações junto ao item |
| 9 | Atendente repete os passos 5-8 para cada item do pedido | Sistema atualiza a lista de itens e o valor total |
| 10 | Atendente revisa o pedido com o cliente | Sistema exibe resumo do pedido com todos os itens e valor total |
| 11 | Atendente confirma o pedido | Sistema valida o pedido |
| 12 | | Sistema registra o pedido com data/hora e número definitivo |
| 13 | | Sistema envia o pedido para a fila da cozinha |
| 14 | | Sistema marca o status do pedido como "Enviado para Cozinha" |
| 15 | | Sistema exibe mensagem de confirmação com o número do pedido |
| 16 | Atendente informa ao cliente o número do pedido | |
| 17 | Cliente aguarda o chamado para retirada | |

---

## 8. Fluxos Alternativos

### 8.1 Fluxo Alternativo 3a - Cliente desiste do pedido

**Ponto de Extensão:** Passo 3 do fluxo principal

| Passo | Ação |
|-------|------|
| 3a.1 | Cliente decide não fazer o pedido |
| 3a.2 | Atendente seleciona a opção "Cancelar Pedido" |
| 3a.3 | Sistema solicita confirmação do cancelamento |
| 3a.4 | Atendente confirma o cancelamento |
| 3a.5 | Sistema descarta o pedido em andamento sem registrar |
| 3a.6 | Sistema retorna à tela inicial |
| 3a.7 | **Caso de uso termina** |

---

### 8.2 Fluxo Alternativo 4a - Item não está disponível

**Ponto de Extensão:** Passos 5-6 do fluxo principal

| Passo | Ação |
|-------|------|
| 4a.1 | Atendente identifica que o item desejado não está disponível |
| 4a.2 | Atendente informa ao cliente sobre a indisponibilidade |
| 4a.3 | Cliente escolhe uma das opções: |
| | **Opção A:** Cliente escolhe outro item - retorna ao passo 5 |
| | **Opção B:** Cliente remove o item do pedido - continua com os demais itens |
| | **Opção C:** Cliente desiste do pedido - vai para fluxo 3a |

---

### 8.3 Fluxo Alternativo 4b - Adicionar observações específicas

**Ponto de Extensão:** Passo 8 do fluxo principal

| Passo | Ação |
|-------|------|
| 4b.1 | Cliente solicita observações especiais para o item (ex: "sem cebola", "bem passado", "com molho extra") |
| 4b.2 | Atendente seleciona o campo de observações do item |
| 4b.3 | Sistema exibe campo de texto para observações |
| 4b.4 | Atendente digita as observações do cliente |
| 4b.5 | Sistema armazena as observações junto ao item |
| 4b.6 | Sistema exibe as observações no resumo do pedido |
| 4b.7 | **Retorna ao passo 9 do fluxo principal** |

---

### 8.4 Fluxo Alternativo 5a - Cliente lembra de mais itens

**Ponto de Extensão:** Passo 10 do fluxo principal

| Passo | Ação |
|-------|------|
| 5a.1 | Durante a revisão, cliente lembra de adicionar mais itens |
| 5a.2 | Atendente seleciona a opção "Adicionar Item" |
| 5a.3 | **Retorna ao passo 5 do fluxo principal** |

---

### 8.5 Fluxo Alternativo 6a - Cliente deseja remover item

**Ponto de Extensão:** Passo 10 do fluxo principal

| Passo | Ação |
|-------|------|
| 6a.1 | Durante a revisão, cliente deseja remover um item |
| 6a.2 | Atendente seleciona o item a ser removido |
| 6a.3 | Atendente seleciona a opção "Remover Item" |
| 6a.4 | Sistema remove o item da lista |
| 6a.5 | Sistema recalcula o valor total |
| 6a.6 | **Retorna ao passo 10 do fluxo principal** |

---

### 8.6 Fluxo Alternativo 7a - Cliente deseja alterar quantidade

**Ponto de Extensão:** Passo 10 do fluxo principal

| Passo | Ação |
|-------|------|
| 7a.1 | Durante a revisão, cliente deseja alterar a quantidade de um item |
| 7a.2 | Atendente seleciona o item |
| 7a.3 | Atendente altera a quantidade |
| 7a.4 | Sistema atualiza a quantidade e recalcula o valor total |
| 7a.5 | **Retorna ao passo 10 do fluxo principal** |

---

## 9. Fluxos de Exceção

### 9.1 Exceção E1 - Falha na comunicação com a cozinha

**Ponto de Extensão:** Passo 13 do fluxo principal

| Passo | Ação |
|-------|------|
| E1.1 | Sistema tenta enviar o pedido para a cozinha mas a comunicação falha |
| E1.2 | Sistema armazena o pedido em uma fila de pendências |
| E1.3 | Sistema exibe mensagem de alerta ao atendente: "Pedido registrado mas não enviado para cozinha - Comunicação falhou" |
| E1.4 | Sistema marca o pedido com status "Pendente de Envio" |
| E1.5 | Atendente informa ao cliente que o pedido foi registrado |
| E1.6 | Sistema tentará reenviar automaticamente quando a conexão for restabelecida |
| E1.7 | **Caso de uso termina** |

---

### 9.2 Exceção E2 - Sistema indisponível

**Ponto de Extensão:** Passo 3 do fluxo principal

| Passo | Ação |
|-------|------|
| E2.1 | Sistema está indisponível ou não responde |
| E2.2 | Atendente registra o pedido manualmente em papel |
| E2.3 | Atendente envia o pedido físico para a cozinha |
| E2.4 | Quando o sistema retornar, atendente deverá registrar o pedido retroativamente |
| E2.5 | **Caso de uso termina** |

---

## 10. Requisitos Especiais

### 10.1 Desempenho
- O sistema deve responder em menos de 2 segundos para cada operação
- O sistema deve suportar múltiplos atendentes registrando pedidos simultaneamente

### 10.2 Usabilidade
- Interface deve ser intuitiva para uso sob pressão em horários de pico
- Botões e textos devem ser legíveis e de tamanho adequado para touch-screen
- Sistema deve usar cores e ícones para facilitar a identificação de categorias

### 10.3 Confiabilidade
- O sistema deve ter disponibilidade de 99% durante horário de funcionamento
- Sistema deve ter mecanismo de backup local em caso de falha de comunicação

### 10.4 Segurança
- Apenas atendentes autenticados podem registrar pedidos
- Cada pedido deve registrar qual atendente o criou (rastreabilidade)

---

## 11. Lista de Variações Tecnológicas

- **Terminal touch-screen:** Interface otimizada para toque
- **Tablet:** Versão mobile responsiva
- **Desktop:** Interface tradicional com mouse e teclado
- **Impressora térmica:** Para imprimir comprovante do pedido (opcional)

---

## 12. Frequência de Ocorrência

Este caso de uso pode ocorrer **continuamente** durante todo o horário de atendimento do estabelecimento. Em horários de pico, podem ocorrer dezenas de pedidos por hora.

---

## 13. Questões em Aberto

1. Haverá algum limite máximo de itens por pedido?
2. O sistema deve permitir pedidos para viagem (take-away)?
3. Deve haver diferenciação entre pedidos para consumo local e para viagem?
4. O sistema deve imprimir comprovante automaticamente ou apenas quando solicitado?
5. Haverá numeração sequencial única ou reset diário dos números de pedido?

---

## 14. Protótipo de Interface

### Tela 1: Novo Pedido
```
+------------------------------------------+
|  [< Voltar]  NOVO PEDIDO  [Cancelar X]  |
+------------------------------------------+
|  Pedido #: ___  (em construção)          |
|  Atendente: João Silva                    |
+------------------------------------------+
|  CATEGORIAS:                              |
|  [Sanduíches] [Bebidas] [Sobremesas]     |
+------------------------------------------+
|  ITENS DO PEDIDO:              Total: R$ |
|                                           |
|  (vazio)                                  |
|                                           |
|                                           |
+------------------------------------------+
|           [+ Adicionar Item]              |
|           [Confirmar Pedido]              |
+------------------------------------------+
```

### Tela 2: Pedido com Itens
```
+------------------------------------------+
|  [< Voltar]  NOVO PEDIDO  [Cancelar X]  |
+------------------------------------------+
|  Pedido #: 042                           |
|  Atendente: João Silva                    |
+------------------------------------------+
|  CATEGORIAS:                              |
|  [Sanduíches] [Bebidas] [Sobremesas]     |
+------------------------------------------+
|  ITENS DO PEDIDO:        Total: R$ 25,00 |
|                                           |
|  1x X-Burger............R$ 15,00  [Edit] |
|     Obs: Sem cebola                      |
|  1x Coca-Cola 350ml.....R$ 5,00   [Edit] |
|  1x Batata Frita........R$ 5,00   [Edit] |
|                                           |
+------------------------------------------+
|           [+ Adicionar Item]              |
|           [Confirmar Pedido]              |
+------------------------------------------+
```

### Tela 3: Confirmação
```
+------------------------------------------+
|            PEDIDO REGISTRADO             |
+------------------------------------------+
|                                           |
|          Pedido Nº 042                   |
|                                           |
|    Enviado para a cozinha com sucesso!   |
|                                           |
|    Cliente: Informe o número 042         |
|                                           |
|                                           |
|           [OK - Novo Pedido]             |
|           [Imprimir Comprovante]          |
+------------------------------------------+
```
