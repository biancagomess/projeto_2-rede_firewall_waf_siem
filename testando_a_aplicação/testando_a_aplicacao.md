<h1>Teste de segurança na aplicação e verificação dos logs</h1>
Para realizar o teste, configuramos o servidor web com uma simulação de aplicação que contem algumas vulnerabilidades DVWA;

- Teste com o atque de SQL Injection:
  
  <div align="center">
  <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/ed7ff6fd-6400-42f6-8510-7be26515d549" width="70%"/>
  </div>

Recebemos um erro HTTP 403 - Forbiden:

<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/16747735-03b0-448e-8f12-77e72834c636" width="70%"/>
</div>
Demostrando que não pode ser acessado. 

No Graylog é possível verificar esse bloqueio, fazendo a busca "ModSecurity": 

<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/745a24b3-188d-4cfc-824f-f357459d0532" width="70%"/>
</div>

Esse log, traz todas as informações do bloqueio, como o host, origem e destino, o erro, a severidade do ataque e diversas outras informações. 

---


- Teste com brute force:
  
<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/2f71a010-4e7c-4742-be37-9368b8b2f738" width="70%"/>
</div>

No Graylog é possível verificar esse bloqueio, fazendo a busca "ModSecurity": 

<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/4b7bd1f1-7e11-4eab-bb26-4af6e68764cb"/>
</div>


**Sendo assim, a nossa aplicação encontra-se segura!**


