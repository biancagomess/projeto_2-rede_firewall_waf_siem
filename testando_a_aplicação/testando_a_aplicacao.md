<h1>Teste de segurança na aplicação e verificação dos logs</h1>
Para realizar o teste, configuramos o servidor web com uma simulação de aplicação que contem algumas vulnerabilidades DVWA;

Realizamos o teste com o atque de SQL Injection: 
![image](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/ed7ff6fd-6400-42f6-8510-7be26515d549)

Recebemos um erro HTTP 403 - Forbiden: 

![image](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/16747735-03b0-448e-8f12-77e72834c636)

Demostrando que não pode ser acesso, pois está priobido. 

**Sendo assim, a nossa aplicação encontra-se segura!**

No Graylog é possível verificar esse bloqueio, fazendo a busca "ModSecurity": 

![image](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/dcd2226c-2e06-4af4-8bbc-8b2bbf05d560)

Esse log, traz todas as informações do bloqueio, como o host, origem e destino, o erro, a severidade do ataque e diversas outras informações. 
