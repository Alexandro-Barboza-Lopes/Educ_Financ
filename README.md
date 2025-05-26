# 🧠 Educador Financeiro com IA + Geração de Relatórios

## 📌 Visão Geral

Este projeto consiste em um **assistente virtual de educação financeira** que:

* Interage com o usuário para entender sua situação financeira
* Oferece orientações com base em boas práticas e na filosofia de Luiz Barsi
* Gera relatórios financeiros personalizados (em PDF e Markdown)
* Usa a **API Gemini (Google Generative AI)** para respostas empáticas e sob medida

---

## 🧰 Tecnologias Utilizadas

* **Python**
* **Google Generative AI (Gemini)**
* **ReportLab** (para gerar PDFs)
* **Markdown** (para relatórios em texto)
* `input()` e terminal para interface interativa

---

## 🧹 Estrutura do Código

### 1. **Inicialização e Configuração**

* Importação de bibliotecas
* Inicialização do modelo `gemini-2.0-flash` da Google:

  ```python
  model = genai.GenerativeModel('gemini-2.0-flash')
  chat = model.start_chat(history=[])
  ```

### 2. **Instruções e Estratégias**

Define duas strings importantes para orientar a IA:

* `instrucoes_sistema`: define o tom empático e os objetivos do assistente
* `estrategias_barsi`: resumo da filosofia de investimentos de Luiz Barsi

### 3. **Funções Auxiliares**

#### 🔄 Conversão e Formatação

* `converter_para_numero()`: limpa e transforma strings de valores monetários em `float`
* `formatar_moeda()`: formata valores como "R\$ 1.000,00"

#### 💬 Interação com IA

* `obter_resposta(mensagem, incluir_barsi=False)`: envia prompts para a IA com ou sem as estratégias de Barsi

---

### 4. **Geração de Relatórios**

#### 📄 PDF com `reportlab`

* Função: `gerar_relatorio_pdf(dados_usuario)`
* Inclui:

  * Perfil financeiro
  * Renda e gastos
  * Reserva de emergência
  * Plano personalizado
  * Estratégias Barsi (se aplicável)

#### 📝 Markdown

* Função: `gerar_relatorio_markdown(dados_usuario)`
* Gera saída de texto estruturada para visualização rápida ou exportação

---

### 5. **Interação Principal: `educador_financeiro()`**

Fluxo:

1. Solicita informações do usuário: salário, renda extra, gastos
2. Faz perguntas qualitativas (situação atual, estratégias, objetivos etc.)
3. Envia essas respostas para a IA gerar feedback acolhedor e plano financeiro
4. Exibe alertas e sugestões com base na diferença entre renda e gastos
5. Permite que o usuário:

   * Faça perguntas adicionais
   * Gere relatórios (PDF ou texto)
   * Encerre a sessão

---

## 📈 Funcionalidades Inteligentes

* **Feedback empático personalizado**: cada resposta do usuário gera uma reação da IA com dicas práticas
* **Plano financeiro completo** com orientações práticas
* **Cálculo automático da reserva de emergência** com base em gastos
* **Interação aberta**: o usuário pode tirar dúvidas como "como sair das dívidas?" ou "como investir?"

---

## 📅 Exemplo de Saída Markdown

```markdown
# Relatório de Planejamento Financeiro
**Data:** 26/05/2025

## 1. Perfil Financeiro
**Situação atual:** Consigo pagar contas mas sem sobras  
**Estratégias atuais:** Tentando economizar no mercado  
**Reserva de emergência:** Tenho para 1 mês  
**Objetivos financeiros:** Comprar uma casa  
**Interesse em investimentos:** Sim

## 2. Análise de Renda e Despesas
**Salário mensal:** R$ 3.000,00  
**Renda extra mensal:** R$ 500,00  
**Renda total mensal:** R$ 3.500,00  
**Gastos mensais:** R$ 3.200,00  
**Saldo mensal:** R$ 300,00  

## 3. Recomendações para Reserva de Emergência
- **Reserva mínima (3x gastos):** R$ 9.600,00  
- **Reserva ideal (6x gastos):** R$ 19.200,00  

## 4. Seu Plano Financeiro Personalizado
(Conteúdo gerado pela IA com plano em 3–4 parágrafos)

## 5. Próximos Passos Recomendados
1. Estabeleça um orçamento rigoroso
2. Priorize a criação da sua reserva
3. Reduza dívidas de alto custo
4. Comece a investir após ter a reserva

## 6. Estratégias de Investimento (Método Barsi)
(Resumo em tópicos das estratégias de Luiz Barsi)
```

---

## 🧠 Considerações Finais

Este projeto é ideal para:

* Workshops e oficinas de finanças pessoais
* Acompanhamento de clientes em consultorias financeiras
* Educação financeira automatizada com empatia e inteligência

---
