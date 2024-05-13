# Criando IP virtual e realizando NAT - Graylog

**IP virtual Graylog**

No menu  **Firewall ➡️ [NAT](http://192.168.56.10/firewall_nat.php) ➡️ [1:1](http://192.168.56.10/firewall_nat_1to1.php)**

Clique em **+Add ⤴️ para adicionar o IP que será traduzido.** 

![Untitled](Criando%20IP%20virtual%20e%20realizando%20NAT%20-%20Graylog%208fa28b93d7f6405cb702880ce6804f07/Untitled.png)

Na imagem acima foi configurado o IP do Graylog **172.16.10.12** na mesma rede da intranet **192.168.56.12,** através do **NAT (Network Address Translation).** 

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

Em seguida é necessário criar um IP virtual para o IP que foi traduzido pelo NAT, pois o IP ainda não existe na rede:

**Firewall ➡️ Virtual IPs**

![Untitled](Criando%20IP%20virtual%20e%20realizando%20NAT%20-%20Graylog%208fa28b93d7f6405cb702880ce6804f07/Untitled%201.png)

Após tudo configurado, clique em **Save** e depois em **Apply Changes.** 

Pronto! Retorne