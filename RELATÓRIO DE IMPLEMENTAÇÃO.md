RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS
Data: 11 de janeiro de 2026

Empresa: Abstergo Industries

Responsável: Gabriel Lucas

Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por [Seu Nome]. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos e modernizar a infraestrutura de distribuição farmacêutica.

Descrição do Projeto
O projeto foi estruturado para resolver os principais gargalos de uma empresa que não possui cloud: alto custo de servidores físicos, manutenção de bancos de dados e armazenamento de arquivos pesados.

Etapa 1:
Nome da ferramenta: Amazon EC2 com Spot Instances (Instâncias Spot).

Foco da ferramenta: Processamento computacional de baixo custo.

Descrição de caso de uso: A Abstergo processa grandes lotes de pedidos e relatórios logísticos durante a madrugada para enviar às farmácias parceiras. Em vez de manter servidores físicos ligados 24/7, utilizaremos Instâncias Spot, que aproveitam a capacidade ociosa da AWS com até 90% de desconto em relação ao preço sob demanda.

Ganho Principal: Redução drástica no gasto com infraestrutura de servidores para tarefas que não são críticas em tempo real (batch processing).

Etapa 2:
Nome da ferramenta: Amazon S3 (Simple Storage Service).

Foco da ferramenta: Armazenamento de objetos escalável e durável.

Descrição de caso de uso: Armazenamento de manuais de medicamentos, notas fiscais digitais e registros regulatórios da Anvisa. Substitui servidores de arquivos locais (NAS/Storage) que exigem manutenção física e upgrades constantes. Com o uso de S3 Intelligent-Tiering, os arquivos antigos que ninguém acessa são movidos automaticamente para camadas mais baratas.

Ganho Principal: Eliminação de gastos com hardware de armazenamento e garantia de 99,999999999% de durabilidade dos dados farmacêuticos.

Etapa 3:
Nome da ferramenta: Amazon DynamoDB.

Foco da ferramenta: Banco de dados NoSQL totalmente gerenciado.

Descrição de caso de uso: Gerenciamento do inventário em tempo real e rastreio de pedidos das farmácias. Por ser um serviço Serverless, a Abstergo não precisa pagar por um servidor de banco de dados rodando sem uso; ela paga apenas pela leitura e escrita realizada.

Ganho Principal: Alta disponibilidade e performance constante sem a necessidade de uma equipe de DBAs (administradores de banco de dados) dedicada para gerenciar patches e backups.

Conclusão
A implementação de ferramentas na empresa Abstergo Industries tem como esperado a redução de gastos operacionais com hardware em até 60% no primeiro ano, além de permitir que a empresa foque em sua atividade fim (distribuição) em vez de manutenção de TI. A escalabilidade da nuvem garantirá que, conforme o número de farmácias parceiras aumente, a infraestrutura acompanhe o crescimento de forma automática e eficiente.

Anexos
Planilha de estimativa de custos (AWS Pricing Calculator).

Guia de boas práticas para segurança de dados sensíveis (Criptografia no S3).

Diagrama de arquitetura Cloud-Native para Hubs Logísticos.

Assinatura do Responsável pelo Projeto: Gabriel Lucas
