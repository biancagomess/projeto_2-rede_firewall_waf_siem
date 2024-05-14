<h2>Implementando o Firewall pfSense</h2>
1. Na máquina virtual do pfSense (Firewall), configure o IP das interfaces, por padrão o pfSense vem com um IP  (você pode alterar), conforme a sua rede na opção 2 do terminal do pfSense. 
 

![interfaces_máquina_pfSense](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/interfaces_pfSense_config.png)

2. Verifique as interfaces configuradas no pfSense:

![exemplo_config_interface_terminal_pfSense](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/interfaces_exemplo_config_pfSense.png)

3. Após as configurações, abra o browser, e digite o ip do pfSense: 
    
    **http://192.168.56.2**
    
    ![login_pfSense](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/login_pfSense.png)
    
    Informe o usuário e a senha, que vem por padrão usuário: “**admin**”, senha:“**pfsense**”.
    
    ![termos_pfSense](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/termos_pfSense.png)
    
Aceite os termos. 

 ---
4. Altere a senha padrão: 
    
    System ➡️ [User Manager](http://192.168.56.2/system_usermanager.php) ➡️  [Users](http://192.168.56.2/system_usermanager.php) ➡️ [Edit](http://192.168.56.10/system_usermanager.php?act=edit&userid=0) (ícone de lápis ✏️ para editar)
   
---    

5. Habilite ssh

    Acesse seguinte caminho no menu para configurar o acesso via ssh ao firewall: 

    System ➡️ [Advanced](http://192.168.56.2/system_advanced_admin.php) ➡️ [Admin Access](http://192.168.56.2/system_advanced_admin.php)

![enable_ssh](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/enable_ssh_pfSense.png)

Clique em **Save**

---


<h2>Verificando as interfaces na página inicial</h2>

Na página inicial verifique as informações do sistema e as interfaces ativas no firewall e o tráfego de rede: 

![verificando_interfaces](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/visualizar_interfaces_pfSense.png)

1. Configure a DMZEXT onde o WAF será configurado: 

   a. Acesse o menu **Interfaces ➡️ [Interface Assignments](http://192.168.56.2/interfaces_assign.php)**
    
    ![adicionando_dmzext](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/add_interface_dmzext.png)
    
    **b. Selecione o botão +Add, para adicionar a DMZEXT.** 
    
    c. Adicione as configurações: 
    
    ![configure_dmzext](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/configure_dmext_pfSense.png)
    
    ![configure_dmzext1](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/configure_dmext_pfSense%202.png)
    
    Depois clique em **SALVAR e Apply Changes, para aplicar as configurações:**
    
    ![apply_changes_dmzext](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/configure_dmext_pfSense%20apply_changes.png)
    
--- 

**Todas as interfaces já estão configuradas, e o próximo passo é configurar a regras no firewall pfSense.**

![interfaces_configuradas](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/todas_interfaces_pfSense.png)

No menu **System ➡️ [General Setup](http://192.168.56.10/system.php)** é possível criar um domínio, configurar o servidor DNS, hostname, e até escolher um tema, mas no projeto vamos manter o padrão.

![demais_configurações](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/demais_configura%C3%A7%C3%B5es_pfSense.png)

![demais_configurações](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/demais_configura%C3%A7%C3%B5es_pfSense%202.png)

<h2>Implementando regras no Firewall pfSense para permitir e negar tráfego:</h2>    
<div>
    <aside>
    💡 Vale lembrar que o firewall ler as regras de cima para baixo!
    </aside>
 </div> 
 -
 
**Para criar uma regra acesse no menu:**
 - **Firewall ➡️ Rules ➡️ selecione a interface onde irá implementar a regra.** 
    
   Neste projeto foi iniciado as **configurações usando a estratégia “deny by default”** (negar por padrão). Essa estratégia envolve configurar um firewall de segurança para bloquear todo o tráfego de entrada e saída por padrão e, em seguida, criar regras específicas para permitir apenas o tráfego necessário para as operações legítimas da aplicação.
    
   Para configurar uma regra, é preciso clicar no botão ⤴️**Add**, e informar as especificações da regra de acordo com a sua rede, como:
   
   - Action  (ação que será realizada);
   - Interface;
   - Tipo de endereço IP (IPv4 / IPv6);
   - Protocolo;
   - Source (origem);
   - Destination (destino);
   - Registro de Logs;
   - Descrição da regra;
    
   **Em todo esse projeto e por boa prática está ativo todos os registros de Log para que seja possível fazer uma melhor análise de tráfego na rede.** 


 <h3>Verificando os logs no firewall</h3>
    
   No Firewall é possível verificar os logs do tráfego de rede e aplicar filtros para uma melhor análise, no seguinte caminho no menu:
    
   **Status ➡️ [System Logs](http://192.168.56.10/status_logs.php) ➡️ [Firewall](http://192.168.56.10/status_logs_filter.php) ➡️ [Dynamic View](http://192.168.56.10/status_logs_filter_dynamic.php?logfile=filter&view=dynamic)**
    
   Para mais detalhes do tráfego da rede, pode ser configurado a captura de pacotes através do acesso em: 
   
   **Diagnostics ➡️ [Packet Capture](http://192.168.56.10/diag_packet_capture.php)**
   
   Insira as configurações que deseja monitorar e clique em **Start,** logo a captura de pacotes será iniciada. Depois para encerrar clica em **Stop.** 
    
