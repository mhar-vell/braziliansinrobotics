---
layout: post-page
title: Monte Carlo Localization using MLS Maps
subtitle: Um estudo sobre Monte Carlo Localization com Mapas de Múltiplos-Níveis 
cover-img: /assets/img/2021-12-21-monte_carlo_localization/mapa.jpg
thumbnail-img: /assets/img/2021-12-21-monte_carlo_localization/mapa.png
share-img: /assets/img/rosa-logo-redondo.png
author: Matheus Anselmo
tags: [blog]
comments: true
---



A Localização é  um quesito importante para robótica móvel, pois são com os dados da posição e orientação que as ações de controle são processadas. Em uma situação que os dados da localização não refletem muito bem a a dinâmica, a atuação pode ser prejudicada principalmente quanto a navegação é realizada de forma autônoma.

Em ambientes internos e controlados, o uso de SLAM e tags, ajudam o robô a obter dados sobre a posição e orientação. Em ambientes externos nem sempre é possível obter dados da posição usando estas ferramentas. Uma solução para realizar a localização em ambientes externos é apresentada por [ Rainer K.](https://www.linkedin.com/in/rainer-k%C3%BCmmerle-256b4a15a/?originalSubdomain=de), [Rudolph T.](https://www.linkedin.com/in/rudolph-triebel-82107713/), [Patrick p.](https://www.linkedin.com/in/patrick-pfaff-97a51b9/) e [wolfram B.](https://www.linkedin.com/in/burgard/) no artigo [Monte Carlo Localization in Outdoor Terrains Using Multi-Level Surface Maps](https://www.researchgate.net/publication/220648287_Monte_Carlo_Localization_in_Outdoor_Terrains_Using_Multi-Level_Surface_Maps) que demonstra a aplicação do Monte Carlo localization com auxílio de mapas multi-níveis e compara os resultados obtidos com mapa de elevação.

Em ambientes externos, é comum usar GPS para obter dados sobre a posição dos robôs, porém o sinal deste pode ser prejudicado pela presença de árvores, muros, paredes e dentre outros anteparos. Estes elementos podem atuar como obstáculos para o sinal do gps. Uma solução para contornar este problema é usar dados do mapa do ambiente juntamente com o Monte Carlo Localization.



[![drawing1000](../assets/img/2022-01-11-monte-carlo-localization/slide4.png)](../assets/img/2022-01-11-monte-carlo-localization/slide4.png)
<br>
### Monte Carlo Localization


O Monte Carlo Localization (MCL) é um algoritmo destinado a sistemas robóticos móveis com o objetivo de obter dados sobre a posição e orientação do robô no ambiente. Este algoritmo usa um filtro de partículas, para posição e orientação, e um mapa do ambiente para realizar a estimação. Cada partícula representa uma possível posição e orientação que o robô pode apresentar. As partículas são estimadas usando filtro Bayesiano recursivo. Geralmente são usados mapas de elevação para abastecer de dados o Monte Carlo Localization. 
Os mapas de elevação, comunalmente chamados de mapas 2.5 d, são formados pela projeção de informações de profundidade de elementos verticais em plano 2D, em outras palavras, os objetos e obstáculos que estão situado em local são usados para representar um plano horizontal. Nestes mapas, os dados do plano são coletados e bem representados, já as elevações são processadas como um média dos dados verticais.

### Mapa de Multi-Níveis

Os Mapas de multi-níveis, além representar bem o plano, consegue representar os dados verticais devido ao uso de representação em camadas.
#### Mapa de Elevação

[![drawing1000](../assets/img/2022-01-11-monte-carlo-localization/elevation.png)](../assets/img/2022-01-11-monte-carlo-localization/elevation.png)
<br>

#### Mapa de Multi-Níveis
<br>
[![drawing1000](../assets/img/2022-01-11-monte-carlo-localization/multi_layer.png)](../assets/img/2022-01-11-monte-carlo-localization/multi_layer.png)

Os dados geométricos verticais dos mapas multi-níveis são usados para estimar a posição do robô, em outras palavras, o plano vertical e horizontal servem para calcular a localização. Os mapa de multi-níveis também oferecem dados sobre a posição do robô quanto ao eixo vertical, o eixo z. Um outro comparação detalhe, é que o custo computacional do mapa de multi-nível só é 10% maior em comparação ao mapa de elevação, em outras palavras, há um pequeno aumento no uso de hardware.

## Resultados 

O uso do Monte Carlos Localization com o mapa de multi-nível apresentou uma melhor representação da posição do robô em comparação ao mapa de elevação. Esta estratégia pode ser uma excelente opção em ambientes externos onde o nem sempre o sinal do GPS está disponível.

[![drawing1000](../assets/img/2022-01-11-monte-carlo-localization/results1.png)](../assets/img/2022-01-11-monte-carlo-localization/results1.png)
<br>

## Mapa Conceitual

Um mapa conceitual foi realizado para compreender melhor o artigo através de ligações gráficas. As ligações gráficas representam as conexões entre os principais  conceitos que compõem o material.


[![drawing1000](../assets/img/2022-01-11-monte-carlo-localization/conceptual_map.jpg)](../assets/img/2022-01-11-monte-carlo-localization/conceptual_map.jpg)


<br>




O Monte Carlo Localization in Outdoor Terrains Using Multi-Level Surface Maps é um excelente artigo. A leitura e a interpretação deste material, juntamente com a montagem do mapa conceitual são válidos para adquirir conhecimentos sobre a localização sobre robótica móvel. A questão sobre a localização é bastante importante para o desenvolvimento e aplicação de sistemas autônomos móveis, já que estes estão ganhando cada vez mais funcionalidades e expandindo as áreas de atuações. Além de propor uma solução para a localização em ambientes externos com baixo custo computacional, este  material faz uso de ferramentas estatística que além de serem fortemente utilizado na robótica são bastantes importantes para outras áreas. 

<br>



<br>

---------------------
<!-- autor -->

<center><h3 class="post-title">Autor</h3><br/></center>

<div class="row">

  <div class="col-xl-auto offset-xl-0 col-lg-4 offset-lg-0 center">

    <table class="table-borderless highlight">

      <thead>

        <tr>

          <th><img src="{{ 'assets/img/people/matheusanselmo-1.png' | relative_url }}" width="100" alt="amarco" class="img-fluid rounded-circle" /></th>

        </tr>

      </thead>

      <tbody>

        <tr class="font-weight-bolder" style="text-align: center margin-top: 0">

          <td>Matheus Anselmo</td>

        </tr>

        <tr style="text-align: center" >

          <td style="color: #808080; vertical-align: top; text-align: justify"><small> Engenheiro de robótica  realizando  no Centro de Competências em Robótica e Sistemas Autônomos do Senai Cimatec. Matheus é formado em engenharia de controle e automação pela UFBA e autor da frase "um cafezinho sempre cai bem antes e depois de outro cafezinho"
          .</small></td>

          <td></td>

        </tr>

      </tbody>

    </table>

  </div>

</div>

<br>







