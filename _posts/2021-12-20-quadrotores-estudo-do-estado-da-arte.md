---
layout: post
title: Quadrotores
subtitle: Estudo do Estado da Arte
cover-img: assets/img/quadrotor/dronecrop.jpg
thumbnail-img: assets/img/quadrotor/dronecrop2.jpeg
share-img: /assets/img/rosa-logo-redondo.png
author: Mateus Seixas
comments: true
tags: [blog] #AJUSTAR
---

## Quadrotores

Quadrotores são aeronaves de asas rotativas, ou seja, são sustentadas e movimentadas
por rotores. Diferente das aeronaves de asas fixas, como aviões, as aeronaves de asas
rotativas não utilizam seu movimento horizontal para sustentar seu vôo. Isso faz com que
esse tipo de veículo apresente um consumo energético muito alto {% cite karydis2017energetics %}. Apesar disso, as aeronaves de asas rotativas apresentam alta manobrabilidadee, possuem a habilidade de realizar pouso e decolagem vertical e também de realizar vôos estacionários ou quase estacionários.

Esses veículos são comumentes chamados de drones, que em inglês significa zangão ou zumbido, pelo barulho gerado pelos seus rotores em sua operação. Os movimentos do quadrotor são obtidos através da combinação das velocidades angulares desses rotores. Para balancear o contra-torque gerado por seus propulsores, é necessário que um par de rotores que estão em uma mesma haste esteja girando no sentido horário, enquanto o outro par de rotores esteja girando no sentido anti-horário.

<center>
  <img src="{{ 'assets/img/sota-quadrotor/800px-Quadcopter_camera_drone_in_flight.jpg' | relative_url }}" width="750" text-align=center alt="img1" />
</center>


## Estudo do Estado da Arte

Foi realizado um documento de estudo do estado da arte para dar suporte no desenvolvimento de um quadrotor autônomo com capacidade de realizar pouso em uma plataforma móvel. Trazendo conhecimento das melhores técnicas que vem sendo utilizadas em áreas como navegação, controle e localização e mapeamento simultâneos (SLAM), assim como os melhores modelos, arquiteturas para conceber um veículo eficiente e principais componentes. A metologia utilizada para o desenvolvimento desse estudo foi o método BILI.

## Método BILI

A pesquisa do estudo do estado da arte desenvolvida neste documento foi elaborada
principalmente a partir do método BILI, que permite realizar uma pesquisa bibliográfica
em um banco de dados de artigos científicos, publicações em periódicos, livros e outras
fontes de conhecimento científicos, fazendo o levantamento das publicações e dos autores
mais impactantes na área pesquisada. Também foram realizadas pesquisas para avaliar as
soluções já encontradas no mercado. O método BILI é dividido em quatro ciclos que acontecem em sequência, como mostrado na Figura 4.3. Eles são chamados de ciclo ingênuo, ciclo otimizada, ciclo de impacto e ciclo de produção, são mais detalhados no documento.

{:.center}
[![drawing500](../assets/img/sota-quadrotor/bili.png)](../assets/img/sota-quadrotor/bili.png) 

## Classificações

A classificação quanto ao peso de um quadrotor depende do autor. Em {% cite brooke2012unmanned %} os quadrotores são classificados como nano drones, micro drones, mini drones, small drones, tactical drones ou como MALE, HALE ou Strike drones. Segundo a Agência Nacional de Aviação Civil {% cite ANAC2021 %}, os drones são classificados como Classe 1, Classe 2 ou Classe 3, de acordo com seu peso, e cada classificação dessa possui regulamentação específica.

Os quadrotores também são classificados quanto ao seu formato. Eles podem ter a configuração em forma de "+", em que a frente da aeronave fica alinhada com uma das hastes que suporta um par de rotores, ou a configuração em "x", em que a frente da aeronave fica a 45◦ do eixo que contém a haste da aeronave, ficando assim a frente da aeronave no meio de duas hastes, como mostrado na figura.

<center>
  <img src="{{ 'assets/img/sota-quadrotor/configs.png' | relative_url }}" width="750" text-align=center alt="img1" />
</center>

A configuração em "+" é mais acrobática, entretanto, como desvantagens, a haste dos rotores bloqueia o campo de visão da câmera e também apresenta um momento de guinada ao transladar, necessitando de um maior gasto energético para estabilizar a aeronave. A configuração em "x" não apresenta esse efeito, apresentando menor esforço para transladar, menor manobrabilidade e sendo mais estável.

## Principais Componentes

Os principais componentes envolvidos no desenvolvimento de um VANT do tipo quadrotor são os rotores que serão responsáveis por toda movimentação do drone, baterias que irão garantir a energia necessária para os rotores, sensores inerciais que irão ser responsáveis pela localização do drone e microcontroladores, responsáveis pelo cálculo das ações de controle e a integração de hardware e software.

Os VANTs são geralmente equipados com uma IMU (Inertial Measurement Unit), que são dispositivos compostos por giroscópios, acelerômetros e magnetômetros. Através da fusão sensorial é possível obter a atitude do robô e realizar odometria. Muita vezes também são utilizados sensores do tipo barômetro, que são sensores capazes de medir a pressão atmosférica. Como a pressão atmosférica varia com a altitude, é possível mensurar
a altura da aeronave em relação ao nível do mar com a utilização desse sensor. 

Como a alimentação do quadrotor é a base de baterias de corrente contínua é adequado que sejam utilizados motores que utilizem esse tipo de alimentação. Uma boa alternativa de escolha para esse tipo de veículo é o motor brushless DC (BLDC), que é um motor de corrente contínua síncrono alimentado por corrente contínua (CC) e não possui escovas de contato elétrico. A vantagem desse tipo de motor é que
eles são altamente eficientes, pois possuem menos perdas por atrito, resultando em torques maiores. Essa eficiência é de grande valia para os quadrotores, pois um grande desafio associado a operação com esse tipo de veículo é a autonomia. A redução do atrito também faz com que a vida útil desse tipo de motor seja maior e que seja necessário ter menos manutenções, por não necessitar trocar as escovas.

As baterias mais amplamente utilizadas para UAVs são baterias polímero de lítio (LiPo). Esse tipo de bateria tem uma das melhores relações entre capacidade e peso, o que é de vital importância para esse tipo de veículo, já que o peso das baterias pode representar até 50% do peso da aeronave, como mostrado em {% cite Mulgaonkar2014 %}. As baterias LiPo possuem uma capacidade regular e um bom ciclo de vida. Em {% cite Abdilla2015b %}, é feito um estudo do consumo de energia de multirrotores e uma modelagem para estimação da autonomia do veículo operando com baterias LiPo. Diversas pesquisas tem surgido também sobre estações de carregamento wireless de quadrotores, como mostrado em {% cite Mulgaonkar2014 %} e em {% cite Abdilla2015b %}.

Existem diversos modelos de microcontroladores no mercado, com diferentes frequências de operação ou clock,memória flash, RAM, EEPROM e tensão de alimentação. O clock determina quantas operações o microprocessador consegue fazer por unidade de tempo, quanto maior essa velocidade, menor é o tempo entre ações de controle, tornando o controle mais preciso. Entre as plataformas mais utilizadas estão o Arduino, a Raspberry, ARM, PIC, ESP32 e Teensy. Entre as plataformas, o Teensy se destaca, como mostrado na figura.

<center>
  <img src="{{ 'assets/img/sota-quadrotor/bench.png' | relative_url }}" width="750" text-align=center alt="img1" />
</center>

## Modelagem

A modelagem de um quadrotor é uma das etapas mais importantes no desenvolvimento de um projeto envolvendo esse tipo de veículo. Por ser uma plataforma instável, se torna inviável realizar técnicas de identificação em malha aberta. Sendo assim, é necessário obter o modelo dinâmico da aeronave através de técnicas de modelagem. A modelagem da aeronave pode ser obtida através das equações de Newton-Euler ou através do formalismo de Euler-Lagrange {% cite castillo2005modelling %}. Através dessa modelagem é possível obter o modelo de alto nível, onde os torques e forças são entradas e as saídas são posições angulares e lineares.

## Controle

Os quadrotores são veículos subatuados, instáveis e com comportamento dinâmico não-linear. Devido a essas características, é necessário projetar controladores bem ajustados para permitir um correto segmento de referência e rejeição de pertubação. É possível a utilização de controladores lineares, realizando a linearização do modelo dinâmico do robô para projetá-los, e também a utilização de controladores não-lineares para estabilizar e controlar a aeronave.

Os controladores que atuam no quadrotor geralmente são utilizados em cascata {% cite Nonami2010a %}, de forma que existe um controle de baixo nível para garantir uma velocidade de rotação desejada nos rotores, um controlador em um nível mais alto para controlar a altitude e as velocidade angulares de rolagem, arfagem e guinada e por último um controlador no nível mais alto controlando posições lineares no espaço tridimensional {% cite Kendoul2007 %}, formando assim uma estrutura de controle hierárquica.

Os controlador mais comumente usado em baixo nível para controlar a velocidade de de rotação dos propulsores é o controlador Proporcional Integral Derivativo (PID) já que os rotores são sistemas SISO (single-input single-output) que podem ser representado por dinâmicas de primeira ordem.

Os controladores lineares que são mais amplamente utilizados são os controladores PID {% cite Hoffmann2007 %}, {% cite bouabdallah2004design %}, LQR {% cite waslander2005multi %} e H∞ {% cite raffo2008backstepping %}. Como alguns parâmetros do quadrotor podem apresentar incertezas ou até mesmo variar durante a operação, sendo possível adicionar robustez a esses controladores, podendo ajudar também na rejeição de perturbação.

Os controladores não-lineares mais amplamente utilizados são backstepping {% cite madani2006backstepping %}, {% cite Bouabdallah2005 %}, o sliding mode control (SMC) {% cite Zhao2018a %} e o controlador Fuzzy {% cite gautam2013control%}, {% cite nicol2008robust%}, {% cite santos2010intelligent%}.

## Localização

métodos

## Planejamento de Trajetória

planning

## Aplicações

oi

## Conclusão

conclui

## Resultados da Pesquisa

Foi feito um estudo do ambiente de desenvolvimento dos quadrotores. Apresentando os tipos de ambiente que os esse tipo de aeronave opera, podendo ser indoor ou outdoor, suas principais aplicações e a situação atual do desenvolvimento, mostrando no que tem se concentrado as principais pesquisas e pesquisadores da área. 

<center>
  <img src="{{ 'assets/img/sota-quadrotor/Package_copter_microdrones_dhl.jpg' | relative_url }}" width="500" text-align=center alt="img1" />
</center>


Foram apresentadas as classificações que existem para esses veículos. Os quadrotores são classificados quanto ao seu peso, podendo ter diferentes categorias dependendo do autor, e também são classificados quanto à disposição dos seus rotores, podendo ter a configuração em "+" ou em "x".

<center>
  <img src="{{ 'assets/img/sota-quadrotor/configs.png' | relative_url }}" width="600" text-align=center alt="img1" />
</center>

Foi feito um estudo dos principais componentes que um quadrotor possui. Os modelos de sensores inerciais, motores, baterias e microcontroladores foram levantados para embasar uma escolha acertada no desenvolvimento de uma plataforma desse tipo.

Por último foi feito o estudo das principais funcionalidades de um quadrotor. Sendo feito o estudo das principais técnicas de controle, falando um pouco de modelagem e identificação do sistema, principais técnicas de planejamento de trajetória e de localização.

## Documento Completo

<br>
<iframe src ="https://drive.google.com/file/d/1Sa2GipjVxa-oJIdlsc7JlCVI1MSaQG1q/preview" width='740' height='430' allowfullscreen mozallowfullscreen webkitallowfullscreen></iframe>
<br>

## Mapa Conceitual

Foi desenvolvido um mapa conceitual para facilitar o entendimento dos conceitos que envolvem esse tipo de plataforma, relacionando eles de uma forma mais visual.

{:.center}
[![drawing500](../assets/img/sota-quadrotor/rovo-seixas-20211026.jpg)](../assets/img/sota-quadrotor/rovo-seixas-20211026.jpg) 

---------------------
<br>

{% bibliography --cited %}

<!-- autor -->
<center><h3 class="post-title">Autor</h3><br/></center>
<div class="row">
  <div class="col-xl-auto offset-xl-0 col-lg-4 offset-lg-0 center">
    <table class="table-borderless highlight">
      <thead>
        <tr>
          <th><img src="{{ 'assets/img/people/mateusseixas-1.png' | relative_url }}" width="100" alt="mateusseixas" class="img-fluid rounded-circle" /></th>
        </tr>
      </thead>
      <tbody>
        <tr class="font-weight-bolder" style="text-align: center margin-top: 0">
          <td>Mateus Seixas</td>
        </tr>
        <tr style="text-align: center" >
          <td style="vertical-align: top"><small>Pesquisador no laboratório de Robótica e Sistemas Autônomos (RoSA), Senai Cimatec, mestrando em Engenharia Elétrica e amante da natuzera.</small></td>
          <td></td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<br>