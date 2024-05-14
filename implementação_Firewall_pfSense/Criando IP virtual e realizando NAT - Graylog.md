# Criando IP virtual e realizando NAT - Graylog

<h3>IP virtual Graylog</h3>

No menu  **Firewall ➡️ [NAT](http://192.168.56.10/firewall_nat.php) ➡️ [1:1](http://192.168.56.10/firewall_nat_1to1.php)**

Clique em **+Add ⤴️ para adicionar o IP que será traduzido.** 

<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7e47b6db46e3539c6b332cf85abc6c6188898c23/imagens/configurando_ip_virtual_nat/ip_virt_nat_graylog01.png" width="70%"/>

Na imagem acima foi configurado o IP do Graylog **172.16.10.12** na mesma rede da intranet **192.168.56.12,** através do **NAT (Network Address Translation).** 

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

<h3>Criar IP Virtual</h3>
Em seguida é necessário criar um IP virtual para o IP que foi traduzido pelo NAT, pois o IP ainda não existe na rede:


**Firewall ➡️ Virtual IPs**

<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7e47b6db46e3539c6b332cf85abc6c6188898c23/imagens/configurando_ip_virtual_nat/ip_virt_nat_graylog02.png" width="70%"/>

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

Pronto! Retorne
