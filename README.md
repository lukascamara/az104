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
