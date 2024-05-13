
1. Na máquina virtual do pfSense (Firewall), configure o IP das interfaces, por padrão o pfSense vem com um IP  (você pode alterar), conforme a sua rede na opção 2 do terminal do pfSense. 
 

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%205.png)

1. Verifique as interfaces configuradas no pfSense:

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%206.png)

1. Após as configurações, abra o browser, e digite o ip do pfSense: 
    
    **http://192.168.56.2**
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%207.png)
    
    Informe o usuário e a senha, que vem por padrão “**admin**” como usuário e “**pfsense**” como senha.
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%208.png)
    

Aceite os termos. 

1. Altere a senha padrão: 
    
    System ➡️ [User Manager](http://192.168.56.10/system_usermanager.php) ➡️  [Users](http://192.168.56.10/system_usermanager.php) ➡️ [Edit](http://192.168.56.10/system_usermanager.php?act=edit&userid=0) (ícone de lápis ✏️ para editar)
    

Acesso seguinte caminho no menu para configurar acesso via ssh ao firewall: 

System ➡️ [Advanced](http://192.168.56.2/system_advanced_admin.php) ➡️ [Admin Access](http://192.168.56.2/system_advanced_admin.php)

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%209.png)

Clique em **Save**

**Verificando as interfaces na página inicial**

Na página inicial verifique as informações do sistema e as interfaces ativas no firewall e o tráfego de rede: 

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2010.png)

1. Configure a DMZEXT onde o WAF será configurado: 
    1. Acesse o menu **Interfaces ➡️ [Interface Assignments](http://192.168.56.10/interfaces_assign.php)**
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2011.png)
    
    **b. Selecione o botão +Add, para adicionar a DMZEXT.** 
    
    c. Adicione as configurações: 
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2012.png)
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2013.png)
    
    Depois clique em **SALVAR e Apply Changes, para aplicar as configurações:**
    
    ![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2014.png)
    

**Todas as interfaces já estão configuradas, e o próximo passo é configurar a regras no firewall pfSense.**

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2015.png)

No menu **System ➡️ [General Setup](http://192.168.56.10/system.php)** é possível criar um domínio, configurar o servidor DNS, hostname, e até escolher um tema, mas no projeto vamos manter o padrão.

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2016.png)

![Untitled](Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246/Untitled%2017.png)

- Implementando regras no Firewall pfSense para permitir e negar tráfego:
    
    <aside>
    💡 **Obs. Vale lembrar que o firewall ler as regras de cima para baixo!**
    
    </aside>
    
    Para criar uma regra acesse no menu: **Firewall ➡️ Rules ➡️ selecione a interface onde irá implementar a regra.** 
    
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
