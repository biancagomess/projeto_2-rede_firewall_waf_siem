# Configurando IP na máquina

No terminal digite o seguinte comando: 

```bash
nano /etc/network/interfaces
```
<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/e17218670af34fbb036d063da8b9e695454c8974/imagens/configurando_ip_na_m%C3%A1quina/comando_interfaces.png" width="70%" />
</div>
**Irá abrir um arquivo de configuração como esse:**

<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/e17218670af34fbb036d063da8b9e695454c8974/imagens/configurando_ip_na_m%C3%A1quina/network_interfaces.png" width="70%"/>
</div>

**Informe o IP da interface que você está configurando, salve o arquivo:** 

```bash
CTRL+O
```

**Depois faça o seguinte comando no terminal para restartar o serviço de rede:** 

```bash
systemctl restart networking.service
```

Verifique a atribuição do IP: 
<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/e17218670af34fbb036d063da8b9e695454c8974/imagens/configurando_ip_na_m%C3%A1quina/verificando_ip.png" width="70%"/>
</div>
<aside>
💡 Obs. Os IPs nas imagens, são para exemplo. É necessário atribuir a cada máquina um IP conforme a sua estrutura de rede.
</aside>
