<h2>Configurando o ambiente no VirtualBox:</h2>

---

1. Baixe e instale o [VirtualBox](https://www.virtualbox.org/wiki/Downloads) no site de acordo com seu sistema operacional;

2. Baixe a .iso do pfSense [aqui](https://www.pfsense.org/download/) (versão 2.7.2, AMD64) e crie a máquina virtual com o nome que desejar, nesse projeto utilizei o nome firewall_pfSense;
   
3. Baixe o Debian  [aqui](https://www.debian.org/download) que será o servidor Web e o WAF e configure de acordo com a documentação.
   
4. Crie as máquinas virtuais seguindo a documentação no próprio site do VirtualBox, ficando assim: 

   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a59d2277c905c7c49a4cd51b3a274a25ca9bfa82/imagens/configurando_ambiente_img/m%C3%A1quinas_virtuais.png" width="70%"/>

---

5. ***Caso tenha alguma dificuldade na criação das máquinas no VirtualBox, siga o*** [Passo a passo para criar máquina virtual(exemplo pfSense): ](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7a0f91bfe5147646560eaf28be88f28e6f13ceca/configs_iniciais_Virtualbox/passo_a_passo_criar_ma%CC%81quina_virtual(exemplo_%20pfSense).md)
   
    
6. **Na máquina virtual do firewall_pfSense,** na sessão de **configurações** ➡️ **rede:** **configure as interfaces** em cada adaptador da seguinte maneira: 

   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a59d2277c905c7c49a4cd51b3a274a25ca9bfa82/imagens/configurando_ambiente_img/rede_pfSense.png" width="70%"/>

7. Nas máquinas virtuais **Server_Web e WAF_machine** configure o adaptador de rede dessa forma: 

   a. Server_Web:  
   <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a59d2277c905c7c49a4cd51b3a274a25ca9bfa82/imagens/configurando_ambiente_img/rede_server_web.png"  width="70%"/>
        
    
    b. WAF_machine:
    
    <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a59d2277c905c7c49a4cd51b3a274a25ca9bfa82/imagens/configurando_ambiente_img/rede_Waf_machine.png" width="70%"/>
    

9. Após configurado as interfaces, desabilite o Servidor DHCP usando o comando `Ctrl + H` .
    
    <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/a59d2277c905c7c49a4cd51b3a274a25ca9bfa82/imagens/configurando_ambiente_img/desable_dhcp.png" width="70%"/>
    

10. Inicie as máquinas virtuais;
    
11. Configure o IP em cada máquina virtual (neste projeto está configurado da seguinte forma): 

    - Internet: IPv4 DHCP (placa em modo Bridge);
    - Server_Web: IPv4 estático: 172.16.10.10/24;
    - Graylog: IPv4 estático: 172.16.10.12/24;
    - WAF: IPv4 estático: 172.16.20.12/24;
---
**Siga essas orientações para atribuir IP na máquina:**

[Configurando IP na máquina](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/931ea57300d9dfa1b0a3cf5a42322f7c9e4465b6/configs_iniciais_Virtualbox/configurando_IP_na_ma%CC%81quina.md) 
