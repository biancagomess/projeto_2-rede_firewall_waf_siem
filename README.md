<h1 align="center">2° Projeto Prático - Segurança da Informação</h1>
<h5 align="center">Programa Desenvolve - Grupo Boticário</h5>

<div>
  <p> No cenário da segurança cibernética, projetar e implementar uma solução abrangente de segurança de rede se tornou crucial. 
Este projeto propõe a concepção e execução de segurança de rede, incorporando elementos-chave como firewall, Web Application Firewall (WAF)  com Nginx ModSecurity e um Sistema de Informações e Eventos de Segurança (SIEM). A implementação eficaz dessa solução envolve não apenas a configuração técnica dos dispositivos de segurança, mas também a definição de políticas de segurança robustas, a detecção proativa e resposta a ameaças em tempo real, bem como a criação de painéis de monitoramento para fornecer insights valiosos sobre a postura de segurança da rede.</p>
</div>

<div align="center">
  
![interfaces_configuradas](https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/7dcaeb101b06428af1c3831245cbf3c6458aa5eb/imagens/configurando_ambiente_img/todas_interfaces_pfSense.png)
</div>


<div align="center">
  <div style="display: flex; flex-direction: row;">
    <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/e899a3a7-b862-4fa2-be20-fbaff7dea9de" width="50%"/>
    <img src="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/assets/81443381/6631f662-0324-409a-84b9-0dc88a19e348" width="50%"/>
  </div>
</div>


---
<span>Etapas do projeto de acordo com o proposto no desafio pelo programa Desenvolve Boticário em parceria com a Alura:</span>
<ul>
  <li> <a href="Planejamento de Segurança/Planejamento de Segurança.md">Planejamento de Segurança: Defina requisitos de segurança, objetivos e políticas.</a>
  </li>
  <br>
  <li> <a href="configs_iniciais_Virtualbox/configurando_ambiente_virtualbox.md">Configurando o ambiente.</a></li>
   <br>
  <li> <a href="implementação_Firewall_pfSense/implementando-firewall-pfSense.md">Implementação de Firewall: Configure um firewall para proteger a rede.</a></li>
   <br>
  <li> <a href="https://github.com/biancagomess/projeto_2_rede_firewall_WAF_SIEM/blob/main/implementa%C3%A7%C3%A3o_Firewall_pfSense/configurando_interfaces/interface_dmzext.md">Configuração de WAF: Configure um WAF para proteger aplicativos web.</a></li>
   <br>
  <li><a href="https://github.com/biancagomess/projeto_2_rede_firewall_WAF_SIEM/blob/a3c2fdaf93930f2c1885e830a0d8340e91d24bdf/Implementando_SIEM/implemantando_SIEM.md"> Implementação de SIEM: Implemente um SIEM para monitorar eventos de segurança.</a></li>
   <br>
  <li><a href="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/c20634ee73c2e8b789298ffab7c73c522297e8dc/testando_a_aplica%C3%A7%C3%A3o/testando_a_aplicacao.md"> Testando a segurança da aplicação.</a></li>
     <br>
  <li><a href="https://github.com/biancagomesalves/projeto_2_rede_firewall_WAF_SIEM/blob/fd5fc023292ff01cc39238d0a13c1e684559d4ba/Implementando_SIEM/visualizando_logs_dashboard/visualizando_logs_dashboard.md"> Facilitando a leitura de logs com dashboard no Graylog </a></li>
  
</ul>

---

<h4>Tecnologias/ferramentas utilizadas:</h4>

- Virtualbox ou outro software de virtualização;
- PfSense .iso versão 2.7.2-realease(amd64);
- Debian .iso;
- Graylog;
- Nginx ModSecurity;
- Snort;
- Netfilter(iptables)
  
---




