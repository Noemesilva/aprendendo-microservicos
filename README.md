# aprendendo-microservicos

📚 Arquitetura de Microsserviços — Miniguia de Estudos(NotebbokLM)

Este repositório foi desenvolvido para o desafio de projeto da DIO, utilizando o **NotebookLM** como ferramenta de aprendizagem ativa para explorar a transição de sistemas monolíticos para microsserviços.

---

## 🎯 Contexto e Objetivos

O tema escolhido foi **Arquitetura de Microsserviços**. O objetivo principal foi entender como essa estrutura resolve gargalos de escalabilidade e resiliência, além de validar estratégias de modernização de sistemas legados.

---

## 🔍 Curadoria de Fontes

Para alimentar o NotebookLM, utilizei fontes bibliográficas, com destaque para:
1. **[Microservices - Martin Fowler](https://martinfowler.com/articles/microservices.html)** 
2. **[Microsoft Azure Architecture Center: Estilo de arquitetura de microsserviços](https://learn.microsoft.com/pt-br/azure/architecture/guide/architecture-styles/microservices)**  
3. **[AWS: O que são microsserviços?](https://aws.amazon.com/pt/microservices/)** 

---

## 🛠️ Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Nesta seção, registro o meu raciocínio e as dificuldades encontradas para extrair o melhor conhecimento da IA. 

### O Desafio: A barreira da teoria abstrata
Inicialmente, tive dificuldades em absorver termos técnicos densos como *Bounded Context*, *Circuit Breaker* e *Strangler Fig* apenas através das definições teóricas. As respostas da IA eram precisas, mas difíceis de visualizar na prática.

### A Solução: Prompt de Contextualização Prática
Para superar essa dificuldade, elaborei um prompt estratégico que forçasse a IA a sair da teoria e entrar em um cenário real.

**Prompt Estratégico Elaborado:**
> *"Aja como um Arquiteto de Software Sênior. Crie um caso de uso detalhado simulando um E-commerce de alto tráfego durante a Black Friday que migrou de monólito para microsserviços. Explique como a separação dos domínios (Catálogo, Carrinho e Pagamentos) resolveu problemas de auto-scaling, resiliência e agilidade de deploy."*

### O Resultado (Insight Técnico)
O uso do exemplo do **E-commerce na Black Friday** foi o ponto de virada. Ao aplicar os conceitos em um evento real, ficou claro como:
* O **Bounded Context** separa o que é "Produto" (Catálogo) do que é "Venda" (Pagamento), evitando conflitos de dados.
* A **Resiliência** não é apenas um termo, mas a garantia de que, se o Pagamento falhar, o cliente ainda consegue usar o Carrinho.
* O **Troubleshooting** se tornou mais fácil ao entender que o erro no quiz sobre *API Gateway* (querer colocar lógica nele) causaria um gargalo insustentável em um dia de pico de vendas.

---

## 📖 Miniguia de Estudo (Entrega Final)

### 1. Resumos Estruturados do Assunto
* **Escalabilidade Granular:** Capacidade de escalar apenas o serviço de Catálogo enquanto o de Pagamentos permanece estável.
* **Resiliência (Fault Tolerance):** Isolamento de falhas via padrões como *Circuit Breaker* e *Bulkhead*.
* **Migração via Strangler Fig:** Substituição gradual do sistema antigo por novos serviços, reduzindo riscos operacionais.

### 2. Glossário de Conceitos
* **Bounded Context:** Fronteira lógica onde um modelo de domínio específico é aplicado.
* **API Gateway:** Ponto de entrada único para gerenciar tráfego, sem conter lógica de negócio.
* **Monolito Distribuído:** Antipadrão onde os serviços são separados, mas continuam dependentes para deploy.

### 3. Prompts Reutilizáveis para Revisão
* *"Com base nas fontes fornecidas, aja como um Arquiteto de Software Sênior. Compare a arquitetura de microsserviços com a monolítica, criando uma tabela de vantagens e desvantagens, focando especificamente em escalabilidade, resiliência e complexidade de deploy."*
* *"Quais os principais desafios de comunicação em microsserviços e como o Gateway atua nisso?"*
* *"O que são contextos delimitados (bounded contexts) no DDD?"*
---
> [!IMPORTANT]
> **Confira o meu Caderno de Estudos no NotebookLM:** [Acesse aqui](https://notebooklm.google.com/notebook/e7cadd44-bc69-4bc9-ac6e-0a13d265d493)
