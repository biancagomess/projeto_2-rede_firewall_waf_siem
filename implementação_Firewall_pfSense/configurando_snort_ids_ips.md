- Configurar IDS/IPS - Snort
    
    No pfSense no menu: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2042.png)
    
    Instale o pacote do Snort. 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2043.png)
    
    Obs. Caso encontre ero na instalação, atualize a versão do pfSense no menu: 
    
    System ➡️ Update
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2044.png)
    
    Após instalado, o Snort deve ser configurado para fazer a detecção de tráfego malicioso(possível ataque e ameaças). 
    
    **Siga as instruções da documentação original para essa configuração de acordo com a sua estrutura de rede:** 
    
    [Packages — IDS / IPS — Configuring the Snort Package | pfSense Documentation](https://docs.netgate.com/pfsense/en/latest/packages/snort/setup.html)
    
    Neste projeto o Snort está configurado na Interface de Internet(WAN). **Clique no play para ativar.** 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2045.png)
    
    É possível habilitar todas as regras no Snort através fo submenu **INTER Categorias,** escolhendo a que melhor atende a proteção da sua rede/aplicação. 
    
    Também é possível criar uma regra customizada no submenu **INTER Rules.** 
    
    Neste projeto foi criado uma regra de Alerta para tentativa de ping na aplicação Web: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2046.png)
    
    **Para fazer o teste, acesse o terminal da máquina host e faça um ping para o IP Virtual do WAF. E veja os alertas no menu conforme imagem abaixo:**
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2047.png)
    
    No Graylog já é possível analisar o alerta configurado. 
