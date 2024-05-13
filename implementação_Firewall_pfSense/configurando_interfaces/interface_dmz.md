 


- **Interface DMZ**
    
    No menu, navegue até a interface da DMZ, pois é necessário a configuração de regras para autorizar o tráfego nesta interface. Neste projeto é criado a regra de autorização de ping na DMZ. 
    
     **Firewall ➡️ [Rules](http://192.168.56.10/firewall_rules.php) ➡️ [DMZ](http://192.168.56.10/firewall_rules.php?if=opt1) ➡️ [Edit](http://192.168.56.10/firewall_rules_edit.php?if=opt1&after=-1)**
    
    Adicione uma regra de **Pass ping** acima da regra já existente “Deny By Default”, com as seguintes especificações:
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2025.png)
    
    <aside>
    💡 Obs. O protocolo autorizado é o ICMP (usado aqui para teste de conexão - ping), foi liberado somente os types (ECHO request e o ECHO replay). Após essa configuração, caso queira testar se a regra está funcionando, acesse a máquina virtual do servidor **Server_Web**, faça o login com as credenciais que você criou e em seguida realize o seguinte comando no terminal:
    
    </aside>
    
    ```bash
    ping 172.16.10.1 #ip da interface DMZ
    ```
    
    **Verifique o resultado do ping com sucesso:**
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2026.png)
    
