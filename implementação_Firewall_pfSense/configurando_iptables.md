- Segurança em camadas
    
    Para melhorar a segurança da rede, neste projeto foi implemento a segurnaça em camadas, configurado um firewall de kernel Linux o Netfilter(iptables), um firewall de linha de comando, que pode ser melhor entendido pela documentação original: 
    
    [netfilter/iptables project homepage
          -
        The netfilter.org "iptables" project](https://netfilter.org/projects/iptables/index.html)
    
    Antes da instalação do iptables, é necessário configurar uma regra no firewall para que as máquinas tenha acesso à internet e possam ser atualizadas: 
    
    **Na interface DMZ foi criado a regra de acesso para o IP do Graylog:**
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2048.png)
    
    Clique em **Save e aplique as alterações.** 
    
    **Instalando o iptables:** 
    
    Acesse a máquia via ssh ou direto no terminal digite os comandos. 
    
    **Via ssh:** 
    
    No terminal do pfSense escolha a digite **ssh user@172.16.10.12** IP do Graylog. 
    
    Informe a senha. 
    Aceite a conexão: **YES**
    
    Digite o comando: **su -** (para acesso como root)
    
    Digite **os seguintes comandos** para prosseguir com a instalação: 
    
    ```bash
    **apt update**
    ```
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2049.png)
    
    ```bash
    **apt install iptables-persistent
    #digite YES para as opções;**
    ```
    
    Verifique as regras padrões no iptables: 
    
    ```bash
    iptables -nvL
    ```
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2050.png)
    
    Para mais informações sempre a documentação: 
    
    [2.6. IPTables Red Hat Enterprise Linux 6 | Red Hat Customer Portal](https://access.redhat.com/documentation/pt-br/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-iptables)
    
    [Outros módulos do iptables](https://guiafoca.org/guiaonline/seguranca/ch05s06.html)
    
    Crie regras para aceitar as conexões já estabelecidas para a saída dos pacotes e para um destino específico, no terminal digite as seguintes regras: 
    
    ```bash
    iptables -**A** OUTPUT -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT #conexões já estabelecidas
    
    iptables -I OUTPUT 1 -d 172.16.10.12 -j ACCEPT #aceita a saída de pacotes para o gateway interface DMZ
    
    iptables -I OUTPUT 3 -d 172.16.10.1/24 -j DROP #impede o acesso de atacantes a outras máquinas na rede
    ```
    
    Com essas configurações é garantido a comunicação com o firewall e a segurança em camadas, ficando as regras da seguinte forma:
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2051.png)
    
    Salve as regras no seguinte caminho de arquivo de configurações: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2052.png)
