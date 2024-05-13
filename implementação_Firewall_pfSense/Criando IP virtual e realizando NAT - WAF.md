# Criando IP virtual e realizando NAT - WAF

**IP virtual Graylog**

No menu  **Firewall ➡️ [NAT](http://192.168.56.10/firewall_nat.php) ➡️ [1:1](http://192.168.56.10/firewall_nat_1to1.php)**

Clique em **+Add ⤴️ para adicionar o IP que será traduzido.** 

![Untitled](Criando%20IP%20virtual%20e%20realizando%20NAT%20-%20WAF%2093024a647e7e4c39b264b6f9e5afe2a6/Untitled.png)

Na imagem acima foi configurado o IP do WAF **172.16.20.12** na mesma rede da internet **nesse caso o IP da sua rede local (do seu roteador),** através do **NAT (Network Address Translation).** 

Verificando IP disponível na rede: 

No terminal verifique o endereço de IP da sua máquina local (host) com o comando: 

```bash
ifconfig
```

Escolha algum outro IP da rede e faça um ping, caso o ping retorne **Destination Host Unreachable** o IP pode ser utilizado e inserido no input conforme mostrado na imagem. 

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

Em seguida é necessário criar um IP virtual para o IP que foi traduzido pelo NAT, pois o IP ainda não existe na rede:

**Firewall ➡️ Virtual IPs**

![Untitled](Criando%20IP%20virtual%20e%20realizando%20NAT%20-%20WAF%2093024a647e7e4c39b264b6f9e5afe2a6/Untitled%201.png)

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

Pronto! Retorne na sessão de configuração da DMZEXT: 

[Projeto_2 - Firewall, WAF, SIEM](../Projeto_2%20-%20Firewall,%20WAF,%20SIEM%20b9678ece1dc849258656670c38ca7246.md)