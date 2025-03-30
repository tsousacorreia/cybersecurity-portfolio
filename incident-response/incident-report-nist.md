# 📊 Relatório de Resposta a Incidentes - NIST CSF

## 📄 Cenário da Atividade
Para entender o contexto deste relatório, consulte a [descrição completa do cenário](incident-report-nist-scenario.md).


## 📌 Introdução
**Data do incidente:** 2025-03-30  
**Tipo de incidente:** Flood de pacotes ICMP  
**Setor afetado:** Toda a rede interna da empresa.  
**Objetivo:** Aplicar o NIST Cybersecurity Framework para analisar, mitigar e fortalecer a resposta a incidentes cibernéticos, garantindo maior resiliência contra futuros ataques.

## 🚨 Resumo do Incidente
Uma empresa de multimídia que fornece serviços de Web design e marketing digital sofreu um **ataque DDoS** que interrompeu seus serviços por **duas horas**. O ataque foi realizado via **flood de pacotes ICMP**, explorando um firewall mal configurado.

## 🔎 Estrutura da Análise (NIST CSF)

### 1️⃣ Identificar (Identify)
**Objetivo:** Determinar ativos críticos, vulnerabilidades e riscos envolvidos.

**_Ativos e Sistemas Afetados:_**

- **Servidores de rede interna**
- **Firewall principal**
- **Serviços web e comunicação interna**

**_Vulnerabilidades Identificadas:_**

- ❌ Falta de configuração adequada no firewall para limitar tráfego ICMP
- ❌ Ausência de monitoramento proativo para padrões anômalos de tráfego
- ❌ Falta de um plano de resposta automatizado para mitigar ataques DDoS

**_Riscos Associados:_**

- ⚠️ **Interrupção de serviços essenciais para clientes**
- ⚠️ **Possível impacto na reputação da empresa**
- ⚠️ **Potenciais danos financeiros devido à inatividade**


### 2️⃣ Proteger (Protect)
**Objetivo:** Implementar medidas para proteger ativos contra futuros ataques.

**_Medidas Implementadas:_**

- ✅ **Configuração de firewall:** Implementação de uma regra para limitar a taxa de entrada de pacotes ICMP.
- ✅ **Verificação de IP de Origem:** Regras para bloquear pacotes ICMP vindos de endereços suspeitos.
- ✅ **Segmentação de Rede:** Isolamento de serviços críticos para evitar impacto total em futuros ataques.
- ✅ **Plano de Resposta Rápida:** Procedimentos atualizados para reação mais ágil a eventos de negação de serviço.


### 3️⃣ Detectar (Detect)
**Objetivo:** Monitorar e identificar atividades suspeitas antes que causem impacto.

**_Ferramentas e Técnicas Implementadas:_**

- 🛠 **Sistema de Monitoramento de Rede:** Software para identificar tráfego anômalo em tempo real.
- 📊 **Logs e Análises:** Implementação de registros detalhados para identificar padrões suspeitos.
- 🛡 **Sistema IDS/IPS:** Configuração de filtros específicos para detectar e bloquear ataques DDoS ICMP.
- 👤 **Monitoramento de Contas de Usuários:** Acompanhamento de acessos autorizados e não autorizados.


### 4️⃣ Responder (Respond)
**Objetivo:** Estabelecer um processo eficaz para conter incidentes e minimizar impactos.

**_Procedimentos de Resposta:_**

- 🛑 **Contenção:** Bloqueio imediato de tráfego ICMP e ativação de medidas de mitigação.
- 🔍 **Análise:** Revisão dos logs e identificação da origem do ataque.
- 📢 **Notificação:** Comunicação interna para equipes afetadas e acionamento de medidas de contingência.
- 🔧 **Correção:** Aplicação de regras aprimoradas de firewall e ajustes no IDS/IPS.

**_Dados Utilizados na Análise:_**

- 📂 Logs de tráfego de rede
- 🔥 Relatórios do firewall
- 📡 Informações dos servidores afetados

**_Aprimoramento da Resposta:_**

- 📖 **Implementação de um Runbook de Incidentes** para ações mais rápidas.
- 🎓 **Treinamento periódico da equipe de TI** em resposta a ataques DDoS.
- 🛠 **Testes regulares** para validação das configurações de mitigação.


### 5️⃣ Recuperar (Recover)
**Objetivo:** Restaurar serviços e melhorar resiliência organizacional.

**_Passos Tomados para a Recuperação:_**

- 🔄 **Restauração de serviços críticos com prioridade.**
- 📑 **Revisão de logs para garantir que o ataque cessou completamente.**
- ⚙️ **Testes de estabilidade para validar a funcionalidade da rede.**

**_Melhorias no Processo de Recuperação:_**

- 💾 **Implementação de backups automáticos** para recuperação mais rápida.
- 🔍 **verificação periódica da integridade dos backups** para evitar problemas na recuperação.
- 🌐 **Planos de redundância** para garantir continuidade operacional em caso de novos ataques.
- 🏴‍☠️ **Simulações regulares de ataques DDoS** para avaliar a eficácia das contramedidas.


## 💡 Reflexões e Notas Finais

**_Lições Aprendidas:_**

- 📌 **A configuração de firewall deve ser revisada regularmente para evitar brechas.**
- ⏳ **A resposta a incidentes precisa ser mais ágil e bem documentada.**
- 📡 **O monitoramento contínuo da rede é essencial para detectar ameaças emergentes.**

**_Próximos Passos:_**

- 📘 **Criar um Plano de Resiliência Cibernética mais robusto.**
- 🤝 **Melhorar a comunicação entre equipes de TI e Segurança da Informação.**
- 🛡 **Investir em soluções anti-DDoS avançadas.**


## 📌 Conclusão
O incidente demonstrou a necessidade de **políticas de segurança mais rigorosas e de um monitoramento mais eficaz**. Agora, com políticas aprimoradas e um monitoramento contínuo, a empresa está significativamente mais preparada para enfrentar desafios cibernéticos, garantindo a continuidade dos serviços e proteção de seus ativos digitais.

---

📖 **Criado por:** Thiago Correia | 2025

---
📜 **Licença**:  
Este documento está licenciado sob a **Creative Commons Atribuição-Compartilhamento pela mesma licença 4.0 Internacional (CC BY-SA 4.0)**.  
Você pode copiar, distribuir e modificar este conteúdo, desde que forneça o devido crédito ao autor e licencie qualquer obra derivada sob os mesmos termos.  

🔗 [Saiba mais sobre esta licença](https://creativecommons.org/licenses/by-sa/4.0/deed.pt)