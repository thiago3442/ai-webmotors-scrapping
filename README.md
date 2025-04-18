# Webmotors Car Data Scraper 🚗

## Visão Geral

Este projeto é um script Python que extrai dados de carros 🚘 do site da Webmotors e envia os resultados para você via e-mail 📧 e Telegram 💬. Ele foi projetado para automatizar o processo de coleta de informações sobre carros de seu interesse, como nome, preço e link do anúncio.

## Funcionalidades

* **Extração de Dados da Webmotors:** Extrai dados de carros de modelos específicos do site da Webmotors.
* **Agendamento Diário:** O script pode ser agendado para rodar diariamente, fornecendo atualizações regulares.
* **Notificações por E-mail:** Envia os dados extraídos para o seu endereço de e-mail.
* **Notificações do Telegram:** Envia os dados extraídos para o seu chat do Telegram.
* **API do Gemini:** Utiliza a API do Gemini para processar e extrair informações relevantes dos anúncios de carros.

## Requisitos

* Python 3.6 ou superior
* Bibliotecas Python:
    * `requests`
    * `beautifulsoup4`
    * `schedule`
    * `google-generativeai`
    * `smtplib`
    * `email.mime.text`
    * `email.mime.multipart`
* Conta do Google Cloud com a API do Gemini ativada
* Conta do Telegram e token de bot
* Servidor de e-mail (por exemplo, Gmail)

## Instalação

1.  **Clone o repositório:**

    ```bash
    git clone [https://github.com/seu-usuario/nome-do-repositorio.git](https://github.com/seu-usuario/nome-do-repositorio.git)
    cd nome-do-repositorio
    ```

2.  **Instale as dependências:**

    ```bash
    pip install requests beautifulsoup4 schedule google-generativeai
    ```

3.  **Configure as credenciais:**

    * Obtenha sua chave da API do Gemini em seu projeto do Google Cloud.
    * Obtenha o token do seu bot do Telegram e o ID do chat do Telegram.
    * Configure suas credenciais de e-mail (endereço de e-mail 📧 e senha 🔑).
    * Abra o arquivo `script.py` e substitua os valores de marcador com suas credenciais:

        ```python
        gemini_api_key = "SUA_CHAVE_DA_API_GEMINI"
        telegram_bot_token = "SEU_TOKEN_DO_TELEGRAM_BOT"
        telegram_chat_id = "SEU_CHAT_ID_DO_TELEGRAM"
        destinatario_email = 'seu_email@gmail.com'
        assunto_email = 'Carros Encontrados na Webmotors'
        remetente_email = 'seu_email@gmail.com'
        senha_remetente_email = 'sua_senha_do_gmail'
        ```

## Uso

1.  **Execute o script:**

    ```bash
    python script.py
    ```

2.  **Agendamento:**

    * O script está configurado para ser executado diariamente às 10:00 🕙. Para alterar o horário, modifique a linha no arquivo `script.py`:

        ```python
        schedule.every().day.at("10:00").do(tarefa)
        ```

3.  **Receba os dados:**

    * Os dados extraídos serão enviados para o seu endereço de e-mail 📧 e para o seu chat do Telegram 💬 no horário agendado.

## Personalização

* **Modelos de carros:** Para alterar os modelos de carros pesquisados, modifique a lista `modelos_desejados` no arquivo `script.py`:

    ```python
    modelos_desejados = ['Chevrolet Onix', 'Hyundai HB20', 'Volkswagen Gol']
    ```

* **Horário de agendamento:** Para alterar o horário em que o script é executado, modifique a string de tempo na chamada `schedule.every().day.at()`:

    ```python
    schedule.every().day.at("14:30").do(tarefa)  # Executa às 14:30 🕞
    ```

* **Formato do e-mail:** Para personalizar o formato do e-mail 📧, modifique a variável `mensagem_email` na função `tarefa()`. Você pode usar HTML para formatar o e-mail.
* **Mensagem do Telegram:** Para personalizar a mensagem do Telegram 💬, modifique a variável `mensagem_telegram` na função `tarefa()`.

## Tratamento de Erros

O script inclui tratamento de erros para lidar com os seguintes casos:

* Falha ao acessar o site da Webmotors 🌐
* Falha ao extrair dados de um anúncio de carro 🚗
* Falha ao enviar e-mail 📧
* Falha ao enviar mensagem do Telegram 💬
* Erros ao analisar a resposta da API do Gemini

## Notas

* Certifique-se de que seu servidor de e-mail permita que o script envie e-mails. Para o Gmail, pode ser necessário ativar o "acesso a aplicativos menos seguros" ou usar uma senha de aplicativo 🔑.
* A API do Gemini tem seus próprios termos de uso e preços 💰. Consulte a documentação do Google Cloud para obter mais detalhes.
* O site da Webmotors pode alterar sua estrutura HTML, o que pode quebrar o script 🛠️. Se isso acontecer, você pode precisar ajustar os seletores CSS no script.
* Use este script com responsabilidade e respeite os termos de serviço da Webmotors e do Telegram 🙏.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para enviar problemas 🐞 ou abrir pull requests 🚀 para melhorar este projeto.
