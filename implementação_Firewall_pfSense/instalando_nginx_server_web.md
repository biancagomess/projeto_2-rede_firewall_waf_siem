<h1>Instaladno Nginx no servidor Web:</h1>

**Neste projeto utiliza o DNS da cloudflare**
      
No terminal da máquina do servidor digite o seguinte comando: 
    
   ```bash
   nano /etc/resolv.conf
   ```

No arquivo digite as seguintes configurações: 
    
nameserver 1.1.1.1 

nameserver 1.0.0.1
    
   Grave as alterações **Ctrl + o**

No terminal do Server_Web (servidor), digite o comando de atualização dos pacotes: 
```
  apt update
```

Caso haje alguma falha digite esse comando, para exclusão de configurações padrão: 

```
  rm /etc/apt/apt.conf
```

Repita o comando de atualização: apt update; 

Instale o nginx

```
apt install nginx
```
Verifique a instalação e a versão: 
```
nginx -v
```
Reinicie a máquina nginx e aplique as configurações realizadas:
```
systemctl enable nginx #habilita o nginx
systemctl restart nginx #ativa as configurações no nginx
```

**Nginx configurado.**

