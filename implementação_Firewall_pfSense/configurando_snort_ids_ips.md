<h1>Configurar IDS/IPS - Snort</h1>
   
   No pfSense no menu: 
    
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/439a3b1bb6390363cd98a118d0d517994f7452ba/imagens/configurando_snort/snort01.png" width="70%"/>
    
   Instale o pacote do Snort. 
    
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/439a3b1bb6390363cd98a118d0d517994f7452ba/imagens/configurando_snort/snort02.png" width="70%" />
    
   Obs. Caso encontre ero na instalação, atualize a versão do pfSense no menu: 
    
   System ➡️ Update
    
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/439a3b1bb6390363cd98a118d0d517994f7452ba/imagens/configurando_snort/snort03.png" width="70%"/>
    
   Após instalado, o Snort deve ser configurado para fazer a detecção de tráfego malicioso(possível ataque e ameaças). 
    
   **Siga as instruções da documentação original para essa configuração de acordo com a sua estrutura de rede:** 
    
   [Packages — IDS / IPS — Configuring the Snort Package | pfSense Documentation](https://docs.netgate.com/pfsense/en/latest/packages/snort/setup.html)
    
   Neste projeto o Snort está configurado na Interface de Internet(WAN). **Clique no play para ativar.** 
    
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/439a3b1bb6390363cd98a118d0d517994f7452ba/imagens/configurando_snort/snort04.png" width="70%"/>
    
   É possível habilitar todas as regras no Snort através fo submenu **INTER Categorias,** escolhendo a que melhor atende a proteção da sua rede/aplicação. 
    
   Também é possível criar uma regra customizada no submenu **INTER Rules.** 
    
   Neste projeto foi criado uma regra de Alerta para tentativa de ping na aplicação Web: 
   
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/439a3b1bb6390363cd98a118d0d517994f7452ba/imagens/configurando_snort/snort05.png" width="70%"/>
    
   **Para fazer o teste, acesse o terminal da máquina host e faça um ping para o IP Virtual do WAF. E veja os alertas no menu conforme imagem abaixo:**
    
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/439a3b1bb6390363cd98a118d0d517994f7452ba/imagens/configurando_snort/snort06.png" width="70%"/>
    
   No Graylog já é possível analisar o alerta configurado. 
