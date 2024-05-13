
- **Interface Intranet**
    
    Ao acessar a interface Intranet é possível verificar a presença de uma regra padrão do próprio pfSense. essa regra é criada automaticamente durante a configuração inicial do pfSense e é projetada para garantir que os administradores não sejam acidentalmente bloqueados de acessar o painel de controle web do pfSense. 
    
    ![iface_intranet01](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5e09d7c53b2e280eed210c8bbc1a96939c20dbcb/imagens/configurando_interfaces/iface_intranet01.png)
    
    Essa regra pode ser editada para adaptar a configuração de cada rede. 
    Nesse projeto foi criado uma nova regra e desabilitada a regra padrão, para liberar tráfego HTTP, HTTPS  nas portas Web 80 e 443 e SSH para à administração o acesso remoto ao firewalll caso necessário. 
    
    **Siga essas instruções para configuração das portas de acesso autorizadas:**
    
    [Configurando as portas de acesso ao firewall Pfsense](https://www.notion.so/Configurando-as-portas-de-acesso-ao-firewall-Pfsense-c8cb2345835b47328ad082c64e66c6d1?pvs=21)
    
     
    Clique no ⤴️Add, e adicione a nova regra, nos campos **Destination Port Range,** insira no input **Custom** a variável criada com as portas autorizadas, no caso deste projeto: **PORTAS_ADMIN_AUTORIZADAS.**  
      
    
    ![iface_intranet02](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5e09d7c53b2e280eed210c8bbc1a96939c20dbcb/imagens/configurando_interfaces/iface_intranet02.png)
    
    Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 
    
    ![iface_intranet03](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5e09d7c53b2e280eed210c8bbc1a96939c20dbcb/imagens/configurando_interfaces/iface_intranet03.png)
    
