---
layout: post-page
title: Projeto BLACKTHOR
subtitle: Missão com manipulador
cover-img: /assets/img/blackthor/manipulador3.jpg
thumbnail-img: /assets/img/blackthor/manipulador.jpg
author: Juliana Santana
tags: [blog]
comments: true
---


Os robôs manipuladores são formados por elos e juntas, as quais são movimentadas por atuadores. São robôs bastante utilizados na indústria devido as suas funcionalidades. 

<center>
<img src="{{ 'assets/img/blackthor/open.png' | relative_url }}" width="800" text-align=center alt="urdf1" />
</center>

Neste projeto iremos trabalhar com o OPEN Manipulator Pro, um robô da fabricante Robotis. Ele é baseado no ROS e seu controle pode ser feito usando o pacote do MoveIt!. Inclusive, tem o modelo do robô para ser utilizado no Gazebo {% cite robotis2022 %}.

<center>
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-7ogr{background-color:#464646;border-color:#ffffff;color:#ffffff;text-align:center;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-7ogr">Nome</th>
    <th class="tg-7ogr">OPen Manipulator-PRO</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-7ogr">DOF</td>
    <td class="tg-7ogr">6</td>
  </tr>
  <tr>
    <td class="tg-7ogr">Peso (kg)</td>
    <td class="tg-7ogr">5.5</td>
  </tr>
  <tr>
    <td class="tg-7ogr">Voltage (VDC)</td>
    <td class="tg-7ogr">24</td>
  </tr>
  <tr>
    <td class="tg-7ogr">Dynamixel PRO</td>
    <td class="tg-7ogr">H54P-200-S500-R x2<br>H54P-100-S500-R x2<br>H42P-20-S300-R x2</td>
  </tr>
  <tr>
    <td class="tg-7ogr">Software</td>
    <td class="tg-7ogr">ROS (Ubuntu Linux)</td>
  </tr>
  <tr>
    <td class="tg-7ogr">Controle</td>
    <td class="tg-7ogr">PC</td>
  </tr>
</tbody>
</table>

</center> 


A missão do robô será identificar e acionar um botão de emergência de um armário de metal que estará posicionado sobre a bancada em qualquer posição vertical.

<center>
<img src="{{ 'assets/img/blackthor/missao.jpg' | relative_url }}" width="400" text-align=center alt="urdf1" />
</center>

Dessa forma, alguns dos requisitos previstos para este projeto são desenvolver a simulação do robô para assegurar testes mais seguros no período de implementação das funcionalidades. E, projetar ou remodelar o manipulador e seus acessórios utilizando recursos do laboratório, o que será necessário ao confeccionar o suporte para a câmera, a qual será utilizada para reconhecer a tag e o botão de emergência.

<center>
<img src="{{ 'assets/img/blackthor/pbs.png' | relative_url }}" width="800" text-align=center alt="urdf1" />
</center>

Este projeto será desenvolvido utilizando o ROS Noetic no Ubuntu 20.04. E, para reconhecer a tag será acoplada uma câmera webcam da Logitech e aplicado o pacote do bir_marker_localization. 

Esta estimada a realização de algumas tarefas como o teste dos motores Dynamixel e a configuração do limite da sua rotação. Será feita a calibração da câmera e os testes para reconhecer a tag. E, a implementação das funcionalidades e os testes do funcionamento para cumprir a missão.

Caso tenha interesse, continue acompanhando pois mais informações sobre estas tarefas serão atualizadas aqui na página.


<br>

### Referências

<div style="text-align: left">
  {% bibliography --cited %}
</div>

<br>

<!-- #### Footnotes

* footnotes will be placed here. This line is necessary
{:footnotes}

<br> -->

<hr>
<!-- autor -->
<center><h3 class="post-title">Autora</h3><br/></center>
<div class="row">
<div class="col-xl-auto offset-xl-0 col-lg-4 offset-lg-0 center">
  <table class="table-borderless highlight">
    <thead>
      <tr>
        <th><img src="{{ 'assets/img/people/juliana-1.png' | relative_url }}" width="100" alt="juliana" class="img-fluid rounded-circle" /></th>
      </tr>
    </thead>
    <tbody>
      <tr class="font-weight-bolder" style="text-align: center margin-top: 0">
        <td>Juliana Santana</td>
      </tr>
      <tr style="text-align: center" >
        <td style="vertical-align: top"><small>Pesquisadora Jr. do projeto <br>Engenheira Eletricista.</small></td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>
</div>
