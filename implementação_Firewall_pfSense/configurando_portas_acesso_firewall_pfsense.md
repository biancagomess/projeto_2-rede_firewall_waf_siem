# Configurando as portas de acesso ao firewall Pfsense

Para mitigar portas abertas desnecessariamente, utilizamos a customização de portas no menu: 

**Firewall ➡️ Aliases ➡️ Ports** 

Clique em **+Add** e insira as configurações para customizar as portas a serem usadas na regra padrão da interface Intranet. 

![Untitled](Configurando%20as%20portas%20de%20acesso%20ao%20firewall%20Pfsen%20c8cb2345835b47328ad082c64e66c6d1/Untitled.png)

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

![Untitled](Configurando%20as%20portas%20de%20acesso%20ao%20firewall%20Pfsen%20c8cb2345835b47328ad082c64e66c6d1/Untitled%201.png)

Retorne nas regras da Interface Intranet: 

**Firewall ➡️ [Rules](http://192.168.56.10/firewall_rules.php) ➡️ [INTRANET](http://192.168.56.10/firewall_rules.php?if=lan)**