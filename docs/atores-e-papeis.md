# Atores e Papéis - Sistema Lanchonete

## Visão Geral

Este documento descreve os atores que interagem com o sistema da lanchonete, seus papéis, responsabilidades e interações no contexto do caso de uso "Registrar Pedido".

---

## 1. Cliente

### Descrição
Pessoa que deseja fazer um pedido na lanchonete universitária.

### Características
- Pode ser estudante, professor ou funcionário da universidade
- Pode ser cliente eventual ou frequente
- Geralmente tem pressa (horário de intervalo limitado)
- Espera atendimento rápido e preciso

### Responsabilidades no Processo de Registro de Pedido

1. **Consultar o cardápio**
   - Visualiza o cardápio impresso disponível no estabelecimento
   - Identifica os produtos disponíveis e seus preços

2. **Decidir o pedido**
   - Escolhe os itens que deseja pedir
   - Define quantidades desejadas
   - Pensa em personalizações (observações)

3. **Comunicar o pedido ao atendente**
   - Informa claramente os itens desejados
   - Especifica quantidades se diferente de 1
   - Comunica observações especiais (ex: "sem cebola")

4. **Confirmar o pedido**
   - Revisa o pedido quando o atendente apresenta
   - Confirma que está correto ou solicita ajustes
   - Aceita ou desiste do pedido

5. **Receber número do pedido**
   - Memoriza ou anota o número do pedido
   - Aguarda ser chamado para retirada

### Expectativas
- Atendimento rápido (máximo 3-5 minutos)
- Pedido registrado sem erros
- Comunicação clara do número do pedido
- Preparo em tempo razoável

### Interação com o Sistema
- **Indireta**: O cliente não usa o sistema diretamente
- **Mediada**: Toda interação é feita através do atendente

---

## 2. Atendente

### Descrição
Funcionário da lanchonete responsável por atender clientes, registrar pedidos e coordenar o fluxo de atendimento.

### Características
- Funcionário treinado para usar o sistema
- Familiarizado com o cardápio e produtos
- Trabalha sob pressão em horários de pico
- Precisa ser eficiente e cortês simultaneamente

### Responsabilidades no Processo de Registro de Pedido

1. **Receber o cliente**
   - Cumprimentar o cliente
   - Estar disponível para tirar dúvidas sobre o cardápio

2. **Ouvir o pedido**
   - Prestar atenção aos itens solicitados
   - Fazer perguntas clarificadoras quando necessário
   - Anotar mentalmente ou registrar no sistema

3. **Operar o sistema**
   - Fazer login no sistema
   - Iniciar um novo pedido
   - Navegar pelas categorias do cardápio
   - Adicionar itens ao pedido
   - Definir quantidades
   - Registrar observações especiais

4. **Validar o pedido com o cliente**
   - Revisar os itens adicionados
   - Confirmar valores e quantidades
   - Fazer ajustes se necessário

5. **Confirmar e enviar o pedido**
   - Confirmar o pedido no sistema
   - Enviar para a cozinha
   - Informar o número do pedido ao cliente

6. **Lidar com problemas**
   - Cancelar pedidos quando cliente desiste
   - Informar sobre itens indisponíveis
   - Lidar com falhas do sistema

### Competências Necessárias
- **Técnicas**: Saber operar o sistema, digitar rapidamente
- **Interpessoais**: Comunicação clara, paciência, cortesia
- **Organizacionais**: Gerenciar múltiplos clientes, priorizar tarefas
- **Resolução de problemas**: Lidar com situações inesperadas

### Interação com o Sistema
- **Direta e constante**: Principal usuário do sistema
- **Múltiplas sessões**: Registra vários pedidos por hora
- **Necessita**: Interface rápida, intuitiva e confiável

### Autorização e Acesso
- Login obrigatório com usuário e senha
- Permissões:
  - ✅ Criar novos pedidos
  - ✅ Editar pedidos em construção
  - ✅ Cancelar pedidos não confirmados
  - ✅ Confirmar e enviar pedidos
  - ❌ Não pode editar pedidos já enviados
  - ❌ Não pode acessar relatórios gerenciais

---

## 3. Cozinha (Equipe de Preparo)

### Descrição
Equipe responsável por preparar os pedidos registrados no sistema.

### Características
- Trabalha na área de preparo (separada do atendimento)
- Recebe pedidos em tempo real via sistema
- Organiza a ordem de preparo
- Precisa entender claramente o que preparar

### Responsabilidades no Processo de Registro de Pedido

1. **Receber pedidos**
   - Monitora o sistema/display de pedidos
   - Identifica novos pedidos que chegam

2. **Interpretar pedidos**
   - Lê os itens solicitados
   - Verifica quantidades
   - Observa as observações especiais

3. **Organizar produção**
   - Define ordem de preparo
   - Prioriza conforme demanda
   - Gerencia tempo de preparo

4. **Preparar itens**
   - Prepara os produtos conforme especificações
   - Segue as observações do cliente
   - Garante qualidade

5. **Notificar conclusão** (não abordado neste caso de uso)
   - Informa quando pedido está pronto
   - Sistema notifica atendente/cliente

### Expectativas
- Receber pedidos claros e legíveis
- Observações visíveis e destacadas
- Sistema em tempo real (sem atrasos)
- Organização por ordem de chegada ou prioridade

### Interação com o Sistema
- **Receptora**: Recebe dados mas não envia
- **Consulta**: Visualiza fila de pedidos
- **Display dedicado**: Pode ter terminal específico

### Autorização e Acesso
- Sistema pode ser view-only para cozinha
- Permissões:
  - ✅ Visualizar pedidos recebidos
  - ✅ Marcar pedidos como "em preparo" (futuro)
  - ✅ Marcar pedidos como "prontos" (futuro)
  - ❌ Não pode criar pedidos
  - ❌ Não pode cancelar pedidos confirmados

---

## 4. Gerente (Papel Secundário neste Caso de Uso)

### Descrição
Responsável pela gestão da lanchonete, incluindo análise de vendas e controle operacional.

### Características
- Supervisiona operações
- Toma decisões estratégicas
- Monitora desempenho
- Planeja cardápio e estoque

### Responsabilidades Relacionadas ao Registro de Pedido

1. **Monitorar operações**
   - Acompanha volume de pedidos
   - Identifica horários de pico

2. **Analisar dados**
   - Consulta relatórios de vendas
   - Identifica produtos mais vendidos
   - Analisa desempenho dos atendentes

3. **Tomar decisões**
   - Ajusta cardápio conforme demanda
   - Planeja escalas de atendimento
   - Define metas de atendimento

### Interação com o Sistema no Contexto de Pedidos
- **Indireta**: Não registra pedidos
- **Analítica**: Usa dados gerados pelos pedidos
- **Configuração**: Pode ajustar parâmetros do sistema

### Autorização e Acesso
- Acesso amplo ao sistema
- Permissões:
  - ✅ Visualizar todos os pedidos
  - ✅ Acessar relatórios e estatísticas
  - ✅ Configurar cardápio
  - ✅ Gerenciar usuários (atendentes)
  - ✅ Visualizar histórico completo

---

## 5. Matriz de Interações - Caso de Uso "Registrar Pedido"

| Ator | Interage com Sistema | Interage com Cliente | Interage com Atendente | Interage com Cozinha |
|------|---------------------|---------------------|------------------------|----------------------|
| **Cliente** | ❌ Não | - | ✅ Sim | ❌ Não |
| **Atendente** | ✅✅✅ Direto | ✅ Sim | - | 🔄 Via Sistema |
| **Cozinha** | 👁️ Visualiza | ❌ Não | 🔄 Via Sistema | - |
| **Gerente** | 📊 Consulta | ❌ Não | 👥 Supervisiona | 👥 Supervisiona |

**Legenda:**
- ✅ Interação direta
- ❌ Sem interação
- 🔄 Interação mediada pelo sistema
- 👁️ Visualização/leitura
- 📊 Análise de dados
- 👥 Supervisão

---

## 6. Fluxo de Comunicação

```
Cliente ──[verbal]──► Atendente ──[sistema]──► Sistema ──[rede]──► Cozinha
   ▲                      │                                              │
   │                      └──[verbal]──► Cliente                        │
   │                                                                     │
   └─────────────────────[espera/chamado]───────────────────────────────┘
```

---

## 7. Cenários por Ator

### 7.1 Cenário: Cliente Regular
**Contexto**: Maria é estudante e almoça na lanchonete 3x por semana

**Comportamento típico:**
1. Já conhece o cardápio, decide rápido
2. Pede sempre "X-Burger sem tomate e uma Coca"
3. Paga e aguarda o número ser chamado
4. Espera um atendimento rápido (3-4 minutos)

**Impacto no sistema:**
- Necessita ser rápido (cliente regular tem expectativa de agilidade)
- Observações devem ser fáceis de registrar
- Histórico de pedidos poderia agilizar (feature futura)

### 7.2 Cenário: Atendente em Horário de Pico
**Contexto**: João é atendente no horário do almoço (12h-13h)

**Situação típica:**
1. Fila de 10-15 clientes aguardando
2. Precisa registrar 1 pedido a cada 2-3 minutos
3. Clientes impacientes
4. Sistema não pode travar ou ser lento

**Necessidades:**
- Interface ultra-rápida
- Mínimo de cliques
- Feedback visual claro
- Sistema confiável

### 7.3 Cenário: Cozinha com Múltiplos Pedidos
**Contexto**: Equipe da cozinha com 5 pedidos simultâneos

**Situação típica:**
1. Recebe pedido #042 com 2 X-Burgers
2. Já está preparando pedidos #038, #039, #040, #041
3. Precisa organizar prioridades
4. Observações especiais precisam estar destacadas

**Necessidades:**
- Display claro com fila de pedidos
- Observações em destaque
- Indicação de tempo de espera
- Capacidade de marcar "em preparo"

---

## 8. Perfil de Usuários do Sistema

### Perfil: Atendente Iniciante
- **Experiência com tecnologia**: Básica
- **Tempo de uso do sistema**: < 1 semana
- **Velocidade**: Lenta (4-5 minutos/pedido)
- **Necessidades**: Tutorial, ajuda contextual, confirmações

### Perfil: Atendente Experiente
- **Experiência com tecnologia**: Intermediária
- **Tempo de uso do sistema**: > 1 mês
- **Velocidade**: Rápida (1-2 minutos/pedido)
- **Necessidades**: Atalhos, múltiplas janelas, eficiência

### Perfil: Cozinheiro
- **Experiência com tecnologia**: Básica
- **Uso do sistema**: Apenas visualização
- **Necessidades**: Display grande, informações claras, mínima interação

---

## 9. Responsabilidades Cruzadas

### Garantir Qualidade do Pedido

| Responsável | Ação |
|------------|------|
| **Cliente** | Comunicar claramente o pedido |
| **Atendente** | Registrar corretamente no sistema |
| **Sistema** | Validar dados e enviar corretamente |
| **Cozinha** | Interpretar e preparar conforme especificado |

### Garantir Velocidade do Atendimento

| Responsável | Ação |
|------------|------|
| **Cliente** | Decidir rapidamente |
| **Atendente** | Operar o sistema eficientemente |
| **Sistema** | Responder em < 2 segundos |
| **Cozinha** | Organizar preparo eficientemente |

---

## 10. Considerações de Acessibilidade

### Para Atendentes
- Interface deve ser clara para uso prolongado
- Evitar fadiga visual (cores adequadas, contraste)
- Possibilidade de usar atalhos de teclado
- Suporte a diferentes dispositivos (tablet, desktop)

### Para Cozinha
- Display visível de longe
- Fonte grande e legível
- Cores para diferenciar prioridades
- Alertas sonoros para novos pedidos

### Para Clientes com Necessidades Especiais
- Atendente deve poder registrar observações detalhadas
- Sistema deve suportar alergias e restrições alimentares (futuro)
- Possibilidade de imprimir pedido em texto grande (futuro)
