---
layout: page
title: Warthog
subtitle: Navegação autônoma
cover-img: /assets/img/aum/matt-hardy-6ArTTluciuA-unsplash.jpg
thumbnail-img: /assets/img/aum/network(2).png
share-img: /assets/img/rosa-logo-redondo.png
author: Marco Reis
comments: true
tags: [project]
---
{% assign date_format = site.date_format | default: "%B %-d, %Y" %}
{%- capture site_tags -%}
    {%- for tag in site.tags -%}
      {% if tag contains 'warthog' %}
        {{- tag | first -}}{%- unless forloop.last -%},{%- endunless -%}
      {% endif %} 
    {%- endfor -%}
{%- endcapture -%}
{%- assign tags_list = site_tags | split:',' | sort -%}

<center><img src="{{ 'assets/img/warthog/smach.gif' | relative_url }}" alt="navegacao_warthog" width="500"/></center>

<div class="before-content">
  <center>
    {%- for tag in tags_list -%}
      <br>
      <a href="#{{- tag -}}" class="btn btn-primary tag-btn"><i class="fas fa-tag" aria-hidden="true"></i>&nbsp;{{- tag -}}-posts&nbsp;({{site.tags[tag].size}})</a>
    {%- endfor -%}
  </center>    
  <!--hr class="mark"-->
</div>

<!-- ## Introdução -->

Para que o deslocamento de um robô móvel seja realizado de forma autônoma, é necessário que
ele seja capaz de realizar, sem intervenção de um controlador externo, o planejamento
e execução de trajetórias no ambiente de operação desejado, desvio de obstáculos e a
localização e mapeamento do ambiente, o que é conhecido como navegação autônoma. A
navegação autônoma é fundamental para que um robô consiga realizar uma ampla gama de
tarefas como, por exemplo, deslocar-se de um ponto a outro em um ambiente desconhecido.

<!--objetivo, data-->
O objetivo geral do projeto é o desenvolvimento de uma arquitetura de gerenciamento para a navegação autônoma de um robô móvel em ambientes externos, avaliando o desempenho de *Behavior Trees* e HFSMs. Este projeto foi iniciado em **15 de Janeiro de 2021** e finalizado em **30 de junho de 2021**.

<!--justificativa-->
Como forma de desenvolvimento de soluções na robótica, cada vez mais é necessário que o controle sobre todos os processos da navegação autônoma sejam elevados, para conseguir personalizar cada processo de acordo com particularidades encontradas na operação de cada robô. Desta forma, foi desenvolvido um sistema de navegação autônoma para a plataforma móvel *Warthog*, de modo a permitir que o robô navegue de forma autônoma em ambientes externos. Este sistema é gerido por uma **arquitetura de gerenciamento de processos na navegação**, utilizando ***Behavior Trees*** e **HFSM**, e desenvolvido utilizando algoritmos *open source* fornecidos pelo *framework* ROS.


## Detalhamento

O sistema é composto de uma plataforma móvel, o robô ***Warthog***, da *Clearpath Robotics*,
que carrega consigo sensores em uma estrutura de perfis de alumínio. A estrutura de
alumínio suporta os seguintes equipamentos: duas câmeras estéreo **Mynt Eye S-1030**,
dois lidares **Velodyne VLP-16** e um computador auxiliar **NUC8i7BEH**. No desenvolvimento deste sistema foi utilizado o ROS na versão *Noetic*.

<center>

<img src="{{ 'assets/img/warthog/warthog_sensor.png' | relative_url }}" alt="Componentes" width="550"/><br>

Plataforma móvel Warthog e sensores e equipamentos instalados.
</center>


O projeto de navegação autônoma no *Warthog* é composto de cinco funcionalidades, descritas a seguir:
- **Localização:** A localização do robô é realizada através da odometria visual;
- **Navegação:** A navegação é responsável por realizar a movimentação do robô dada uma posição objetivo;
- **Percepção:** O módulo de percepção é responsável por fornecer ao robô a capacidade de perceber o ambiente ao seu redor através dos dados provenientes dos sensores embarcados;
- **Planejamento:** Responsável pelo cálculo de rotas livres de colisão;
- **Mapeamento:** A partir das imagens da câmera estéreo, é realizado o mapeamento da área percorrida pelo robô.

<br>

## Simulação

Para a simulação, foi utilizado como ambiente uma representação do pátio do prédio
Cimatec 4 (SENAI Cimatec), este ambiente de simulação tem dimensões reais e serve como base para a implementação de toda a base de algoritmos utilizada neste projeto.

<center>

<img src="{{ 'assets/img/warthog/gazebo.gif' | relative_url }}" alt="Simulação" width="550"/><br>

Simulação do projeto no *Gazebo*.
</center>


<br>

## *Live Action*

Alguns testes foram feitos utilizando o robô no ambiente real, e o robô se comportou bem nesta tarefa, de modo a prover dados coerentes que auxiliaram no planejamento de trajetórias e no desvio de obstáculos.

Nos testes realizados, através do uso do algoritmo de odometria visual e localização
e mapeamento simultâneo com o **RTAB-Map**, foi utilizado o **Move Base Flex** para a navegação e também dois algoritmos de gerenciamento de comportamento. O **SMACH**, que utiliza o conceito de máquinas de estados hierárquicas, e o **PyTrees**, que utiliza o conceito de *Behavior Trees*.

<center>

<img src="{{ 'assets/img/warthog/real.gif' | relative_url }}" alt="Simulação" width="300"/><br>

Testes no projeto em ambiente real.
</center>


<br>

<!--equipe-->

<center><h3 class="post-title">Equipe de desenvolvimento</h3><br/></center>
<div class="row">
  <div class=" col-xl-auto offset-xl-0 col-lg-4 offset-lg-0">
    <table class="table-borderless highlight">
      <thead>
        <tr>
          <th><center><img src="{{ 'assets/img/people/israelneto-1.png' | relative_url }}" width="100" alt="israel" class="img-fluid rounded-circle" /></center></th>
          <th></th>
          <th><center><img src="{{ 'assets/img/people/lucaslins-1.png' | relative_url }}" width="100" alt="lucas" class="img-fluid rounded-circle"/></center></th>
          <th></th>
          <th><center><img src="{{ 'assets/img/people/marcoreis8b&w-1.png' | relative_url }}" width="100" alt="marco" class="img-fluid rounded-circle"/></center></th>
        </tr>
      </thead>
      <tbody>
        <tr class="font-weight-bolder" style="text-align: center margin-top: 0">
          <td width="33.33%">Israel Motta</td>
          <td></td>
          <td width="33.33%">Lucas Lins</td>
          <td></td>
          <td width="33.33%">Marco Reis</td>
        </tr>
        <tr style="text-align: center" >
          <td style="vertical-align: top"><small>Pesquisador bolsista no CC RoSA, Engenheiro Mecatrônico, Especialista em Robótica e Sistemas Autonônomos.</small></td>
          <td></td>
          <td style="vertical-align: top"><small>Estagiário no CC RoSA, graduando em Eng. Elétrica. Participou de projetos de Robótica Móvel.</small></td>
          <td></td>
          <td style="vertical-align: top"><small>Pesquisador Sênior do projeto <br>Mestre em Engenharia de Produção e Eng. Eletricista.</small></td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<br>

### Resumo do Projeto
1. Categoria: <font color="#fbb117">Robótica móvel</font>
2. Prazo: <font color="#fbb117">5 meses e 15 dias</font>
3. Data de início: <font color="#fbb117">15/01/2021</font>
4. Data de término: <font color="#fbb117">30/06/2021</font>
5. Repositório URL: [Warthog](https://github.com/Brazilian-Institute-of-Robotics/bir_warthog)
6. Sponsor: <a href="http://www.senaicimatec.com.br/en/"><font color="#fbb117">Senai CIMATEC</font></a>
7. Recursos materiais: --
8. Apresentação URL: [Warthog-presentation](https://github.com/Brazilian-Institute-of-Robotics/bir_warthog/blob/feature/move_base_flex/warthog_docs/presentation.pdf)
9. Report URL: [Warthog-report](https://github.com/Brazilian-Institute-of-Robotics/bir_warthog/blob/feature/move_base_flex/warthog_docs/report.pdf)
10. Artigos produzidos:

<br>

### Referências
1. PÜTZ, S.; SIMÓN, J. S.; HERTZBERG, J. Move base flex a highly flexible navigation
framework for mobile robots. In: IEEE. 2018 IEEE/RSJ International Conference on
Intelligent Robots and Systems (IROS). [S.l.], 2018. p. 3416–3421.
2. COLLEDANCHISE, M.; ÖGREN, P. Behavior trees in robotics and AI: An introduction.
[S.l.]: CRC Press, 2018.


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
</div>