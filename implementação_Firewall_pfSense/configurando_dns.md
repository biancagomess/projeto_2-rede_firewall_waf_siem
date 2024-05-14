<h1>Configurando DNS</h1>
    
**Neste projeto utiliza o DNS da cloudflare**
      
   No terminal da máquina do servidor digite o seguinte comando: 
    
   ```bash
   nano /etc/resolv.conf
   ```
    
   No arquivo informe as seguintes configurações: 
    
   nameserver 1.1.1.1
   nameserver 1.0.0.1
    
   Grave as alterações **Ctrl + o**
