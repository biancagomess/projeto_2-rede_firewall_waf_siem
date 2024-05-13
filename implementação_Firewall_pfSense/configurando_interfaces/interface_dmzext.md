- **Interface DMZEXT**
    
    Configurando o WAF
    
    Crie uma nova máquina virtual com a .iso Debian, nesse projeto está com o nome **WAF_machine**, e siga as orientações dessas documentações para instalar o Nginx ModSecurity: 
    
    [NGINX ModSecurity WAF](https://docs.nginx.com/nginx-waf/)
    
    [How to Install ModSecurity for Nginx on Debian/Ubuntu](https://www.tecmint.com/install-modsecurity-nginx-debian-ubuntu/)
    
    Configure a rede na DMZEXT:
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2027.png)
    
    Ligue a máquina e atribua um IP com essas instruções:
    
    No terminal, abre o arquivo de configuração do Nginx com o seguinte comando: 
    
    ```bash
    nano /etc/nginx/nginx.conf
    ```
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2028.png)
    
    Para enviar os logs do WAF ao Graylog, configurar esse arquivo com os seguintes dados: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2029.png)
    
    Informando o endereço **IP do Graylog** com a **porta** padão **UDP 1514**.
    
    Salve o arquivo com **CRTL + 0**. 
    
    No terminal digite o comando: 
    
    ```bash
    nginx -t #verifica se a sintaxe está correta
    nginx -s realod #recarrega as configurações do nginx
    ```
    
    <aside>
    💡 O WAF e o Graylog estão em DMZs diferentes, sendo assim o firewall bloqueia o tráfego, e não é possível enviar os logs apenas com essa configuração, nesse caso é necessário criar uma regra no firewall.
    
    </aside>
    
    No menu: 
    
    **Firewall ➡️ [Rules](http://192.168.56.2/firewall_rules.php) ➡️ [DMZEXT](http://192.168.56.2/firewall_rules.php?if=opt2)**
    
    Configure a regras para liberar o acesso do WAF ao Graylog, para enviar os logs através do protocolo UDP: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2030.png)
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2031.png)
    
    **Salve e aplique as mudanças.**
    
    Na prática o sevidor não está hospedado, porém é possível simular o acesso para ver o envio dos logs do WAF para o Graylog, pois ele está na linha de frente da rede, recebendo todas as requisições de origem da internet/clientes. Mas a rede ainda não reconhece o IP do WAF sendo assim deve ser criado um IP virtual e realizar o NAT. 
    
    [Criando IP virtual e realizando NAT - WAF](https://www.notion.so/Criando-IP-virtual-e-realizando-NAT-WAF-93024a647e7e4c39b264b6f9e5afe2a6?pvs=21)
    
    No browser, na barra de pesquisa **informe o IP  virtual criado para o WAF** e veja o acesso à página do padrão do Nginx: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2032.png)
    
    No Graylog já é possível identificar os logs enviados pelo WAF:
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2033.png)
    
    Para implementar mais segurança a rede, é necessário o uso de um IDS/IPS para detectar tráfego malicioso e realizar ações de bloqueio, pois somente o WAF não oferece uma proteção abrangente. 
