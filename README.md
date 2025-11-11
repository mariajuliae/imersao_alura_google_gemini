# Sistema Multi-Agente de IA para Apoio à Saúde

Este é um protótipo funcional de um sistema de agentes de Inteligência Artificial (IA) construído em Python. O objetivo é demonstrar como agentes de IA podem orquestrar tarefas complexas, como triagem de usuários e busca de informações em tempo real, para resolver um problema do mundo real: o apoio a pessoas com ludopatia.

**Foco do Projeto:** Este projeto não é uma ferramenta de diagnóstico, mas sim uma **prova de conceito de engenharia** focada na arquitetura de agentes, uso de LLMs e integração de ferramentas externas (Google Search).

---

### 1. Arquitetura da Solução: Um Sistema de Dois Agentes

A solução opera com dois agentes de IA distintos, cada um com uma responsabilidade clara, orquestrados em Python:

#### 🤖 Agente 1: Triagem e Psicoeducação (`AgenteTriagem`)
* **Função:** Atua como o primeiro contato com o usuário.
* **Implementação:** Um agente baseado em lógica de Python (Classe `AgenteTriagem`) que guia o usuário por um fluxo de perguntas (sim/não) para incentivar a autoconsciência sobre hábitos de jogo.
* **Resultado:** Fornece informações educativas e, se o usuário consentir, aciona o próximo agente.

#### 🕵️‍♂️ Agente 2: Busca e Encaminhamento de Recursos (`agente_encaminhamento_adk`)
* **Função:** Encontrar ajuda profissional e grupos de apoio com base na localização do usuário.
* **Implementação:** Um agente avançado construído com o **Google Agent Development Kit (ADK)**.
* **Ferramentas:** Utiliza a ferramenta **Google Search** (integrada via ADK) para buscar informações em tempo real na web (Ex: "psicólogos em [Cidade]" ou "Jogadores Anônimos em [Estado]").
* **Resultado:** Processa a solicitação, interage com a ferramenta de busca e formata os resultados para o usuário.

---

### 2. Tecnologias e Ferramentas Utilizadas

* **Linguagem:** Python 3.x
* **Framework de Agentes:** Google Agent Development Kit (`google-adk`)
* **Modelo de IA:** Google Generative AI (`google-generativeai` - Gemini)
* **Ferramentas de Agente:** Google Search API
* **Outras:** `requests`, `warnings`

---

### 3. Como Executar o Projeto

#### 1. Crie o arquivo `requirements.txt`
Crie um arquivo `requirements.txt` na pasta do projeto com o seguinte conteúdo:

```txt
google-generativeai
google-adk
requests
