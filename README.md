# az104

Resumo prático: Criar uma VM no Azure é como montar um computador na nuvem. Você escolhe o sistema operacional, configura o hardware (como CPU, memória e disco), define a rede e, com alguns cliques (ou comandos), ela está pronta para uso.
Boas práticas:
Use imagens prontas: O Azure oferece imagens com Windows, Linux e até ferramentas como SQL Server já instaladas.
Pense na performance: Escolha o tamanho da VM conforme a carga de trabalho. VMs pequenas são boas para testes, grandes para produção.
Organize com grupos de recursos: Assim você mantém tudo relacionado (VM, discos, redes) no mesmo "pacote".
Automatize com templates: Use Azure Resource Manager (ARM) ou Bicep para implantar várias VMs com a mesma configuração.

- Desanexando Discos de VMs no Azure
Resumo prático: Desanexar um disco é basicamente "desconectar" ele da VM. O disco permanece salvo na conta do Azure, mas sem estar vinculado a nenhuma máquina — pronto para ser reutilizado, analisado ou até excluído.
Boas práticas:
Desligue a VM primeiro, por segurança.
No portal do Azure, vá até a VM > Discos > escolha o disco de dados > clique em Desanexar.
Depois disso, o disco aparecerá como "não anexado" na seção de Discos do Azure.
Evite deletar direto: só remova o disco permanentemente se tiver certeza de que não será mais usado.
Você também pode montar o disco em outra VM, útil para recuperação de dados ou troubleshooting.



Implementando Monitoramento:

1 Planejamento
Antes de começar a configurar alertas e dashboards, pense no que realmente precisa ser monitorado:
- Quais recursos são críticos?
- Quais métricas fazem sentido (CPU, memória, latência, falhas)?
- Quem precisa ser notificado?
Dica: Crie um mapeamento com os serviços que serão acompanhados e as equipes responsáveis.

2  Azure Monitor como base
O Azure Monitor é o hub de monitoramento da plataforma. Com ele, você consegue:
- Coletar métricas e logs de quase todos os serviços
- Criar dashboards personalizados
- Disparar alertas com base em condições específicas
Dica: Configure Workbooks no Monitor para visualizar dados com painéis interativos.

3 diagnósticos em todos os recursos
Habilite logs de diagnóstico (Azure Diagnostics) nos recursos como VMs, Storage, App Services, etc. Assim, você garante que tudo seja registrado para análise posterior.
Dica: Direcione esses logs para um Log Analytics Workspace — facilita a centralização e análise via KQL.

4 Crie Alertas Inteligentes
Configure alertas com base em métricas (CPU > 80%, por exemplo), logs (como erros específicos), ou até consultas com KQL.
Dica: Agrupe alertas com Action Groups para notificar pessoas via e-mail, SMS, chamada webhook, etc.

5 Defender for Cloud
O Defender for Cloud oferece insights de segurança e postura — ideal para identificar riscos de configuração, vulnerabilidades e comportamento suspeito.
Dica: Ative as recomendações automáticas para reforçar a proteção dos recursos monitorados.

6 ferramentas auxiliares
Além do Azure Monitor, combine com:
- Network Watcher: para tráfego de rede e conectividade
- Application Insights: se tiver aplicações Web, APIs ou microserviços
- Azure Advisor: para sugestões de melhoria em performance, segurança e custo
