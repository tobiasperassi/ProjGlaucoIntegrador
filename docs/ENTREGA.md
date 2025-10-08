# 📦 Entrega do Projeto - Registrar Pedido

## ✅ Status: COMPLETO

**Data de Entrega:** Janeiro 2025  
**Caso de Uso:** UC01 - Registrar Pedido  
**Issue:** #1 - Registrar Pedido

---

## 📋 Resumo Executivo

Este projeto documenta completamente o caso de uso "Registrar Pedido" para o sistema da Lanchonete Universitária, incluindo todos os artefatos necessários para as duas sprints de desenvolvimento.

### Problema Resolvido
O sistema permite que atendentes registrem pedidos digitalmente, substituindo o processo manual em papel, reduzindo erros e aumentando a eficiência do atendimento.

### Atores Principais
1. **Cliente** - Faz o pedido
2. **Atendente** - Registra no sistema
3. **Cozinha** - Recebe e prepara

---

## 📚 Documentação Entregue

### 1. Casos de Uso Essenciais ✅
- **Arquivo:** `casos-de-uso-essenciais.md`
- **Tamanho:** 2.1 KB (63 linhas)
- **Conteúdo:**
  - UC01 completo em formato Cockburn
  - Cenário principal com 9 passos
  - 3 extensões (fluxos alternativos)
  - Requisitos especiais

### 2. Caso de Uso Expandido ✅
- **Arquivo:** `caso-de-uso-expandido-registrar-pedido.md`
- **Tamanho:** 11.4 KB (453 linhas)
- **Conteúdo:**
  - Fluxo principal detalhado (17 passos)
  - 7 fluxos alternativos documentados
  - 2 fluxos de exceção
  - 3 protótipos de interface em ASCII
  - 5 questões em aberto
  - Requisitos de desempenho e segurança

### 3. Backlog e Histórias de Usuário ✅
- **Arquivo:** `backlog-historias-usuario.md`
- **Tamanho:** 9.1 KB (366 linhas)
- **Conteúdo:**
  - 13 User Stories completas
  - Critérios de aceitação para cada história
  - Estimativas em story points
  - Planejamento de 2 sprints
  - Definition of Done

**Distribuição das Sprints:**
- **Sprint 1:** 11 histórias (36 pontos) - Core do sistema
- **Sprint 2:** 2 histórias (8 pontos) - Robustez

### 4. Fluxo do Sistema ✅
- **Arquivo:** `fluxo-sistema-registrar-pedido.md`
- **Tamanho:** 12 KB (432 linhas)
- **Conteúdo:**
  - Diagrama de contexto
  - Fluxo detalhado em 5 fases (23 passos)
  - 4 fluxos alternativos ilustrados
  - Estrutura de dados (JSON)
  - 6 cenários de teste
  - Métricas de sucesso
  - Glossário completo

### 5. Atores e Papéis ✅
- **Arquivo:** `atores-e-papeis.md`
- **Tamanho:** 10.9 KB (456 linhas)
- **Conteúdo:**
  - 4 atores detalhados (Cliente, Atendente, Cozinha, Gerente)
  - Responsabilidades de cada ator
  - Matriz de interações
  - 3 cenários por ator
  - Perfis de usuário
  - Considerações de acessibilidade

### 6. README e Índice ✅
- **Arquivo:** `README.md`
- **Tamanho:** 10.6 KB (385 linhas)
- **Conteúdo:**
  - Índice de toda documentação
  - Visão geral do sistema
  - Guia de uso da documentação
  - Planejamento de sprints
  - Processo de desenvolvimento
  - Estratégia de testes

---

## 📊 Estatísticas da Documentação

| Métrica | Valor |
|---------|-------|
| **Total de arquivos** | 6 documentos |
| **Total de linhas** | 1.795 linhas |
| **Total de texto** | ~56 KB |
| **User Stories** | 13 histórias |
| **Story Points** | 44 pontos (2 sprints) |
| **Fluxos documentados** | 10 fluxos (1 principal + 7 alternativos + 2 exceções) |
| **Cenários de teste** | 6 cenários |
| **Atores** | 4 atores detalhados |
| **Protótipos** | 3 telas em ASCII |

---

## 🎯 Histórias de Usuário (Resumo)

### Epic: Registrar Pedido

#### Sprint 1 - Core (36 pontos)
1. **US01** - Iniciar Novo Pedido (3 pts)
2. **US02** - Adicionar Item ao Pedido (5 pts)
3. **US03** - Definir Quantidade de Item (3 pts)
4. **US04** - Adicionar Observações ao Item (3 pts)
5. **US05** - Revisar Pedido (2 pts)
6. **US06** - Editar Item do Pedido (5 pts)
7. **US07** - Confirmar Pedido (3 pts)
8. **US08** - Enviar Pedido para Cozinha (5 pts)
9. **US09** - Cancelar Pedido em Andamento (2 pts)
10. **US10** - Informar Número do Pedido ao Cliente (2 pts)
11. **US11** - Visualizar Categorias do Cardápio (3 pts)

#### Sprint 2 - Robustez (8 pontos)
12. **US12** - Tratamento de Erro de Comunicação (5 pts)
13. **US13** - Registro de Auditoria (3 pts)

---

## 🔄 Fluxos Principais Documentados

### Fluxo Básico (Sucesso)
```
Cliente → Consulta Cardápio
       → Informa Pedido → Atendente → Registra no Sistema
                                    → Sistema envia → Cozinha
Cliente ← Recebe Número ← Atendente ← Sistema confirma
```

### Fluxos Alternativos
1. Cliente desiste do pedido
2. Item não está disponível
3. Cliente adiciona observações
4. Cliente lembra de mais itens durante revisão
5. Cliente deseja remover item
6. Cliente deseja alterar quantidade
7. Falha de comunicação com cozinha

---

## 🎨 Protótipos de Interface

Três telas foram prototipadas em formato ASCII:

1. **Tela: Novo Pedido** (vazio)
   - Layout básico com categorias
   - Área para lista de itens
   - Botões de ação

2. **Tela: Pedido com Itens**
   - Lista de itens adicionados
   - Quantidades e observações
   - Valor total calculado

3. **Tela: Confirmação**
   - Número do pedido em destaque
   - Mensagem de sucesso
   - Opção de imprimir

---

## ✅ Critérios de Aceitação Globais

- [x] Documentação segue padrões reconhecidos (Cockburn, IEEE)
- [x] Todos os atores estão identificados e descritos
- [x] Fluxo principal está completo e detalhado
- [x] Fluxos alternativos cobrem cenários importantes
- [x] Exceções e erros estão documentados
- [x] User Stories têm critérios de aceitação
- [x] Estimativas de story points fornecidas
- [x] Sprints planejadas com objetivos claros
- [x] Protótipos de interface disponíveis
- [x] Cenários de teste definidos

---

## 🚀 Próximos Passos Sugeridos

### Fase 1: Validação (Semana 1)
1. Revisar documentação com stakeholders
2. Validar protótipos com atendentes reais
3. Resolver questões em aberto com cliente
4. Ajustar requisitos se necessário

### Fase 2: Implementação Sprint 1 (Semanas 2-3)
1. Setup do ambiente de desenvolvimento
2. Implementar histórias US01-US11
3. Testes funcionais e de usabilidade
4. Sprint Review com cliente

### Fase 3: Implementação Sprint 2 (Semana 4)
1. Implementar US12-US13
2. Testes de robustez e erro
3. Refinamentos de interface
4. Sprint Review final

### Fase 4: Entrega (Semana 5)
1. Apresentação ao cliente (professor)
2. Demonstração do sistema funcionando
3. Entrega da documentação final
4. Retrospectiva do projeto

---

## 📝 Questões Pendentes para o Cliente

As seguintes questões precisam ser discutidas:

1. **Limite de itens por pedido**: Existe algum máximo?
2. **Pedidos para viagem**: Deve haver diferenciação?
3. **Impressão de comprovante**: Automática ou manual?
4. **Numeração de pedidos**: Sequencial ou reset diário?
5. **Cancelamento pós-envio**: Cozinha pode recusar?

---

## 🎓 Aprendizados do Projeto

### Técnicos
- Documentação de casos de uso em formato padrão
- Criação de user stories com critérios claros
- Planejamento de sprints
- Prototipação de interfaces

### Processo
- Metodologia ágil (Scrum)
- Iteração com feedback do cliente
- Priorização de funcionalidades
- Estimativa de esforço

### Negócio
- Compreensão do domínio de lanchonetes
- Identificação de atores e papéis
- Análise de fluxos de trabalho
- Requisitos não-funcionais

---

## 👥 Equipe

**Desenvolvido para:**
- Lanchonete Universitária
- Professor (Cliente/Validador)

**Metodologia:**
- Scrum
- Documentação ágil
- Prototipação em papel

---

## 📞 Suporte

Para dúvidas sobre a documentação:
1. Consulte o `docs/README.md` para índice completo
2. Cada documento tem seção específica
3. Glossário disponível em `fluxo-sistema-registrar-pedido.md`

---

## 🏆 Conclusão

A documentação completa do caso de uso "Registrar Pedido" foi entregue com sucesso, incluindo:

✅ Casos de uso (essencial e expandido)  
✅ 13 histórias de usuário com critérios  
✅ Planejamento de 2 sprints  
✅ Fluxos detalhados do sistema  
✅ Documentação de atores e papéis  
✅ Protótipos de interface  
✅ Cenários de teste  

**O projeto está pronto para iniciar a fase de implementação!**

---

*Última atualização: Janeiro 2025*  
*Versão: 1.0*
