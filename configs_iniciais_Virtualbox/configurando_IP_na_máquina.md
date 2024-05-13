# Configurando IP na máquina

No terminal digite o seguinte comando: 

```bash
nano /etc/network/interfaces
```

![Untitled](Configurando%20IP%20na%20ma%CC%81quina%20a892d5177ab9472f9af47f64832234bd/Untitled.png)

**Irá abrir um arquivo de configuração como esse:**

![Untitled](Configurando%20IP%20na%20ma%CC%81quina%20a892d5177ab9472f9af47f64832234bd/Untitled%201.png)

**Informe o IP da interface que você está configurando, salve o arquivo:** 

```bash
CTRL+O
```

**Depois faça o seguinte comando no terminal para restartar o serviço de rede:** 

```bash
systemctl restart networking.service
```

Verifique a atribuição do IP: 

![Untitled](Configurando%20IP%20na%20ma%CC%81quina%20a892d5177ab9472f9af47f64832234bd/Untitled%202.png)

<aside>
💡 Obs. Os IPs nas imagens, são para exemplo, é preciso atribuir a cada máquina um IP conforme a sua estrutura de rede.

</aside>