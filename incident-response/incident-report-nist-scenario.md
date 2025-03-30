# 🔍 Visão Geral da Atividade

Criar um relatório de incidente usando o conhecimento adquirido sobre redes ao longo do curso para analisar um incidente de rede. A análise segue a Estrutura de Segurança Cibernética do Instituto Nacional de Padrões e Tecnologia (NIST CSF).

## 📄 Cenário do Incidente

Você é analista de segurança cibernética e trabalha para uma empresa de multimídia que oferece serviços de Web design, design gráfico e soluções de marketing de mídia social para pequenas empresas. Sua organização sofreu recentemente um ataque DDoS, comprometendo a rede interna por duas horas até ser resolvido.

### **_Detalhes do Ataque:_**

- Durante o ataque, os serviços de rede pararam de responder devido a um fluxo de pacotes ICMP.
- O tráfego normal da rede interna foi bloqueado.
- A equipe de gerenciamento de incidentes respondeu bloqueando pacotes ICMP e interrompendo serviços não críticos.
- A investigação revelou que o ataque ocorreu devido a um firewall mal configurado, permitindo que um agente mal-intencionado executasse um ataque de negação de serviço distribuído (DDoS).

### **_Soluções Implementadas:_**

- Nova regra de firewall para limitar a taxa de entrada de pacotes ICMP.
- Verificação de endereço IP de origem para identificar IPs falsos.
- Software de monitoramento de rede para detectar tráfego anormal.
- Implementação de IDS/IPS para filtrar tráfego ICMP suspeito.

### **_Plano de Segurança com NIST CSF:_**

- **Identificar:** Auditorias regulares de redes, sistemas e acessos.

- **Proteger:** Políticas, treinamento e ferramentas de mitigação.

- **Detectar:** Melhoria no monitoramento e resposta rápida.

- **Responder:** Contenção, análise e melhoria dos processos.

- **Recuperar:** Restauração dos sistemas e normalização dos serviços.


🔗 [Acesse o relatório completo](incident-response/incident-report-nist.md)
