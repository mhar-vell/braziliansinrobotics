---
layout: page
title: Blackthor 
subtitle: Desenvolvendo missão botão
---
{% assign date_format = site.date_format | default: "%B %-d, %Y" %}
{%- capture site_tags -%}
    {%- for tag in site.tags -%}
      {% if tag contains 'doogie' %}
        {{- tag | first -}}{%- unless forloop.last -%},{%- endunless -%}
      {% endif %} 
    {%- endfor -%}
{%- endcapture -%}
{%- assign tags_list = site_tags | split:',' | sort -%}

<div class="before-content">
  <center>
    {%- for tag in tags_list -%}
      <br>
      <a href="#{{- tag -}}" class="btn btn-primary tag-btn"><i class="fas fa-tag" aria-hidden="true"></i>&nbsp;{{- tag -}}-posts&nbsp;({{site.tags[tag].size}})</a>
    {%- endfor -%}
  </center>    
  <!--hr class="mark"-->
</div>


Os robôs manipuladores são utilizados em diversas aplicações como manuseio de materiais, soldagem, montagem, sendo bastante empregados em ambiente industrial de alto risco ou em atividades que exigem precisão de movimentos. Um manipulador robótico é composto por um conjunto de corpos rígidos ligados por juntas.  


O **Blackthor** é um projeto realizado com o manipulador ***OpenMANIPULATOR-P*** (Open Manipulator Pro).

<center>
<img src="{{ 'assets/img/blackthor/openmanipulator_pro.png' | relative_url }}" alt="Dois protótipos construídos" width="200"/><br>
OpenMANIPULATOR-P
</center>

O ***OpenMANIPULATOR-P (RM-P60-RNH)*** é um robô manipulador ***OpenSource*** baseado em ***ROS*** que pode ser controlado pelo pacote ***"MoveIt!"*** e oferece a possibilidade de ser simulado pelo ***Gazebo***, é composto por motores ***DYNAMIXEL-P*** e pode ter suas juntas removidas facilmente.

## Missão

O **Blackthor** precisa acionar um botão de emergência que se encontra em uma caixa, para isso deverá buscar e fazer o reconhecimento de um marcador do tipo ***ArUco*** associado a caixa. A missão deverá ser realizada de forma autônoma.

<center>
<img src="{{ 'assets/img/blackthor/optag.drawio.png' | relative_url }}" alt="Dois protótipos construídos" width="600"/><br>
Estruturação da missão
</center>

<br>

## O sistema robótico
A estruturação da missão a ser realizada pelo **Blackthor** será dividido em quatro blocos básicos, sendo eles **comportamento**, **planejamento**, **percepção**  e **atuação**. O robô irá atuar saindo da posição ***Home*** para ***Posição inicial*** de busca e posteriormente irá iniciar a varredura (busca) pelo marcador, após encontrar o marcador, dará início ao planejamento da trajetória para alcançar o botão de acionamento, a seguir o diagrama de funcionalidades do sistema:   

<center>
<img src="{{ 'assets/img/blackthor/diagrama_funcionalidades.png' | relative_url }}" alt="Dois protótipos construídos" width="750"/><br>
Diagrama de funcionalidades
</center>

### Componentes adicionais

Para que seja possível o cumprimento da missão, alguns componentes foram adicionados a estrutura básica do ***OpenMANIPULATOR-P***: 

#### Hardware
- Raspberry pi 4

<center>
<img src="{{ 'assets/img/blackthor/rasp-removebg.png' | relative_url }}" alt="Dois protótipos construídos" width="350"/><br>
</center>

- Câmera Raspberry Pi v2

<center>
<img src="{{ 'assets/img/blackthor/cameraV2.png' | relative_url }}" alt="Dois protótipos construídos" width="150"/><br>
</center>

O uso de um micro-computador (Raspberry pi 4) no projeto permite a possibilidade de adição de novos sensores, caso seja necessário, além da câmera RGB que será utilizada para o reconhecimento do marcador ***AruCo***.

- Webcam HD Logitech C270

<center>
<img src="{{ 'assets/img/blackthor/c270.png' | relative_url }}" alt="Dois protótipos construídos" width="150"/><br>
</center>

No estágio inicial do projeto foi utilizado a câmera C270 no intuito de simplificar o desenvolvimento do desafio na prática, por se tratar de uma câmera usb, a parte de integração no **ROS** se tornaria mais simples. A funcionalidade de reconhecimento do marcador ***AruCo*** foi realizada com sucesso em ambas as câmeras.

#### Estrutura
- Ferramenta para acionamento do botão

<center>
<img src="{{ 'assets/img/blackthor/peca.png' | relative_url }}" alt="Dois protótipos construídos" width="150"/><br>
</center>

Foi feita a ***modelagem*** e ***impressão 3D*** de uma peça que tem a função de aumentar a área de atuaçao do ***end effector*** do manipulador. O resultado final da montagem pode ser visto na imagem a seguir:

<center>
<img src="{{ 'assets/img/blackthor/mount.jpg' | relative_url }}" alt="Dois protótipos construídos" width="750"/><br>
Blackthor montado
</center>

#### Simulação

A simulação do ***Blackthor*** teve bastante impacto no resultado final do projeto, o teste das funcionalidades foi iniciado em ambiente de simulação, desenvolver o conhecimento inicial necessário no pacote ***Moveit!*** do ***ROS*** permitiu obter resultados mais concretos em ambiente real.
A seguir um exemplo de movimentação do  ***OpenMANIPULATOR-P*** se dirigindo para uma ***Pose*** especificada previamente utilizando o ***Moveit!***:

<center>
<img src="{{ 'assets/img/blackthor/move-to-goal.gif' | relative_url }}" alt="Dois protótipos construídos" width="750"/><br>
Pose to goal
</center>


A missão de reconhecer o marcador **ArUco** e posteriormente acionar o botão de emergência foi concluída com sucesso:

> Realizando a missão do Blackthor:

<div align="center">
<iframe width="620" height="315" src="https://youtu.be/Mp-_eczVI4I" frameborder="0" allowfullscreen></iframe>
</div>