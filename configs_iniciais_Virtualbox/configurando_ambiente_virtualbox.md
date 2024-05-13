<h2>Configurando o ambiente no VirtualBox:</h2>

---

1. Baixe e instale o [VirtualBox](https://www.virtualbox.org/wiki/Downloads) no site de acordo com seu sistema operacional;

2. Baixe a .iso do pfSense [aqui](https://www.pfsense.org/download/) (versão 2.7.2, AMD64) e crie a máquina virtual com o nome que desejar, nesse projeto utilizei o nome firewall_pfSense;
   
3. Baixe o Debian  [aqui](https://www.debian.org/download) que será o servidor Web e o WAF e configure de acordo com a documentação.
   
4. Crie as máquinas virtuais seguindo a documentação no próprio site do VirtualBox, ficando assim: 

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled.png)

---

5. ***Caso tenha alguma dificuldade na criação das máquinas no VirtualBox, siga o*** [Passo a passo para criar máquina virtual(exemplo pfSense): ](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7a0f91bfe5147646560eaf28be88f28e6f13ceca/configs_iniciais_Virtualbox/passo_a_passo_criar_ma%CC%81quina_virtual(exemplo_%20pfSense).md)
   
    
6. **Na máquina virtual do firewall_pfSense,** na sessão de **configurações** ➡️ **rede:** **configure as interfaces** em cada adaptador da seguinte maneira: 

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%201.png)

7. Nas máquinas virtuais **Server_Web e WAF_machine** configure o adaptador de rede dessa forma: 

   a. Server_Web:  
        ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%202.png)
        
    
    b. WAF_machine:
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%203.png)
    

9. Após configurado as interfaces, desabilite o Servidor DHCP usando o comando `Ctrl + H` .
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%204.png)
    

10. Ligue as máquinas virtuais;
    
11. Configure o IP em cada máquina virtual (neste projeto está configurado da seguinte forma): 

    - Internet: IPv4 DHCP (placa em modo Bridge);
    - Server_Web: IPv4 estático: 172.16.10.10/24;
    - Graylog: IPv4 estático: 172.16.10.12/24;
    - WAF: IPv4 estático: 172.16.20.12/24;

**Siga essas orientações para atribuir IP na máquina.:**

[Configurando IP na máquina](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7a0f91bfe5147646560eaf28be88f28e6f13ceca/configs_iniciais_Virtualbox/configurando_IP_na_ma%CC%81quina.md)
