# Sistema Multi-Agente de IA para Apoio à Saúde

Este é um protótipo funcional de um sistema de agentes de Inteligência Artificial (IA) construído em Python. O objetivo é demonstrar como agentes de IA podem orquestrar tarefas complexas, como triagem de usuários e busca de informações em tempo real, para resolver um problema do mundo real: o apoio a pessoas com ludopatia.

**Foco do Projeto:** Este projeto não é uma ferramenta de diagnóstico, mas sim uma **prova de conceito de engenharia** focada na arquitetura de agentes, uso de LLMs e integração de ferramentas externas (Google Search).

---

### 1. Arquitetura da Solução: Um Sistema de Dois Agentes

A solução opera com dois agentes de IA distintos, cada um com uma responsabilidade clara, orquestrados em Python:

#### 🤖 Agente 1: Triagem e Psicoeducação (`AgenteTriagem`)
* **Função:** Atua como o primeiro contato com o usuário.
* **Implementação:** Um agente baseado em lógica de Python que guia o usuário por um fluxo de perguntas (sim/não) para incentivar a autoconsciência sobre hábitos de jogo.
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

---

### 3. Como Executar o Projeto

#### Pré-requisitos
1.  Python 3.x
2.  Instalar as bibliotecas:
    ```bash
    pip install google-generativeai google-adk
    ```

#### Configuração da API Key
Você precisará de uma chave de API do Google.

1.  Defina sua chave de API como uma variável de ambiente:
    `export GOOGLE_API_KEY="SUA_CHAVE_AQUI"`
2.  (No Google Colab) Use o gerenciador de segredos (Secrets) e nomeie-o como `GOOGLE_API_KEY`.

#### Executar
1.  Salve o código como `chatbot_ludopatia.py`.
2.  Execute o script no seu terminal:
    ```bash
    python chatbot_ludopatia.py
    ```

---

### 4. Próximos Passos (Roadmap)

Este projeto estabeleceu a base, mas pode evoluir para:

* **Front-End:** Desenvolver uma interface gráfica (Web com Streamlit/Flask) para uma interação mais amigável que a linha de comando.
* **Aprimoramento do Agente:** Usar *fine-tuning* no Agente de Triagem para interações mais fluidas e empáticas, indo além das perguntas de sim/não.
* **Integração de APIs:** Conectar diretamente com APIs de saúde (ao invés do Google Search) para localizar profissionais de forma mais precisa.

---
*Aviso: Esta aplicação é uma ferramenta de demonstração e informação. Não fornece diagnóstico médico nem substitui a consulta por profissionais de saúde qualificados.*
