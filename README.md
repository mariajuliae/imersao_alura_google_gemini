# Sistema de Apoio à Ludopatia com IA

Este projeto é um modelo conceitual de um sistema de agentes de Inteligência Artificial (IA) desenvolvido em Python, com o objetivo de oferecer apoio inicial, informações e recursos para indivíduos que possam estar enfrentando problemas relacionados à ludopatia (vício em jogo).

**Aviso Importante:** Esta aplicação é uma ferramenta de demonstração, informação e reflexão. 
**Não fornece diagnóstico médico nem substitui a consulta e o acompanhamento por profissionais de saúde qualificados.**

## Funcionalidades Principais

O sistema é composto por dois agentes principais:

1.  **Agente de Triagem e Autoconscientização (`AgenteTriagem`):**
    * Realiza uma série de perguntas interativas (sim/não) para ajudar o usuário a refletir sobre seus hábitos de jogo e identificar possíveis sinais de alerta.
    * Fornece um feedback geral com base nas respostas, incentivando a autoconsciência.
    * Apresenta informações educativas básicas sobre a ludopatia, seus sinais e onde buscar ajuda.

2.  **Agente de Encaminhamento e Busca de Recursos (`agente_encaminhamento`):**
    * Utiliza o Google Agent Development Kit (ADK) e a ferramenta Google Search.
    * Se o usuário desejar, este agente busca online (simuladamente, com base nas capacidades do modelo e da ferramenta de busca) por:
        * Profissionais de saúde mental (psicólogos, psiquiatras) ou clínicas especializadas no tratamento da ludopatia, com base na cidade e estado fornecidos pelo usuário.
        * Grupos de Jogadores Anônimos (JA) na localidade informada ou orientações sobre como encontrar reuniões (presenciais e online).
    * Fornece sugestões de termos de busca e como acessar recursos como o SUS, CAPS e sites oficiais de JA.

## Como Funciona

* O `AgenteTriagem` opera através de uma lógica de perguntas e respostas predefinidas em Python.
* O `agente_encaminhamento_adk` é um agente construído com o `google-adk`, que recebe instruções para interagir com a ferramenta `google_search`. Ele processa a solicitação do usuário (localização) e usa a busca para encontrar informações relevantes, formatando-as conforme as instruções.

## Como Executar o Projeto

1.  **Pré-requisitos:**
    * Python 3.x
    * Bibliotecas Python: `google-generativeai`, `google-adk`
        ```bash
        pip install google-generativeai google-adk
        ```

2.  **Configuração da Chave de API do Google:**
    * Você precisará de uma chave de API do Google para usar os modelos generativos e a ferramenta de busca.
    * Defina a sua chave de API como uma variável de ambiente chamada `GOOGLE_API_KEY`.
        * No Colab, você pode usar o gerenciador de segredos (ícone de chave no painel esquerdo) e nomear o segredo como `GOOGLE_API_KEY`.
        * Em um ambiente local, você pode definir a variável de ambiente no seu sistema ou, para fins de teste (menos seguro), diretamente no script (ex: `os.environ["GOOGLE_API_KEY"] = "SUA_CHAVE_AQUI"`).

3.  **Executar o Script:**
    * Salve o código Python fornecido no Canvas como um arquivo `.py` (por exemplo, `chatbot_ludopatia.py`).
    * Execute o script a partir do seu terminal:
        ```bash
        python chatbot_ludopatia.py
        ```
    * Siga as instruções no console para interagir com os agentes.

## Estrutura do Código

* **`informacoes_ludopatia`**: String contendo texto educativo sobre ludopatia.
* **`AgenteTriagem` (Classe Python)**: Gerencia a triagem inicial e a psicoeducação.
* **`agente_encaminhamento_adk` (Objeto `Agent` do ADK)**: Responsável pela busca de recursos online.
* **`call_adk_agent(...)`**: Função para interagir com o agente ADK.
* **`to_markdown_display(...)`**: Função para formatar a saída em Markdown (para ambientes como Jupyter/Colab).
* **`main()`**: Orquestra a interação do usuário com os agentes.

## Limitações

* **Não é um Diagnóstico:** Reitera-se que esta ferramenta não substitui a avaliação profissional.
* **Qualidade da Busca:** A precisão e a abrangência das informações fornecidas pelo `agente_encaminhamento_adk` dependem da capacidade do modelo LLM e da ferramenta Google Search.
* **Interface de Linha de Comando:** A interação atual é via console.

## Possíveis Melhorias Futuras

* Desenvolvimento de uma interface gráfica (Web ou Desktop).
* Integração com APIs mais específicas para localização de profissionais de saúde.
* Aprimoramento do Processamento de Linguagem Natural (PLN) para interações mais fluidas.
* Internacionalização e localização para outras línguas e regiões.
* Coleta de feedback anônimo para melhoria contínua.


---

*Este projeto foi desenvolvido como parte de um estudo/exercício e visa explorar o uso de IA para fornecer suporte informativo.*
