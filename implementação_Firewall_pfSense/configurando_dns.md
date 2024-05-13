- **Configurando regra de DNS para resolução de endereços:**
    
    Na interface **DMZ**, **adicione** mais uma **regra para consulta DNS**: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2053.png)
    
    **Salve e aplique as alterações.**
    
    No terminal da máquina do servidor digite o seguinte comando: 
    
    ```bash
    nano /etc/resolv.conf
    ```
    
    No arquivo informe as seguintes configurações: 
    
    nameserver 1.1.1.1
    
    nameserver 1.0.0.1
    
    Grave as alterações **Ctrl + o**
