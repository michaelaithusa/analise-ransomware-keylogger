# 🛡️ Simulação e Análise de Ameaças: Ransomware e Keylogger

## 📖 Descrição do Projeto
Este projeto foi desenvolvido como parte de um desafio educacional focado em cibersegurança. O objetivo principal é documentar e compreender o funcionamento de duas ameaças digitais clássicas: **Ransomwares** e **Keyloggers**. Em vez de focar na criação de artefatos maliciosos, este repositório detalha a mecânica teórica desses ataques, como eles exploram vulnerabilidades tecnológicas e humanas, e, mais importante, quais são as estratégias de defesa essenciais para mitigá-los.

## 🎯 Objetivos de Aprendizagem
- Compreender a mecânica de operação de Ransomwares e Keyloggers.
- Identificar as principais vulnerabilidades exploradas (falhas de sistema e engenharia social).
- Refletir sobre estratégias de defesa em profundidade (Defense in Depth).
- Documentar estudos teóricos e práticas de prevenção.

---

## 🦠 Análise Teórica das Ameaças

### 1. Ransomware
O ransomware é um tipo de malware que sequestra os dados da vítima (geralmente por meio de criptografia forte, como AES ou RSA) e exige um pagamento (resgate) para fornecer a chave de descriptografia.
*   **Mecânica de Infecção:** Geralmente propagado por e-mails de phishing (anexos maliciosos), exploração de serviços RDP expostos ou downloads drive-by.
*   **Ação no Sistema:** Uma vez executado, ele varre o disco em busca de arquivos críticos (documentos, bancos de dados, fotos), gera uma chave de criptografia, altera os arquivos e descarta uma nota de resgate (ex: `LEIA-ME.txt`).

### 2. Keylogger
Um keylogger é um software ou hardware projetado para registrar clandestinamente cada tecla pressionada no teclado do computador alvo.
*   **Mecânica de Infecção:** Frequentemente embutido em cavalos de Troia (Trojans) baixados por engano pelo usuário, ou instalado via acesso físico.
*   **Ação no Sistema:** Ele se acopla à API do sistema operacional (como hooks no Windows) para interceptar os eventos de teclado antes que cheguem ao aplicativo de destino. Os dados são salvos em arquivos ocultos e, posteriormente, exfiltrados (enviados) para o atacante via e-mail, FTP ou servidores C2 (Command and Control).

---

## 🛡️ Reflexão sobre Defesa e Mitigação

Para proteger sistemas e usuários contra essas ameaças, uma abordagem de segurança em camadas é fundamental:

1.  **Antivírus e EDR (Endpoint Detection and Response):**
    *   Soluções modernas não dependem apenas de assinaturas de vírus conhecidos, mas utilizam análise comportamental (heurística) para bloquear processos que tentam criptografar arquivos em massa ou injetar hooks suspeitos no teclado.
2.  **Firewall e Segurança de Rede:**
    *   Firewalls bem configurados podem bloquear a comunicação de saída de um keylogger tentando enviar logs por e-mail, ou impedir que um ransomware contate seu servidor de chaves.
3.  **Sandboxing e Restrição de Privilégios:**
    *   A execução de anexos suspeitos em ambientes isolados (sandbox) permite analisar o comportamento do arquivo antes que ele toque no sistema operacional real. Além disso, usar contas sem privilégios de administrador (Princípio do Menor Privilégio) impede que o malware faça alterações profundas no sistema.
4.  **Backups Offline (Foco contra Ransomware):**
    *   A única defesa garantida contra a perda de dados por ransomware é manter backups regulares, testados e mantidos offline (desconectados da rede principal), seguindo a regra 3-2-1.
5.  **Conscientização do Usuário (Security Awareness):**
    *   A falha humana ainda é o vetor número um. Treinar usuários para identificar e-mails de phishing, verificar remetentes e não baixar softwares pirateados reduz drasticamente a superfície de ataque.

## 🎓 Conclusão
O estudo do comportamento de malwares é essencial para a formação do profissional de Blue Team e Segurança da Informação. Entender como o ataque funciona na teoria permite arquitetar defesas muito mais eficientes na prática.
