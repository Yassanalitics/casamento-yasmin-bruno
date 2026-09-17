### Site de casamento com confirmação de presença e integração serverless

Desenvolvi e publiquei um site de casamento utilizando HTML, CSS e JavaScript, com hospedagem pelo GitHub Pages. O projeto possui apresentação do casal, informações do evento, confirmação de presença, validação por código de convite, lista de presentes, links externos e opção de contribuição por Pix.

Para evitar a exposição direta de informações sensíveis no repositório público, implementei um back-end serverless com Cloudflare Workers. A API valida o código do convite, controla a origem das requisições, fornece o endereço de entrega somente para convidados autorizados e processa as confirmações de presença.

As confirmações são armazenadas no Cloudflare KV utilizando o telefone como identificador. Caso o mesmo convidado envie o formulário novamente, o registro anterior é atualizado, reduzindo duplicidades.

Também desenvolvi uma integração com Google Sheets por meio de um Google Apps Script publicado como App da Web. O Cloudflare envia os dados de forma autenticada por token, e o script cria ou atualiza automaticamente os registros na planilha de controle.

Durante o projeto, trabalhei com Git e GitHub, APIs, requisições HTTP, JSON, CORS, variáveis de ambiente, secrets, armazenamento chave-valor, logs, implantação serverless e integração entre diferentes serviços.

Utilizei inteligência artificial como ferramenta de apoio para desenvolvimento e diagnóstico. Fui responsável por compreender a arquitetura, adaptar os códigos, configurar os serviços, realizar os deploys, testar o fluxo e corrigir problemas de permissões, autenticação e integração.






Resumo do que foi desenvolvido
Front-end do site
Site estático criado com HTML, CSS e JavaScript.
Página inicial apresentando Yasmin e Bruno.
Informações do casamento.
Área de confirmação de presença.
Validação por código de convite.
Área de endereço de entrega protegida.
Lista de presentes com links externos.
Alternativa de contribuição por Pix.
Publicação pelo GitHub Pages.
Controle de versão com Git e GitHub.
Back-end e segurança

Foi criado um back-end serverless no Cloudflare Workers para evitar que informações sensíveis ficassem diretamente no código público do GitHub.

O Worker é responsável por:

Receber requisições do site.
Permitir chamadas somente da origem configurada.
Validar o código do convite.
Retornar o endereço de entrega apenas após a validação.
Validar os dados da confirmação.
Salvar e atualizar confirmações.
Encaminhar as confirmações para o Google Sheets.
Manter tokens e dados sensíveis em secrets e variáveis protegidas.
Cloudflare KV

O Cloudflare KV foi utilizado como banco de dados chave-valor.

Estrutura utilizada:

convite:YB-2027-AMOR
rsvp:61998215604

A chave convite: valida o código informado pelo convidado. As chaves rsvp: armazenam as confirmações identificadas pelo telefone.

Quando o mesmo telefone envia novamente, o registro é atualizado, evitando duplicidades.

Integração com Google Sheets

Foi criado um Google Apps Script publicado como App da Web.

Ele:

Recebe os dados enviados pelo Cloudflare.
Valida um token secreto.
Localiza a aba Confirmações.
Procura o telefone na coluna correspondente.
Atualiza a linha existente ou cria uma nova.
Registra data, nome, telefone, presença, quantidade de pessoas, acompanhantes, restrições e código do convite.
Protege as células contra fórmulas maliciosas inseridas pelos usuários.
Depuração realizada

Durante o desenvolvimento, você resolveu problemas reais:

Binding incorreto do Cloudflare KV.
Diferença entre namespace, chave e variável de binding.
Publicação de novas versões do Worker.
Erro 403 causado pela permissão do Google Apps Script.
Configuração do Apps Script para acesso por qualquer pessoa.
Uso correto da URL /exec.
Erro de token entre WEBHOOK_TOKEN e SHEETS_TOKEN.
Análise dos logs do Cloudflare.
Testes do fluxo completo entre site, Worker, KV e planilha.

O GitHub Pages entrega o site. O Cloudflare Worker processa e protege as informações. O KV mantém os registros e códigos. O Apps Script funciona como ponte para a planilha.

Texto pronto para o portfólio
