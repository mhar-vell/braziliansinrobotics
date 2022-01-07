---
layout: post-page
title: Robôs Antropomórficos
subtitle: Uma breve introdução ao estudo do estado da arte
cover-img: /assets/img/humanoids-sota/wallpaper2.png
thumbnail-img: /assets/img/humanoids-sota/thumb2.png
share-img: /assets/img/rosa-logo-redondo.png
author: Juliana Santana
tags: [blog]
comments: true
---

Robôs antropomórficos, também conhecidos como humanoides, possuem uma estrutura que tem como base o corpo humano, com membros e movimentos que visam uma mobilidade que permita ao robô realizar tarefas diversificadas.

Por isso eles são amplamente utilizados em diversas áreas do dia-a-dia, desde interações com humanos até aplicações na área da saúde, bem como em pesquisas acadêmicas, sendo a sua configuração uma das mais eficientes para locomoção em ambientes de difícil navegação.

Com o intuito de auxiliar no desenvolvimento do projeto Walker, que tem como objetivo construir um robô humanoide autônomo de pequeno porte, foi realizado um estudo bibliográfico. Para mais informações sobre este projeto acesse a página do Walker [aqui](https://mhar-vell.github.io/rasc/project-walker/). 

Este estudo do Estado da Arte sobre robôs antropomórficos aborda algumas das **aplicações** destes robôs e uma visão geral do **atual cenário** como por exemplo, o robô Ginger, desenvolvido pela CloundMinds, que foi disponibilizado para diversas instalações médicas para ajudar no cuidado de pacientes em meio a pandemia do Coronavírus. 

{:.center}
[![drawing400](../assets/img/humanoids-sota/ginger.gif)](../assets/img/humanoids-sota/ginger.gif)
<br>
*Photo by <a href="https://www.businessgyan.com/how-robots-helped-protect-doctors-coronavirus">Businessgyan</a>*

E, o Digit, que em uma parceria da Agility Robotics com a Ford, está sendo testado em conjunto com um carro autônomo, em um projeto que visa automatizar todo o processo de entrega de mercadorias.

{:.center}
[![drawing400](../assets/img/humanoids-sota/Agility-GIF-2.gif)](../assets/img/humanoids-sota/Agility-GIF-2.gif)
<br>
*Photo by <a href="https://media.lincoln.com/content/fordmedia/feu/pt/pt.relatedmedia.viewmore.image.html/content/fordmedia/feu/pt/pt/news/2019/05/22/meet-digit-robot-self-driving-delivery/jcr:content/rightRailPar/relatedmedia_51b9.html">Ford</a>*

Nesta documentação também é apresentada uma seção sobre as **principais características** de alguns modelos de robôs humanoides comumente utilizados por pesquisadores para realizar estudos sobre a locomoção bípede. Dentre as referêcias utilizadas nesta pesquisa a maior parte utilizava como modelo o NAO, o DARWIN-OP, o LOLA ou o HUBO.

{:.center}
[![drawing600](../assets/img/humanoids-sota/robots.png)](../assets/img/humanoids-sota/robots.png)

Também são apresentadas as principais características dos sistemas de **percepção** e **controle** dos robôs antropomórficos, assim como da **estrutura mecânica**, devido a extrema importância destes quesitos no desenvolvimento destes robôs.

Considerações como a quantidade de graus de liberdades (DOFs), altura, peso, velocidade e os tipos de sensores utilizados foram documentadas para auxiliar na parte conceitual do desenvolvimento de um projeto de um robô humanoide, assim como informações referentes ao sistema de processamento e a bateria devido a sua relevância como embasamento para o projeto. 

Essa comparação realizada entre os robôs humanoides, disponibilizada na forma de uma **tabela comparativa** apresentada no Apêndice da documentação do [SOTA](https://github.com/Brazilian-Institute-of-Robotics/bir_humanoid_sota/tree/sota), considera estas características, as quais são de extrema importância para determinar e possibilitar a funcionalidades e atuações do robô humanoide e foi realizado com base nas informações disponibilizadas nos artigos e pelos desenvolvedores. 

Recomendo também a leitura deste [post](https://mhar-vell.github.io/rasc/2021-10-06-walker-comparativo/) para mais informações sobre as características e um comparativo simplificado entre modelos de robôs antropomórficos.

A pesquisa realizada foi de extrema importância para a análise e o aprendizado sobre os robôs antropomórficos. E, as informações que são apresentadas na documentação são bastante relevantes para o desenvolvimento de novos projetos. A documentação do estudo do Estado da Arte pode ser lido [aqui](https://github.com/Brazilian-Institute-of-Robotics/bir_humanoid_sota/tree/sota).

<!-- <iframe src = "https://drive.google.com/file/d/1qjir5z_dT99IG0E7SpOfg_sypdbb2L5L/preview" width='740' height='430' allowfullscreen mozallowfullscreen webkitallowfullscreen></iframe> -->


## Referências

1. CNBC. **Look inside the hospital in China where coronavirus patients were treated by robots.** 2021. <https://www.cnbc.com/2020/03/23/video-hospital-in-china-where-covid-19-patients-treated-by-robots.html>. Accessed: 2021-12-02.
2. SCIENCE, P. **Tesla wants to make humanoid robots. Here’s their competition.** 2021.<https://www.popsci.com/technology/list-of-companies-creating-human-like-robots/>. Accessed: 2021-12-02.
3. ASME. **10 Humanoid Robots of 2020. 2021.** <https://www.asme.org/topics-resources/content/10-humanoid-robots-of-2020>. Accessed: 2021-12-02. 

* * *

<!-- autor -->
<center><h3 class="post-title">Autor</h3><br/></center>
<div class="row">
  <div class="col-xl-auto offset-xl-0 col-lg-4 offset-lg-0 center">
    <table class="table-borderless highlight">
      <thead>
        <tr>
          <th><img src="{{ 'assets/img/people/juliana-1.png' | relative_url }}" width="100" alt="amarco" class="img-fluid rounded-circle" /></th>
        </tr>
      </thead>
      <tbody>
        <tr class="font-weight-bolder" style="text-align: center margin-top: 0">
          <td>Juliana Santana</td>
        </tr>
        <tr style="text-align: center" >
          <td style="color: #808080; vertical-align: top; text-align: justify"><small>Pesquisadora em Robótica no Centro de Competências em Robótica e Sistemas Autônomos do Senai Cimatec. Motivada por desenvolver projetos que possam fazer a diferença. Juliana é formada em engenharia elétrica pelo Centro Universitário SENAI Cimatec. </small></td>
          <td></td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
<br>