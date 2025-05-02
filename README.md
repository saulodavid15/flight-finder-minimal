# Aplicação Buscador de Passagens Aéreas

Este é um protótipo de aplicação web Flask para buscar passagens aéreas com base em dados simulados.

## Funcionalidades

- Busca de voos com base em critérios como origem, destino, datas, preço (reais ou milhas), companhia aérea, custo do milheiro e tipo de trecho.
- Exibição dos resultados filtrados em uma interface web.
- (Lógica interna para verificação de alertas, salva em `alerts.txt` no diretório raiz do projeto).

## Como Executar Localmente

1.  **Pré-requisitos:**
    *   Python 3.10 ou superior
    *   `pip` (gerenciador de pacotes Python)

2.  **Descompactar o arquivo:**
    *   Extraia o conteúdo do arquivo `flight_finder_app.zip` para um diretório de sua escolha.

3.  **Navegar até o diretório:**
    *   Abra um terminal ou prompt de comando e navegue até o diretório `flight_finder_app` que você acabou de extrair.
    ```bash
    cd caminho/para/flight_finder_app
    ```

4.  **Criar e Ativar Ambiente Virtual (Recomendado):**
    *   É uma boa prática usar um ambiente virtual para isolar as dependências do projeto.
    ```bash
    # Se você não tiver o venv (geralmente incluído no Python 3)
    # python3 -m pip install --user virtualenv
    python3 -m venv venv
    source venv/bin/activate  # No Linux/macOS
    # venv\Scripts\activate    # No Windows
    ```

5.  **Instalar Dependências:**
    *   Instale as bibliotecas Python necessárias listadas no arquivo `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```

6.  **Executar a Aplicação:**
    *   Execute o script principal da aplicação Flask.
    ```bash
    python src/main.py
    ```

7.  **Acessar a Aplicação:**
    *   Abra seu navegador web e acesse o endereço `http://127.0.0.1:5000` ou `http://localhost:5000`.

## Estrutura do Projeto

```
flight_finder_app/
├── venv/                  # Ambiente virtual Python
├── src/
│   ├── static/
│   │   └── index.html     # Arquivo HTML da interface
│   ├── flight_logic.py    # Lógica de carregamento, unificação e filtragem de dados
│   ├── main.py            # Arquivo principal da aplicação Flask
│   └── unified_flights.json # Arquivo com dados de voos simulados
├── requirements.txt       # Lista de dependências Python
└── README.md              # Este arquivo
```

## Observações

*   Esta aplicação utiliza **dados simulados** (`unified_flights.json`) e não busca informações em tempo real.
*   A funcionalidade de coleta de dados (APIs e web scraping) foi desenvolvida como prova de conceito em scripts separados (`skyscanner_collector.py`, `afklm_collector.py`, `smiles_scraper.py`) e não está integrada à aplicação Flask principal.
*   A funcionalidade de alerta apenas registra os alertas disparados no arquivo `alerts.txt` (criado na raiz do projeto ao executar `flight_logic.py` diretamente ou ao rodar o Flask app pela primeira vez após uma busca que dispare um alerta). Não há envio de e-mail, Telegram ou notificações push implementado.
*   A implantação automática falhou. Este pacote contém o código-fonte para implantação manual.

