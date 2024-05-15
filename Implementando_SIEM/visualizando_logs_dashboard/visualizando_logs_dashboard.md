<h1>Melhorando a visualização dos logs no Graylog:</h1>

No Graylog é possível criar modos **extractor** para facilitar a visulização dos logs, para isso faça uma pesquisa no input por **"ModSecurity"**. 

- Selecione um dos logs;
- Clique no log;
- Selecione: Create extractor;
- Selecione: regular expression (regex);
  
<h2>Extractors com regex: </h2>

- Extrai a data:

```
^.*nginx:(.*)\[error\].*$

```

- Extrai o ip do cliente:

```
^.*\[client\ (.*)\] ModSecurity.*$

```

- Extrai o id da regra:

```
^.*\[id\ \"(\d*)\"\]\ \[rev.*$

```


- Extrai o arquivo do ataque:

```
^.*\[file\ \"(.*)"]\ \[line.*$

```

- Extrai o arquivo o hostname:

```
^.*\[hostname\ \"(.*)"\]\ \[uri.*$

```

- Extrai a severidade da vulnerabilidade:

```
^.*\[severity\ \"(.*)"\]\ \[ver.*$

```

Condition: Only attempt extraction if field matches regular expression

Store as field: "ModSecurity"

Extraction strategy: Copy

Extractor title: Threat Time do WAF

<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/58382573-82de-4a1e-8101-ae141fe1c0d6" width="70%"/>
</div>

<h3>Extractors criados:</h3>
<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/830c8a3b-3eae-4525-8cb1-2ff39398e808" width="70%"/>
</div>

<h3>Log com os extractors:</h3>
<div align="center">
<img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/a150cda4-22bf-49c0-bb79-048dd171ecf0" width="70%"/>
</div>

Assim, fica mais fácil analisar as informações nos logs. 

<h2>Extractor com Grok pattern</h2>

Com o Grok pattern é mais fácil a criação dos extractors, sendo possível consultar a documentação padrão [aqui](https://docs.netgate.com/pfsense/en/latest/monitoring/logs/raw-filter-format.html)

***Neste projeto ele foi utilizado para os logs do pfSense que possuem por padrão o filterlog.***

- Faça uma pesquisa no input por **"filterlog"**;
- Selecione um log;
- Clique na mensagem;
- Create extrector;
- Insira o grok patterns(observando a documetação):
 ```
: %{BASE10NUM:rule},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{WORD:iface},%{DATA:UNWANTED},%{WORD:action},%{WORD:direction},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{DATA:UNWANTED},%{WORD:protocol},%{DATA:UNWANTED},%{IPV4:srcip},%{IPV4:dstip},%{BASE10NUM:srcport},%{BASE10NUM:dstport}   
```
- Teste o exemplo;
- Condition: Only attempt extraction if field contains string
- Field contains string: filterlog
- Extraction strategy: Copy
- title: (nome que desejar)
  
<h3>Log com extractor grok pattern:</h3>

![image](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/7e1ff85f-c896-469e-8932-ef6eaded8efd)

