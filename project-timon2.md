---
layout: page
title: Jax Manipulator
subtitle: Jax@Noetic
---
{% assign date_format = site.date_format | default: "%B %-d, %Y" %}
{%- capture site_tags -%}
    {%- for tag in site.tags -%}
      {% if tag contains 'timon2' %}
        {{- tag | first -}}{%- unless forloop.last -%},{%- endunless -%}
      {% endif %} 
    {%- endfor -%}
{%- endcapture -%}
{%- assign tags_list = site_tags | split:',' | sort -%}

<center><img src="{{ 'assets/img/jax/timao.jpg' | relative_url }}" text-align=center width="500" alt="aperea" /><br></center>

<div class="before-content">
  <center>
    {%- for tag in tags_list -%}
      <br>
      <a href="#{{- tag -}}" class="btn btn-primary tag-btn"><i class="fas fa-tag" aria-hidden="true"></i>&nbsp;{{- tag -}}-posts&nbsp;({{site.tags[tag].size}})</a>
    {%- endfor -%}
  </center>    
  <!--hr class="mark"-->
</div>

 
Braços manipuladores estão cada vez mais presentes na dinâmica humana. No universo da produção automobilística, já é bastante comum notar a presença de robôs manipuladores exercendo várias funções, principalmente pintura e soldagem. Os manipuladores vem ganhando espaço em função de sua alta capacidade de repetitividade e da qualidade das operações. Para garantir a produtividade, qualidade e além de ampliar a quantidade de aplicações, várias pesquisas e projetos estão sendo desenvolvidos nos principais centros de pesquisa do mundo.


O Projeto Jax Manipulator tem por objetivo realizar uma operação completamente autônoma com o braço manipulador [JeRoTimon](https://braziliansinrobotics.com/project-jerotimon/), que foi desenvolvido em 2020 para o ROS versão Melodic por um grupo de pesquisadores e especialista em robótica. A operação consiste na busca e identificação de um marcador visual posicionado em uma caixa que está presente no ambiente, e após identificação, o robô deve pressionar o botão que também está alocado na caixa. Esta operação utiliza aplicações de **cinemática inversa**, que é crucial para a realização de operações autônomas com os braços manipuladores, **controle de trajetória**, **visão computacional** e **integração de sistemas**. O projeto também teve como objetivo atualizar o Jerotimon para o ROS Noetic.


## Um pouco sobre o Jax Manipulator


O projeto Jax Manipulator foi inicializado em 18/02/2022. Este projeto foi dividido em 5 etapas: Conceitual, Design, Simulação, Integração e testes e conclusão. Estas etapas foram montadas de acordo com Framework de projetos Robótica utilizado pelo RASC e considerando as principais etapas que devem ser executadas para garantir o sucesso do projeto.

## Sistemas do Jax Manipulator

Quase todo sistema robótico pode ser fracionado em conjuntos menores. Jax Manipulator foi dividido em 4 grupos: atuação, software, sensoriamento e alimentação. Esta fragmentação ajuda a visualização do robô diante de suas funcionalidades e dos seus equipamentos. O Prototype structure breakdown que apresenta a divisão do Jax Manipulator em sistemas menores e auxilia na visualização dos equipamentos.

<center>
<img src="{{ 'assets/img/jax/pbs.png' | relative_url }}" width="800" text-align=center alt="ga" />
</center>

<br/>

O sistema mecânico é composto por 5 servomotores Dynamixel. Estes servomotores já possuem um controle de posição, velocidade e torque que foi implementado pelo seu desenvolvedor. O sistema de sensoriamento possui a câmera digital que será utilizada para detectar o marcador visual.
 
Os softwares que permitem a realização da cinemática inversa, controle de trajetória e posição do manipulador estão presentes no pacote  Moveit.  O pacote de software possui uma interface com as linguagens de programação C++ e Python,  o que permite o uso de programas desenvolvidos em ambas línguas para realizar interação com o manipulador. No projeto a interface com braço robótico foi realizada usando a linguagem C++. Para fornecer energia para o sistema foi utilizada uma fonte 24V.

## State Machine

Para executar a missão foi implementada uma state machine com 3 estados. No estado 1 o manipulador inicia a procura do marcador fiducial, fazendo uma varredura contínua por toda região em sua frente e passa pro estado 2 se encontrar o marcador. No estado 2 ele se desloca em direção ao botão pra pressioná-lo, realizando um primeiro movimento pra se aproximar e um segundo movimentar para pressionar o botão. No estado 3 o manipulador retorna para a posição inicial.

<center>
<img src="{{ 'assets/img/jax/state_machine.png' | relative_url }}" width="800" text-align=center alt="ga" />
</center>
<br>

## Resultados

O braço robótico foi implementado com sucesso na versão Noetic do ROS. A missão proposta foi cumprida com sucesso, tanto para a caixa que contém o botão na posição vertical e também na posição horizontal, na simulação e na prática. Foi possível adquirir domínio no pacote de localização de marcos fiduciais utilizado, o [bir_marker_localization](https://github.com/Brazilian-Institute-of-Robotics/bir_marker_localization), no pacote de planejamento de trajetória [moveit](https://moveit.ros.org/) e nos drivers necessários para o funcionamento da [câmera](http://wiki.ros.org/usb_cam) e dos [motores](https://github.com/ROBOTIS-GIT/dynamixel-workbench), assim como domínio na integração desses pacotes.

<br/>


<center>
  <h3 class="post-title">Equipe de desenvolvimento</h3><br/>
</center>
<div class="row">

<div class=" col-xl-auto offset-xl-0 col-lg-4 offset-lg-0">
<table class="table-borderless highlight">
<thead>
<tr>
<th><center><img src="{{ 'assets/img/people/mateusseixas-1.png' | relative_url }}" width="100" alt="juliana" class="img-fluid rounded-circle" /></center></th>
<th></th>
<th><center><img src="{{ 'assets/img/people/matheusanselmo-1.png'| relative_url }}" width="100" alt="matheusanselmo" class="img-fluid rounded-circle"/></center></th>
<th></th>
<th><center><img src="{{ 'assets/img/people/marcoreis8b&w-1.png' | relative_url }}" width="100" alt="marco" class="img-fluid rounded-circle"/></center></th>
</tr>
</thead>
<tbody>
<tr class="font-weight-bolder" style="text-align: center margin-top: 0">
  <td width="33.33%">Mateus Seixas</td>
  <td></td>
  <td width="33.33%">Matheus Anselmo</td>
  <td></td>
  <td width="33.33%">Marco Reis</td>
  </tr>
<tr style="text-align: center" >
<td style="vertical-align: top"><small>Pesquisador Jr. do projeto <br>Mestrando em Engenharia Elétrica.</small></td>
<td></td>
<td style="vertical-align: top"><small>Pesquisador Jr. do projeto <br>Engenheiro de Controle e Automação.</small></td>
<td></td>
<td style="vertical-align: top"><small>Orientador do projeto <br>Mestre em Engenharia de Produção e Eng. Eletricista.</small></td>
</tr>
</tbody>
</table>
</div>
</div>


<br>
<hr class="mark">
<div id="full-tags-list">
<h3 class="post-title"><font color="#fbb117">Posts</font></h3>
  {%- for tag in tags_list -%}
      <h4 id="{{- tag -}}" class="linked-section">
          <i class="fas fa-tag" aria-hidden="true"></i>
          &nbsp;{{- tag -}}&nbsp;({{site.tags[tag].size}})
      </h4>
      <div class="post-list">
          {%- for post in site.tags[tag] -%}
              <div class="tag-entry">
                  <a href="{{ post.url | relative_url }}">{{- post.title -}}</a>
                  <div class="entry-date">
                      <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: date_format -}}</time>
                  </div>
              </div>
          {%- endfor -%}
      </div>
  {%- endfor -%}