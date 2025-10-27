# Sistema de Registro de Pedidos - Documentação Completa

## Índice de Documentação

Este documento serve como índice para toda a documentação do caso de uso "Registrar Pedido" do sistema da Lanchonete Universitária.

---

## 📋 Documentos Disponíveis

### 1. [Casos de Uso Essenciais](./casos-de-uso-essenciais.md)
**Descrição**: Visão resumida do caso de uso UC01 - Registrar Pedido em formato Cockburn

**Conteúdo:**
- Identificação de atores e partes interessadas
- Pré-condições e pós-condições
- Cenário de sucesso principal
- Fluxos alternativos (extensões)
- Requisitos especiais
- Frequência de ocorrência

**Público-alvo**: Equipe de desenvolvimento, stakeholders, cliente

---

### 2. [Caso de Uso Expandido - Registrar Pedido](./caso-de-uso-expandido-registrar-pedido.md)
**Descrição**: Especificação detalhada e completa do caso de uso UC01

**Conteúdo:**
- Descrição completa do caso de uso
- Tabela detalhada do fluxo principal
- 7 fluxos alternativos documentados
- 2 fluxos de exceção (erros)
- Requisitos especiais detalhados
- Protótipos de interface em ASCII
- 5 questões em aberto para discussão com cliente

**Público-alvo**: Desenvolvedores, designers de interface, testadores

---

### 3. [Backlog - Histórias de Usuário](./backlog-historias-usuario.md)
**Descrição**: Product backlog com histórias de usuário para implementação

**Conteúdo:**
- 13 User Stories completas com critérios de aceitação
- Estimativas em story points
- Planejamento de 2 sprints
- Definição de Pronto (Definition of Done)
- Priorização das histórias

**Histórias incluídas:**
- US01: Iniciar Novo Pedido
- US02: Adicionar Item ao Pedido
- US03: Definir Quantidade de Item
- US04: Adicionar Observações ao Item
- US05: Revisar Pedido
- US06: Editar Item do Pedido
- US07: Confirmar Pedido
- US08: Enviar Pedido para Cozinha
- US09: Cancelar Pedido em Andamento
- US10: Informar Número do Pedido ao Cliente
- US11: Visualizar Categorias do Cardápio
- US12: Tratamento de Erro de Comunicação
- US13: Registro de Auditoria

**Público-alvo**: Product Owner, Scrum Master, equipe de desenvolvimento

---

### 4. [Fluxo do Sistema - Registrar Pedido](./fluxo-sistema-registrar-pedido.md)
**Descrição**: Diagramas e fluxos detalhados do processo de registro de pedidos

**Conteúdo:**
- Diagrama de contexto do sistema
- Fluxo detalhado em 5 fases
- 4 fluxos alternativos ilustrados
- Estados do pedido
- Estrutura de dados (JSON)
- Integrações do sistema
- Requisitos de interface
- Métricas de sucesso
- 6 cenários de teste
- Glossário de termos

**Público-alvo**: Arquitetos de sistema, desenvolvedores, analistas de negócio

---

### 5. [Atores e Papéis](./atores-e-papeis.md)
**Descrição**: Descrição detalhada de todos os atores do sistema

**Conteúdo:**
- 4 atores principais: Cliente, Atendente, Cozinha, Gerente
- Responsabilidades de cada ator
- Características e expectativas
- Interações entre atores
- Matriz de interações
- Cenários por ator
- Perfis de usuário
- Considerações de acessibilidade

**Público-alvo**: Designers de UX, gerentes de produto, equipe de treinamento

---

## 🎯 Visão Geral do Sistema

### Problema
A Lanchonete Universitária atualmente registra pedidos em papel, causando:
- Erros no registro de pedidos
- Demora no processo de atendimento
- Falta de controle e rastreabilidade
- Dificuldade de comunicação com a cozinha

### Solução Proposta
Sistema informatizado que permite:
1. Atendente registra pedidos digitalmente
2. Seleção de produtos do cardápio por categorias
3. Envio automático para a cozinha
4. Rastreamento de pedidos por número
5. Base para relatórios gerenciais futuros

### Escopo Inicial (Sprint 1 e 2)
- ✅ Registro de pedidos
- ✅ Gerenciamento de itens do pedido
- ✅ Envio para cozinha
- ✅ Tratamento de erros básico
- ❌ Pagamento (fase futura)
- ❌ Controle de status de preparo (fase futura)
- ❌ Notificação ao cliente (fase futura)
- ❌ Relatórios (fase futura)

---

## 📊 Planejamento de Sprints

### Sprint 1 - Core do Sistema (36 pontos)
**Duração**: 2 semanas  
**Objetivo**: Implementar funcionalidade básica de registro de pedidos

**Entregas:**
- Interface de novo pedido
- Seleção de itens por categoria
- Gerenciamento de quantidades e observações
- Revisão e edição de pedidos
- Confirmação e envio para cozinha
- Display básico para cozinha

**Critério de Sucesso:**
- Atendente consegue registrar um pedido completo
- Pedido aparece na tela da cozinha
- Sistema responde em < 2 segundos

---

### Sprint 2 - Robustez e Qualidade (8 pontos)
**Duração**: 1 semana  
**Objetivo**: Adicionar tratamento de erros e auditoria

**Entregas:**
- Tratamento de falhas de comunicação
- Fila de pedidos pendentes
- Registro de auditoria (quem, quando)
- Melhorias de usabilidade baseadas em feedback

**Critério de Sucesso:**
- Sistema não perde pedidos em caso de falha
- Possível rastrear quem registrou cada pedido
- Interface refinada após testes com usuários

---

## 🔄 Processo de Desenvolvimento

### Metodologia
- **Scrum**: Sprints de 1-2 semanas
- **Prototipação em papel**: Telas desenhadas e validadas
- **Feedback contínuo**: Cliente (professor) valida cada sprint
- **Iterativo**: Melhorias baseadas em feedback

### Artefatos
1. ✅ Product Backlog (histórias de usuário)
2. ✅ Sprint Backlog (tarefas da sprint)
3. ✅ Casos de uso (essenciais e expandidos)
4. ✅ Protótipos de interface
5. 📋 Sprint Review (apresentação ao cliente)
6. 📋 Sprint Retrospective (melhoria contínua)

### Ferramentas
- **GitHub Projects**: Kanban (Backlog, ToDo, Doing, Review, Done)
- **Papel e caneta**: Protótipos de interface
- **Documentação em Markdown**: Casos de uso e especificações

---

## 👥 Papéis do Projeto

### Product Owner
- Define prioridades do backlog
- Valida entregas
- Representa os interesses do cliente

### Scrum Master
- Facilita as cerimônias Scrum
- Remove impedimentos
- Garante que o processo está sendo seguido

### Time de Desenvolvimento
- Estima histórias
- Implementa funcionalidades
- Testa e valida entregas

### Stakeholders
- Cliente (dono da lanchonete)
- Usuários finais (atendentes, cozinha)
- Professor (validador acadêmico)

---

## 📈 Métricas de Acompanhamento

### Velocidade do Time
- Story points completados por sprint
- Meta: 30-40 pontos/sprint

### Qualidade
- Bugs encontrados por sprint
- Histórias retrabalhadas
- Meta: < 10% de retrabalho

### Satisfação do Cliente
- Feedback nas Sprint Reviews
- Aceitação das entregas
- Meta: Todas histórias aceitas

---

## 🎨 Padrões de Interface

### Visual
- **Cores**: Verde para confirmar, vermelho para cancelar, azul para neutro
- **Botões**: Grandes (mín. 60x60px) para touch-screen
- **Fonte**: Sans-serif, tamanho 14-16pt
- **Espaçamento**: Generoso, evitar elementos muito próximos

### Interação
- **Confirmações**: Para ações destrutivas (cancelar, remover)
- **Feedback**: Visual imediato para toda ação
- **Navegação**: Breadcrumbs ou indicador de posição
- **Erros**: Mensagens claras e acionáveis

### Responsividade
- Tablet (landscape): Layout principal
- Desktop: Layout expandido
- Mobile (portrait): Versão simplificada (futuro)

---

## 🧪 Estratégia de Testes

### Testes de Usabilidade
1. **Teste com papel**: Protótipos em papel com usuários reais
2. **Teste de tarefas**: Usuários executam cenários típicos
3. **Observação**: Identificar pontos de confusão
4. **Feedback**: Ajustar interface antes de implementar

### Testes Funcionais
1. **Cenários de sucesso**: Pedido completo registrado
2. **Cenários alternativos**: Edições, cancelamentos
3. **Cenários de erro**: Falhas de comunicação
4. **Testes de carga**: Múltiplos pedidos simultâneos

### Critérios de Aceitação
- Todos os critérios das User Stories atendidos
- Casos de uso executados com sucesso
- Interface aprovada pelos usuários finais
- Performance dentro dos requisitos (< 2s resposta)

---

## 📝 Como Usar Esta Documentação

### Para Desenvolvedores
1. Leia o **Caso de Uso Expandido** para entender requisitos detalhados
2. Consulte o **Backlog** para ver as histórias da sua sprint
3. Use o **Fluxo do Sistema** para entender integrações
4. Revise **Atores e Papéis** para entender contexto de uso

### Para Designers
1. Estude **Atores e Papéis** para entender usuários
2. Consulte **Protótipos** no Caso de Uso Expandido
3. Revise **Requisitos de Interface** no Fluxo do Sistema
4. Valide designs contra **Cenários de Teste**

### Para Testadores
1. Use **Cenários de Teste** no Fluxo do Sistema
2. Valide **Critérios de Aceitação** das User Stories
3. Execute todos os **Fluxos Alternativos** do Caso de Uso
4. Teste **Fluxos de Exceção** para robustez

### Para Product Owner
1. Priorize usando o **Backlog**
2. Valide entregas contra **Casos de Uso**
3. Use **Métricas** para acompanhar progresso
4. Apresente **Protótipos** ao cliente

---

## 🔍 Questões em Aberto

Questões que precisam ser discutidas com o cliente:

1. **Limite de itens por pedido**: Existe algum máximo?
2. **Pedidos para viagem**: Sistema deve diferenciar?
3. **Impressão de comprovante**: Automática ou sob demanda?
4. **Numeração de pedidos**: Sequencial único ou reset diário?
5. **Cancelamento após envio**: Cozinha pode recusar pedidos?
6. **Priorização de pedidos**: FIFO ou pode haver prioridades?
7. **Múltiplos atendentes**: Sistema suporta quantos simultâneos?
8. **Integração com pagamento**: Quando será implementada?

---

## 📚 Referências

### Padrão de Documentação
- Alistair Cockburn - Writing Effective Use Cases
- IEEE 830 - Software Requirements Specification

### Metodologia Ágil
- Scrum Guide
- User Story Mapping - Jeff Patton

### Design de Interface
- Don Norman - The Design of Everyday Things
- Jakob Nielsen - Usability Heuristics

---

## 📞 Contatos do Projeto

*(Preencher com informações reais da equipe)*

- **Product Owner**: [Nome]
- **Scrum Master**: [Nome]
- **Equipe de Desenvolvimento**: [Nomes]
- **Cliente**: Lanchonete Universitária

---

## 📅 Histórico de Versões

| Versão | Data | Autor | Descrição |
|--------|------|-------|-----------|
| 1.0 | 2025-01-15 | Equipe | Versão inicial - Sprint 1 Planning |

---

## ✅ Status da Documentação

- [x] Casos de Uso Essenciais - Completo
- [x] Caso de Uso Expandido - Completo
- [x] Backlog com User Stories - Completo
- [x] Fluxo do Sistema - Completo
- [x] Atores e Papéis - Completo
- [x] Índice e Visão Geral - Completo
- [ ] Sprint Planning Detalhado - Pendente
- [ ] Protótipos em Alta Fidelidade - Pendente
- [ ] Plano de Testes Detalhado - Pendente

---

**Última atualização**: Janeiro 2025  
**Status do Projeto**: Em planejamento - Pronto para Sprint 1
