<h2>Implementando um SIEM para monitoramento de eventos:</h2>
    
   Este projeto usa Graylog como ferramenta de SIEM para centralização dos logs. 
    
   Para configurar o Graylog, crie uma máquina virtual no VirtualBox usando a .iso do Debian ou outra distro que você preferir utilizar e siga as instruções no próprio site do [Graylog](https://go2docs.graylog.org/5-0/downloading_and_installing_graylog/debian_installation.htm).  
    
   Após a máquina virtual do Graylog criada, inicie e entre com as credenciais informadas no momento da instalação. 
    
   **Configure a rede da máquina da seguinte forma:** 
    
   ![rede_graylog01](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/rede_graylog01.png)
    
**Ligue a máquina e atribua um IP com essas instruções:**

---
   [Configurando IP na máquina ](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/configs_iniciais_Virtualbox/configurando_IP_na_ma%CC%81quina.md)
    
   Irá abrir um arquivo de configuração, informe o endereço de IP da máquina, nesse projeto é o: 
    **172.16.10.12 (mesma rede que a interface DMZ).**

---

O Graylog está configurado, porém não é possível ter acesso a ele, pois a intranet não está na mesma rede, assim a intranet não reconhece o IP do Graylog, nesse caso é necessário realizar uma tradução de IP usando o NAT e essa configuração é feita no pfSense. 

---
   [Criando IP virtual e realizando NAT - Graylog](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/implementa%C3%A7%C3%A3o_Firewall_pfSense/Criando%20IP%20virtual%20e%20realizando%20NAT%20-%20Graylog.md)

---

  O Graylog por padrão usa a port 9000, dessa forma é preciso verificar quais são as portas ativas no Graylog, indo no terminal do Graylog, digite o comando: 
    
```bash
 ss -nlt
```
    
![ip_porta_graylog02](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/porta_udp_graylog06.png)
    
Confirme o IP do Graylog com a porta padrão. 
    
   Para que haja comunicação entre Intranet e Graylog, será necessário ainda configurar o pfSense para permitir o tráfego  que chega no IP do Graylog e porta 9000. 
    
   Vá ao **firewall**, na interface **Intranet** e aplique as seguintes configurações conforme a imagem: 
    
   ![regra_graylog_pfsense03](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/regra_graylog_pfsense03.png)
   
   ![regra_graylog_pfsense04](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/regra_graylog_pfsense04.png)
    
   Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 
    
   **Verifique como fica as regras na interface Intranet:**
    
   ![conferindo_regras_graylog05](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/conferindo_regras_graylog05.png)
    
   Graylog já está autorizado para ser acessado. 
    
   No navegador, digite o IP traduzido via NAT para acessar o Graylog: **192.168.56.12:9000**
    
   Insira as credenciais de acesso criadas. 
    
   Para o envio de logs do firewall ao Graylog configuramos nesse projeto a opção de Logs remotos, no seguinte caminho: 
    
   Status ➡️ System Logs ➡️ Settings ➡️ Remote Logging Options
    
   <aside>
    💡 Obs. O envio dos logs para o Graylog é através do protocolo UDP, nesse caso ao informar o IP do Graylog será necessário inserir a porta UDP padrão que é 1514, conforme imagem abaixo:
    </aside>
    
   Para verificar a porta, insira esse comando no terminal da máquina Graylog: 
    
   ```jsx
   ss -nlu //mostra as portas UDP
   ```
    
   ![porta_udp_graylog06](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/porta_udp_graylog06.png)
    
     
    
   Em seguida prossiga com a configuração dos logs remotos no firewall: 
    
   ![log_remotos_graylog07](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/log_remotos_graylog07.png)
    
   Selecione quais tipos de log deseja enviar para ser gerenciado, nesse projeto somente os logs do firewall. 
    
   Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 
    
   No página do Graylog já é possível verificar os logs, quando selecionado uma opção de updating em tempo escolhido. 
    
   ![verificando_logs_graylog08](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/f71aaa1b33e78052115e7d43c6213d3944d47ac1/imagens/configurando_siem/verificando_logs_graylog08.png)
