# 🤖 PRD: Assistente Financeiro Conversacional (MVP)

> **Visão do Produto:** Uma experiência conversacional onde o usuário registra gastos em linguagem natural, recebe classificação automática, metas e um Agente Financeiro que propõe planos de economia personalizados e automatizados. A abordagem segue a ideia de *Vibe Coding*: descrever intenções em linguagem natural e deixar agentes de IA cuidarem da execução técnica e automações.

---

## 📖 Contexto
Criar um aplicativo de Organização de Finanças Pessoais que funcione por conversa natural com agentes de IA, reduzindo a entrada manual de dados e tornando o controle financeiro acessível a iniciantes.

## 🎯 O Problema e Hipótese de Valor

### Problema
Usuários desistem de manter o controle financeiro porque os aplicativos atuais exigem muito input manual, configuração complexa e oferecem pouca personalização.

### Hipótese de Valor
**Se** oferecermos um fluxo conversacional simples que registra transações automaticamente, classifica gastos e entrega planos de economia acionáveis, **então** os iniciantes manterão o controle financeiro por mais tempo e alcançarão suas metas com menos esforço.

---

## 👥 Público-Alvo e Métricas de Sucesso

### Público-Alvo
* Iniciantes em controle financeiro.
* Pessoas que preferem interações dinâmicas por chat.
* Usuários com pouco tempo ou paciência para configurar orçamentos complexos.

### Métricas Iniciais de Sucesso (MVP)
* **Adoção:** % de novos usuários que completam 3 registros via chat na primeira semana.
* **Retenção:** Retenção semanal de usuários após 14 dias de uso.
* **Engajamento do Agente:** % de usuários que aceitam ao menos 1 sugestão de economia.
* **Precisão de Classificação:** Acurácia automática das categorias ≥ 85% no conjunto de validação.

---

## ⚙️ Recursos Necessários

### 💻 Back-end
* **NLP/LLM:** Para interpretação de linguagem natural e geração de respostas.
* **Motor de Classificação:** ML supervisionado + regras lógicas para categorização de transações.
* **Orquestrador de Automações:** Para executar planos (agendamento, notificações, transferências simuladas).
* **Integração Bancária (Opcional):** Via APIs de Open Banking.
* **Banco de Dados:** Para armazenar transações, metas e histórico de conversas.

### 📱 Front-end
* Interface de chat responsiva e fluida.
* Componentes de visualização simples (ex: gráficos de tendência enxutos).
* Fluxos guiados de onboarding e aceitação de planos financeiros.

### 🧠 Dados e Machine Learning (ML)
* Conjunto inicial de categorias e exemplos de frases anotadas.
* Pipeline de feedback para melhorar a classificação com base nas correções feitas pelo usuário.

### 👥 Equipe Mínima Sugerida
* 1 Product Manager
* 1 Designer UX/UI (com foco em interfaces conversacionais)
* 1 Engenheiro(a) de Front-end
* 1 Engenheiro(a) de Back-end
* 1 Engenheiro(a) de ML (foco em NLP e classificação)
* 1 QA / Analista de Dados (para validação de métricas)

---

## 🔒 Requisitos Legais e de Segurança
* Criptografia rigorosa de dados (em trânsito e em repouso).
* Conformidade total com a **LGPD**.
* Políticas claras e transparentes sobre o uso de dados financeiros e modelos de IA.

---

## 🤖 A Experiência do Agente (Vibe Coding)

### Comportamento do Agente Financeiro
* **Entrada Natural:** Aceita frases informais como *"almocei R$ 35 no centro"* e as transforma em transações estruturadas.
* **Confirmação Curta:** O agente confirma a categoria detectada de forma concisa e só faz perguntas quando está incerto.
* **Proatividade:** Sugere metas e micro-ações (ex.: *"Que tal reduzir R$ 50 de delivery por semana?"*) acompanhadas de uma justificativa simples.
* **Automação:** O usuário pode aceitar que o agente crie regras automáticas (ex.: *"Quando eu gastar mais de R$ 200 em restaurante, me mande um aviso"*).

> **💡 Notas sobre Vibe Coding:**
> Esta abordagem permite que Product Owners e Designers descrevam fluxos e intenções em linguagem natural. Agentes de IA (como Lovable, Cursor, etc.) cuidam de gerar e ajustar as regras e automações no código, acelerando drasticamente o desenvolvimento e as iterações do produto.

---

## 🧪 Plano de Validação Inicial

### 1. Teste de Conceito Conversacional (5 a 10 usuários)
* **Objetivo:** Validar se os usuários conseguem registrar gastos via chat intuitivamente, sem precisar de um tutorial.
* **Métrica:** % de usuários que registram 5 transações em 3 dias.

### 2. Teste de Classificação Automática (50 a 200 transações)
* **Objetivo:** Medir a acurácia inicial do classificador e coletar dados de correções manuais.
* **Métrica:** Acurácia inicial e taxa de correção pelo usuário.

### 3. Teste de Aceitação do Agente (Teste A/B)
* **Grupo A:** Recebe sugestões proativas do agente.
* **Grupo B:** Usa apenas o chat passivo (só responde quando acionado).
* **Métrica:** Taxa de aceitação de sugestões e impacto na mudança do gasto médio.

### 4. Teste de Usabilidade do Fluxo de Metas
* **Objetivo:** Medir se os usuários entendem e engajam com os planos de economia propostos.
* **Métrica:** % de usuários que criam uma meta e seguem o plano por 14 dias.

### 🏆 Critério de Sucesso para Avançar
* Atingir pelo menos **60% de aceitação** das sugestões do agente entre os usuários ativos.
* Manter uma **retenção semanal ≥ 25%** após os primeiros 14 dias de uso.

---

## ⚠️ Riscos e Mitigações

| Risco | Estratégia de Mitigação |
| :--- | :--- |
| **Desconfiança nas Automações** | Oferecer explicações claras para cada ação da IA e garantir que o usuário tenha controle total e reversível sobre qualquer regra criada. |
| **Erros de Classificação (IA)** | Permitir que o usuário corrija a categoria com um clique, utilizando esse input para retreinar e refinar o modelo. |
| **Privacidade / Open Banking** | Tratar a integração bancária estritamente como um recurso **opcional** ("opt-in"). O core do app deve funcionar perfeitamente apenas com input manual/texto. |
| **Alucinação / Dependência de LLM** | Implementar regras de fallback baseadas em código tradicional (rule-based) para cálculos críticos e manter um log de decisões do agente para auditoria. |
