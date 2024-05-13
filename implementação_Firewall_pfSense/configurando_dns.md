- **Configurando regra de DNS para resolução de endereços:**
    
    Na interface **DMZ**, **adicione** mais uma **regra para consulta DNS**: 
    
    ![configure_regra_dns](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7705a063117b6af8bb3d4eb1106ab815174abbe2/imagens/configurando_dns/configure_regra_dns.png)
    
    **Salve e aplique as alterações.**
    
    No terminal da máquina do servidor digite o seguinte comando: 
    
    ```bash
    nano /etc/resolv.conf
    ```
    
    No arquivo informe as seguintes configurações: 
    
    nameserver 1.1.1.1
    
    nameserver 1.0.0.1
    
    Grave as alterações **Ctrl + o**
