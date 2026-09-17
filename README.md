### Site de casamento com confirmação de presença e integração serverless

Desenvolvi e publiquei um site de casamento utilizando HTML, CSS e JavaScript, com hospedagem pelo GitHub Pages. O projeto possui apresentação do casal, informações do evento, confirmação de presença, validação por código de convite, lista de presentes, links externos e opção de contribuição por Pix.

Para evitar a exposição direta de informações sensíveis no repositório público, implementei um back-end serverless com Cloudflare Workers. A API valida o código do convite, controla a origem das requisições, fornece o endereço de entrega somente para convidados autorizados e processa as confirmações de presença.

As confirmações são armazenadas no Cloudflare KV utilizando o telefone como identificador. Caso o mesmo convidado envie o formulário novamente, o registro anterior é atualizado, reduzindo duplicidades.

Também desenvolvi uma integração com Google Sheets por meio de um Google Apps Script publicado como App da Web. O Cloudflare envia os dados de forma autenticada por token, e o script cria ou atualiza automaticamente os registros na planilha de controle.

Durante o projeto, trabalhei com Git e GitHub, APIs, requisições HTTP, JSON, CORS, variáveis de ambiente, secrets, armazenamento chave-valor, logs, implantação serverless e integração entre diferentes serviços.

Utilizei inteligência artificial como ferramenta de apoio para desenvolvimento e diagnóstico. Fui responsável por compreender a arquitetura, adaptar os códigos, configurar os serviços, realizar os deploys, testar o fluxo e corrigir problemas de permissões, autenticação e integração.
