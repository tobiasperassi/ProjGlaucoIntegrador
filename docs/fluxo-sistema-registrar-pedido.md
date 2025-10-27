# Fluxo do Sistema - Registrar Pedido

## 1. Visão Geral do Sistema

O sistema de registro de pedidos conecta três atores principais:
- **Atendente** (usuário do sistema)
- **Cliente** (consumidor final)
- **Cozinha** (receptora dos pedidos)

---

## 2. Diagrama de Contexto

```
┌──────────┐
│ Cliente  │
└────┬─────┘
     │ informa pedido
     ▼
┌─────────────┐                      ┌──────────────┐
│  Atendente  │◄────────────────────►│   Sistema    │
└─────────────┘  registra/consulta   │  Lanchonete  │
                                      └──────┬───────┘
                                             │ envia pedido
                                             ▼
                                      ┌──────────────┐
                                      │   Cozinha    │
                                      └──────────────┘
```

---

## 3. Fluxo Detalhado do Processo

### Fase 1: Atendimento Inicial
```
Cliente                    Atendente                    Sistema
   │                           │                           │
   │──(1) Consulta cardápio    │                           │
   │       impresso             │                           │
   │                           │                           │
   │──(2) Informa itens───────►│                           │
   │       desejados            │                           │
   │                           │                           │
   │                           │──(3) Inicia novo──────────►│
   │                           │       pedido               │
   │                           │                           │
   │                           │◄─(4) Gera número────────  │
   │                           │       provisório          │
```

### Fase 2: Construção do Pedido
```
Atendente                                            Sistema
   │                                                    │
   │──(5) Seleciona categoria (ex: Sanduíches)────────►│
   │                                                    │
   │◄─(6) Exibe produtos da categoria─────────────────  │
   │                                                    │
   │──(7) Seleciona produto (ex: X-Burger)────────────►│
   │                                                    │
   │◄─(8) Adiciona item ao pedido─────────────────────  │
   │       Atualiza valor total                        │
   │                                                    │
   │──(9) Define quantidade (se > 1)──────────────────►│
   │                                                    │
   │◄─(10) Atualiza quantidade e valor────────────────  │
   │                                                    │
   │──(11) Adiciona observações (opcional)────────────►│
   │        (ex: "sem cebola")                         │
   │                                                    │
   │◄─(12) Registra observações───────────────────────  │
   │                                                    │
   │          [Repete passos 5-12 para cada item]      │
```

### Fase 3: Revisão e Confirmação
```
Atendente         Cliente                    Sistema
   │                 │                           │
   │◄──(13) Exibe resumo────────────────────────  │
   │         completo do pedido                  │
   │                 │                           │
   │──(14) Revisa──►│                           │
   │         com cliente                         │
   │                 │                           │
   │◄──(15) Confirma pedido                      │
   │                 │                           │
   │──(16) Confirma no sistema─────────────────►│
   │                                             │
   │◄──(17) Valida pedido──────────────────────  │
   │         Registra com número definitivo     │
   │         Marca data/hora                     │
```

### Fase 4: Envio para Cozinha
```
Sistema                                    Cozinha
   │                                          │
   │──(18) Envia pedido──────────────────────►│
   │        para fila                          │
   │                                          │
   │◄─(19) Confirma recebimento──────────────  │
   │                                          │
   │──(20) Marca status: "Enviado"           │
   │                                          │
   │──(21) Exibe confirmação─────────────────►Atendente
   │        com número do pedido              │
```

### Fase 5: Finalização
```
Atendente                Cliente
   │                        │
   │──(22) Informa número──►│
   │        do pedido        │
   │                        │
   │                        │──(23) Aguarda
   │                        │       chamado
```

---

## 4. Fluxos Alternativos

### 4.1 Cliente Desiste Durante Atendimento

```
Cliente          Atendente                    Sistema
   │                 │                           │
   │──Desiste────────►│                           │
   │                 │                           │
   │                 │──Cancela pedido──────────►│
   │                 │                           │
   │                 │◄─Solicita confirmação───  │
   │                 │                           │
   │                 │──Confirma cancelamento───►│
   │                 │                           │
   │                 │◄─Descarta pedido──────────│
   │                 │   Retorna tela inicial    │
```

### 4.2 Item Indisponível

```
Cliente          Atendente                    Sistema
   │                 │                           │
   │──Pede item X────►│                           │
   │                 │                           │
   │                 │──(verifica disponibilidade)
   │                 │                           │
   │◄─Item não────────│                           │
   │   disponível     │                           │
   │                 │                           │
   │──Escolhe────────►│                           │
   │   alternativa    │                           │
   │                 │                           │
   │                 │──Adiciona item Y─────────►│
```

### 4.3 Cliente Adiciona Itens Durante Revisão

```
Atendente         Cliente                    Sistema
   │                 │                           │
   │◄──Exibe resumo─────────────────────────────  │
   │                 │                           │
   │──Revisa────────►│                           │
   │                 │                           │
   │◄─Lembra de──────│                           │
   │   mais itens     │                           │
   │                 │                           │
   │──Adiciona item──────────────────────────────►│
   │                 │                           │
   │          [Retorna ao fluxo de adicionar item]
```

### 4.4 Falha de Comunicação com Cozinha

```
Sistema                                    Cozinha
   │                                          │
   │──Tenta enviar pedido─────────────────X   │
   │                                (falha)
   │                                          │
   │──Armazena em fila de pendências         │
   │                                          │
   │──Marca status: "Pendente de Envio"      │
   │                                          │
   │──Alerta atendente sobre falha───────────►Atendente
   │                                          │
   │                                          │
   │  [Sistema tentará reenviar automaticamente]
   │  [quando conexão for restabelecida]      │
```

---

## 5. Estados do Pedido

Um pedido passa pelos seguintes estados durante seu ciclo de vida:

```
┌─────────────────┐
│  Em Construção  │ ◄─── Pedido iniciado mas não confirmado
└────────┬────────┘
         │ Atendente confirma
         ▼
┌─────────────────┐
│   Confirmado    │ ◄─── Pedido validado pelo atendente
└────────┬────────┘
         │ Sistema envia
         ▼
┌─────────────────┐
│ Enviado p/      │ ◄─── Pedido na fila da cozinha (sucesso)
│ Cozinha         │
└─────────────────┘

         OU
         
┌─────────────────┐
│ Pendente de     │ ◄─── Falha ao enviar, aguardando reenvio
│ Envio           │
└─────────────────┘
```

---

## 6. Estrutura de Dados do Pedido

### Pedido
```
{
  "numeroPedido": "042",
  "numeroProvisorio": "P123",
  "dataHoraInicio": "2025-01-15T10:30:00",
  "dataHoraConfirmacao": "2025-01-15T10:32:00",
  "atendente": {
    "id": "A001",
    "nome": "João Silva"
  },
  "status": "Enviado para Cozinha",
  "itens": [
    {
      "id": "I001",
      "nome": "X-Burger",
      "categoria": "Sanduíches",
      "quantidade": 1,
      "precoUnitario": 15.00,
      "observacoes": "Sem cebola"
    },
    {
      "id": "I002",
      "nome": "Coca-Cola 350ml",
      "categoria": "Bebidas",
      "quantidade": 1,
      "precoUnitario": 5.00,
      "observacoes": null
    }
  ],
  "valorTotal": 20.00
}
```

---

## 7. Integrações do Sistema

### 7.1 Módulo de Cardápio
- Fornece lista de categorias
- Fornece lista de produtos por categoria
- Fornece preços atualizados

### 7.2 Módulo de Autenticação
- Valida atendente logado
- Fornece dados do atendente para registro

### 7.3 Sistema da Cozinha
- Recebe pedidos em tempo real
- Confirma recebimento
- Atualiza status de preparo (futuro)

### 7.4 Módulo de Relatórios (futuro)
- Consome dados dos pedidos registrados
- Gera relatórios de vendas

---

## 8. Requisitos de Interface

### Princípios de Design
1. **Simplicidade**: Interface limpa e direta
2. **Velocidade**: Mínimo de cliques para ações comuns
3. **Clareza**: Informações visíveis e legíveis
4. **Responsividade**: Resposta imediata às ações

### Elementos Visuais
- **Botões grandes**: Fácil toque em tela touch-screen
- **Cores por categoria**: Diferenciação visual rápida
- **Fonte legível**: Tamanho adequado para leitura rápida
- **Feedback visual**: Confirmação de ações realizadas

### Navegação
- **Mínimo de níveis**: Máximo 2-3 níveis de profundidade
- **Caminho claro**: Sempre possível voltar ou cancelar
- **Estado visível**: Usuário sempre sabe onde está

---

## 9. Métricas de Sucesso

### Desempenho
- Tempo médio para registrar um pedido: < 2 minutos
- Tempo de resposta do sistema: < 2 segundos
- Taxa de disponibilidade: > 99%

### Qualidade
- Taxa de erros em pedidos: < 2%
- Taxa de cancelamentos: < 5%
- Satisfação dos atendentes: > 80%

### Eficiência
- Pedidos registrados por hora: aumento de 30%
- Redução de erros vs. papel: > 50%
- Tempo de treinamento de novos atendentes: < 1 hora

---

## 10. Cenários de Teste

### CT01 - Pedido Simples
1. Cliente pede 1 X-Burger e 1 Coca-Cola
2. Atendente registra sem observações
3. Confirma e envia para cozinha
4. **Resultado esperado**: Pedido registrado com sucesso

### CT02 - Pedido com Observações
1. Cliente pede 1 X-Burger sem cebola
2. Atendente adiciona observação
3. Confirma e envia
4. **Resultado esperado**: Observação aparece na cozinha

### CT03 - Pedido com Múltiplos Itens
1. Cliente pede 2 X-Burgers, 3 Cocas e 1 Batata Frita
2. Atendente define quantidades corretas
3. Confirma e envia
4. **Resultado esperado**: Todas quantidades corretas

### CT04 - Cancelamento
1. Atendente inicia pedido
2. Cliente desiste
3. Atendente cancela
4. **Resultado esperado**: Pedido descartado sem registro

### CT05 - Edição Durante Revisão
1. Atendente adiciona 3 itens
2. Durante revisão, cliente remove 1 item
3. Atendente remove e confirma
4. **Resultado esperado**: Pedido com 2 itens

### CT06 - Falha de Comunicação
1. Atendente confirma pedido
2. Sistema não consegue enviar para cozinha
3. Sistema alerta sobre falha
4. **Resultado esperado**: Pedido em fila de pendências

---

## 11. Glossário

- **Pedido**: Conjunto de itens solicitados por um cliente
- **Item**: Produto individual do cardápio (sanduíche, bebida, sobremesa)
- **Observação**: Personalização solicitada pelo cliente para um item
- **Categoria**: Agrupamento de produtos similares
- **Atendente**: Funcionário que opera o sistema
- **Cozinha**: Área de preparo que recebe os pedidos
- **Número do Pedido**: Identificador único do pedido
- **Status**: Estado atual do pedido no sistema
