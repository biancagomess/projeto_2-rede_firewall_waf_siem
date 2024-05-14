# Configurando as portas de acesso ao firewall Pfsense

Para mitigar portas abertas desnecessariamente, utilizamos a customização de portas no menu: 

**Firewall ➡️ Aliases ➡️ Ports** 

Clique em **Add⤴️** e insira as configurações para customizar as portas a serem usadas na regra padrão da interface Intranet. 
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/9913a3122571281664526298aeb3b54b268346cc/imagens/configurando_portas_acesso_firewall_pfsense/config_portas_admin01.png" width="70%" />

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/9913a3122571281664526298aeb3b54b268346cc/imagens/configurando_portas_acesso_firewall_pfsense/config_portas_admin02.png" width="70%"/>

Retorne nas regras da Interface Intranet: 

**Firewall ➡️ [Rules](http://192.168.56.10/firewall_rules.php) ➡️ [INTRANET](http://192.168.56.10/firewall_rules.php?if=lan)**
