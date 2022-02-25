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


Os robôs manipuladores são formados por elos e juntas, as quais são movimentadas por atuadores.São robôs bastante utilizados na indústria devido as suas funcionalidades. Caso queira saber um pouco mais

<center>
<img src="{{ 'assets/img/blackthor/manipulador.jpg' | relative_url }}" width="400" text-align=center alt="urdf1" />
</center>


A missão do robô será identificar e acionar um botão de emergência de um armário de metal que estará posicionado sobre a bancada em qualquer posição vertical.

<center>
<img src="{{ 'assets/img/blackthor/missao.jpg' | relative_url }}" width="400" text-align=center alt="urdf1" />
</center>

<center>
<img src="{{ 'assets/img/blackthor/pbs.png' | relative_url }}" width="800" text-align=center alt="urdf1" />
</center>

Dessa forma, alguns dos requisitos previstos para este projeto são desenvolver a simulação do robô, para assegurar testes mais seguros no período de implementação das funcionalidades, projetar ou remodelar o manipulador e seus acessórios utilizando recursos do laboratório, o que será necessário ao confeccionar o suporte para a câmera, a qual será utilizada para reconhecer a tag e o botão de emergência.

Este projeto será desenvolvido utilizando o ROS Noetic no Ubuntu 20.04. E, para reconhecer a tag será acoplada uma câmera webcam da Logitech aplicando o pacote do bir_marker_localization. 

Esta estimada a realização de algumas tarefas como o teste dos motores Dynamixel e a configuração do limite da sua rotação. A calibração da câmera e os testes para reconhecer a tag. E, a implementação das funcionalidades e os testes do funcionamento para cumprir a missão.


{:.center}
[![drawing400](../assets/img/2021-11-19-cmu-rover/The_Stanford_Cart_and_The_CMU_Rover-Juliana-artigo2-20211027.jpg)](../assets/img/2021-11-19-cmu-rover/The_Stanford_Cart_and_The_CMU_Rover-Juliana-artigo2-20211027.jpg)




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
