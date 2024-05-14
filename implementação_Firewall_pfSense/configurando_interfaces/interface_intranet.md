
<h1>Interface Intranet</h1>
    
  Ao acessar a interface Intranet é possível verificar a presença de uma regra padrão do próprio pfSense. essa regra é criada automaticamente durante a configuração inicial do pfSense e é projetada para garantir que os administradores não sejam acidentalmente bloqueados de acessar o painel de controle web do pfSense. 
    
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5e09d7c53b2e280eed210c8bbc1a96939c20dbcb/imagens/configurando_interfaces/iface_intranet01.png" width="70%"/>
    
   Essa regra pode ser editada para adaptar a configuração de cada rede. 
    Nesse projeto foi criado uma nova regra e desabilitada a regra padrão, para liberar tráfego HTTP, HTTPS  nas portas Web 80 e 443 e SSH porta 22, para  administração fazer acesso remoto ao firewalll caso necessário.
  
   ---
   **Siga essas instruções para configuração das portas de acesso autorizadas:**
    
   [Configurando as portas de acesso ao firewall Pfsense](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5deccad9e2f0d8db95765000c37f2aba53e88ba3/implementa%C3%A7%C3%A3o_Firewall_pfSense/configurando_portas_acesso_firewall_pfsense.md)
    
---
   Clique no ⤴️Add, e adicione a nova regra, nos campos **Destination Port Range,** insira no input **Custom** a variável criada com as portas autorizadas, no caso deste projeto: **PORTAS_ADMIN_AUTORIZADAS.**  
          
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5e09d7c53b2e280eed210c8bbc1a96939c20dbcb/imagens/configurando_interfaces/iface_intranet02.png" width="70%"/>
    
   Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 
   
---

---

<h2>Configure regra para comunicação ao Graylog</h2>
    Siga essas orientações nesta sessão: 
    
[Implementando SIEM](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/5deccad9e2f0d8db95765000c37f2aba53e88ba3/Implementando_SIEM/implemantando_SIEM.md)

---


  
    
