# Criando IP virtual e realizando NAT - WAF

**IP virtual WAF**

No menu  **Firewall ➡️ [NAT](http://192.168.56.10/firewall_nat.php) ➡️ [1:1](http://192.168.56.10/firewall_nat_1to1.php)**

Clique em **+Add ⤴️ para adicionar o IP que será traduzido.** 

![ip_virtual_nat_waf01](https://github.com/biancagomess/projeto_2_rede_firewall_WAF_SIEM/blob/main/imagens/configurando_ip_virtual_nat/ip_virtual_nat_waf01.png)

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

![ip_virtual_nat_waf02](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/8ceadf0a53055e218ac847840b160ae64ed1d75f/imagens/configurando_ip_virtual_nat/ip_virtual_nat_waf02.png)


Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

Pronto! Retorne na sessão de configuração da DMZEXT.

