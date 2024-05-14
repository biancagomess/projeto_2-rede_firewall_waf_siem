<h1>Interface DMZEXT</h1>
    
   **Configurando o WAF**
    
   Crie uma nova máquina virtual com a .iso Debian, nesse projeto está com o nome **WAF_machine**, e siga as orientações dessas documentações para instalar o Nginx ModSecurity: 
    
   [NGINX ModSecurity WAF](https://docs.nginx.com/nginx-waf/)
    
   [How to Install ModSecurity for Nginx on Debian/Ubuntu](https://www.tecmint.com/install-modsecurity-nginx-debian-ubuntu/)
    
   Configure a rede na DMZEXT:
    
   ![interface_dmzext01](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a622bf803f6908b4aac03f16e98901337a3ef49c/imagens/configurando_interfaces/iface_dmzext.png)
    
   Ligue a máquina e atribua um IP com essas instruções:
    
   No terminal, abre o arquivo de configuração do Nginx com o seguinte comando: 
    
   ```bash
   nano /etc/nginx/nginx.conf
   ```
    
   ![interface_dmzext01](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/9c8a2fce0ea0a40f756d457b62012df8f222ee12/imagens/configurando_interfaces/iface_dmzext01.png)
    
   Para enviar os logs do WAF ao Graylog, configurar esse arquivo com os seguintes dados: 
    
   ![interface_dmzex02](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/9c8a2fce0ea0a40f756d457b62012df8f222ee12/imagens/configurando_interfaces/iface_dmzext02.png)
    
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
    
   ---
  
   No menu: 
    
   **Firewall ➡️ [Rules](http://192.168.56.2/firewall_rules.php) ➡️ [DMZEXT](http://192.168.56.2/firewall_rules.php?if=opt2)**
    
   Configure a regras para liberar o acesso do WAF ao Graylog, para enviar os logs através do protocolo UDP: 
    
   ![iface_dmzext03](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a622bf803f6908b4aac03f16e98901337a3ef49c/imagens/configurando_interfaces/iface_dmzext03.png)
    
   ![iface_dmzext04](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a622bf803f6908b4aac03f16e98901337a3ef49c/imagens/configurando_interfaces/iface_dmzext04.png)
    
   **Salve e aplique as mudanças.**
  
   ---
  
   Na prática o sevidor não está hospedado, porém é possível simular o acesso para ver o envio dos logs do WAF para o Graylog, pois ele está na linha de frente da rede, recebendo todas as requisições de origem da internet/clientes. Mas a rede ainda não reconhece o IP do WAF sendo assim deve ser criado um IP virtual e realizar o NAT. 
    
   [Criando IP virtual e realizando NAT - WAF](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/cfd3f01e4cbc7d5e6cfd95fb47af2c14535d0b3b/implementa%C3%A7%C3%A3o_Firewall_pfSense/Criando%20IP%20virtual%20e%20realizando%20NAT%20-%20WAF.md)
    
   No browser, na barra de pesquisa **informe o IP  virtual criado para o WAF** e veja o acesso à página do padrão do Nginx: 
    
   ![iface_dmext05](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a622bf803f6908b4aac03f16e98901337a3ef49c/imagens/configurando_interfaces/iface_dmzext05.png)
    
   No Graylog já é possível identificar os logs enviados pelo WAF:
    
   ![iface_dmext06](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a622bf803f6908b4aac03f16e98901337a3ef49c/imagens/configurando_interfaces/iface_dmzext06.png)
    
   Para implementar mais segurança a rede, é necessário o uso de um IDS/IPS para detectar tráfego malicioso e realizar ações de bloqueio, pois somente o WAF não oferece uma proteção abrangente. 
