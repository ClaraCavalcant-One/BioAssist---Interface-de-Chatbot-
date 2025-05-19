Documentação do Projeto: 
BioAssist - Interface de Chatbot

Data: 16 de Maio de 2025 - 
Versão: 1.0
Autor: Maria Clara Cavalcante


1. Introdução
 
Este documento descreve o desenvolvimento do BioAssist, um chatbot integrado ao Google Workspace, projetado para simplificar a gestão de informações de saúde dos usuários. A solução oferece uma série de funcionalidades que facilitam o arquivamento, consulta e organização de dados médicos de forma prática e segura.

Funcionalidades do Sistema

1. Arquivamento de Exames
Armazena informações relevantes de exames médicos no Google Sheets de forma estruturada e segura, permitindo fácil acesso e histórico clínico organizado.

2. Agendamento de Compromissos
Cria automaticamente eventos relacionados à saúde (consultas, exames, retornos) no Google Agenda, com notificações e lembretes para evitar esquecimentos.

3. Recuperação de Exames
Permite ao usuário consultar e visualizar dados de exames médicos previamente armazenados no Google Sheets, com busca rápida por data, tipo ou palavra-chave.

4. Consulta de Compromissos
Lista todos os compromissos de saúde registrados no Google Agenda, com filtros por data ou tipo de evento.

5. Geração de Insights a partir de Exames
Analisa os resultados dos exames arquivados para oferecer insights clínicos básicos, como tendências de saúde, valores fora do padrão de referência e sugestões de acompanhamento (dependendo da integração com modelos analíticos ou IA).

Interação com o Usuário

A interação inicial ocorre por meio de um chatbot, onde o usuário envia suas solicitações em linguagem natural. 
O sistema interpreta as mensagens e executa as ações correspondentes automaticamente, proporcionando uma experiência fluida e eficiente.

Layout da tela:
https://codepen.io/Maria-Clara-Cavalcante/pen/gbbEZGR

Aqui está a versão revisada e aprimorada do seu texto, com foco em clareza, coesão técnica e padronização do estilo, mantendo todos os detalhes relevantes e agregando melhorias linguísticas:

2. Detalhamento das Funcionalidades e Implementação

2.1. Arquivar Exames Médicos

Fluxo de Operação
 O usuário insere os dados do exame na interface. O JavaScript envia essa entrada ao backend via AJAX. O backend interpreta as informações, formata os dados e utiliza a Google Sheets API para armazená-los em uma nova linha da planilha designada.
Backend
Configuração de OAuth 2.0.

- Identificação da planilha de destino.
- Utilização do método append da API para inserção de dados.

Frontend

- O botão "Arquivar" ativa o campo de entrada e orienta o usuário.
- A área .white-space pode exibir o histórico da interação para melhor acompanhamento.

2.2. Agendar Compromissos de Saúde

Fluxo de Operação
 O usuário informa os detalhes do agendamento (data, hora, descrição, local). O backend processa esses dados e cria o evento no Google Calendar por meio da API. A confirmação ou falha é então exibida no frontend.

Backend
- Requer autenticação via OAuth 2.0.

- Criação de um objeto JSON com os dados do evento.

- Envio à Google Calendar API para criação do compromisso.

Frontend
- O botão "Agendar" pode sugerir o formato da entrada e focar o campo correspondente.

2.3. Buscar por Exames Arquivados

Fluxo de Operação
 O usuário insere um termo de busca. O backend acessa a planilha via Google Sheets API, realiza a leitura e aplica uma lógica de filtragem para identificar exames correspondentes. Os resultados são exibidos na interface.

Backend
- Leitura da planilha.

- Aplicação de filtros no conteúdo retornado.

- Retorno formatado dos dados ao frontend.

Frontend
- O botão "Buscar" exibe uma instrução clara e mostra os resultados na área .white-space.

2.4. Buscar Compromissos Agendados

Fluxo de Operação

 O usuário pode solicitar os compromissos agendados, com ou sem período específico. O backend consulta os eventos no calendário, filtrando por intervalo, e retorna os dados ao frontend.

Backend
- Uso da função de listagem da Google Calendar API.

- Definição de parâmetros de intervalo (início e fim).

- Retorno formatado com os dados relevantes.

Frontend
- Pode utilizar o mesmo botão "Buscar" com opções adicionais ou um botão dedicado.
- A exibição dos compromissos deve destacar data, hora, descrição e local.

3. Tecnologias Envolvidas

- Frontend: HTML, CSS, JavaScript
- Backend: Python, Flask ou Django
- APIs: google-api-python-client, google-auth
- Infraestrutura: Google Cloud Platform (GCP)

4. Próximos Passos
Finalizar o desenvolvimento do backend e definição dos endpoints.

- Implementar interpretação de linguagem natural no backend para comandos do usuário.
- Realizar integração completa com as APIs do Google.
- Conectar frontend e backend com validação e feedback.
- Melhorar a interface para exibição de histórico, resultados e erros.
- Implementar funcionalidades de login/logout com OAuth.
- Adotar tratamento robusto de erros e mensagens amigáveis ao usuário.
- Conduzir testes unitários, funcionais e de integração.
- Reforçar as medidas de segurança e privacidade.

6. Conclusão
  
  O BioAssist propõe uma solução prática, segura e integrada para organização de informações de saúde, utilizando os serviços do Google Workspace. Com uma interface web intuitiva e uma camada de backend robusta, a ferramenta busca facilitar o arquivamento, agendamento e recuperação de dados médicos. O avanço no desenvolvimento da lógica do chatbot e a integração com APIs são essenciais para entregar uma experiência fluida e centrada no usuário.


Observação: Para o desenvolvimento, utilizei algumas ferramentas e linguagens com o objetivo de realizar testes. Os arquivos disponíveis ainda estão em fase de desenvolvimento.

O projeto segue em desenvolvimento. 
