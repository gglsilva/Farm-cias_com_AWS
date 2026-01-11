# GUIA DE BOAS PRÁTICAS: SEGURANÇA E CRIPTOGRAFIA (ABSTERGO INDUSTRIES)

## 1. OBJETIVO
Este documento estabelece as diretrizes de segurança para o armazenamento de dados sensíveis da Abstergo Industries no Amazon S3, visando conformidade regulatória e proteção contra vazamentos.

---

## 2. CRIPTOGRAFIA DE DADOS
Para garantir a confidencialidade, todos os dados devem ser criptografados em repouso e em trânsito.

### 2.1 Criptografia em Repouso (SSE-KMS)
- **Padrão:** Utilizar AWS KMS (Key Management Service).
- **Vantagem:** Permite rotação automática de chaves e auditoria detalhada de quem acessou a chave para descriptografar arquivos.
- **Ação:** Configurar o Bucket para rejeitar qualquer upload que não utilize criptografia KMS.

### 2.2 Criptografia em Trânsito (TLS)
- **Padrão:** Todos os dados devem trafegar via HTTPS.
- **Ação:** Aplicar política de bucket que negue acesso (Deny) a conexões via HTTP (porta 80).

---

## 3. CONTROLE DE ACESSO E PRIVACIDADE

### 3.1 Bloqueio de Acesso Público (Block Public Access)
- **Regra:** Deve estar ATIVADO em nível de conta e de bucket.
- **Justificativa:** Previne que erros humanos exponham dados da farmácia para a internet.

### 3.2 Princípio do Menor Privilégio
- **Implementação:** Utilizar IAM Roles específicas para cada aplicação.
- **Restrição:** Servidores que apenas geram notas fiscais não devem ter permissão para deletar arquivos, apenas para "PutObject" (escrita).

---

## 4. INTEGRIDADE E RESILIÊNCIA

### 4.1 Versionamento
- **Ativar:** Versionamento de Objetos.
- **Motivo:** Proteção contra exclusão acidental e ataques de Ransomware. Caso um arquivo seja deletado, a versão anterior permanece disponível.

### 4.2 S3 Object Lock (WORM)
- **Uso:** Para documentos regulatórios da ANVISA.
- **Função:** Impede que um arquivo seja deletado ou alterado por um período fixo (ex: 5 anos), mesmo por administradores.

---

## 5. MONITORAMENTO (AUDITORIA)
- **AWS CloudTrail:** Deve estar habilitado para registrar logs de acesso a dados (Data Events).
- **Amazon Macie:** Executar varreduras periódicas para identificar se há CPFs ou dados sensíveis em locais não autorizados.

---
*Documento gerado para: Abstergo Industries*
*Responsável Técnico: [Seu Nome]*
