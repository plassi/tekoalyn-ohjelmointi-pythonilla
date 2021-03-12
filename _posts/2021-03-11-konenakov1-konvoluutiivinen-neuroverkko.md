---
layout: post
title: "Konenäkö v1.0 - osa 1 - Karhuntunnistin konvoluutioneuroverkolla"
author: "Lassi Puurunen"
date: 2021-03-11 00:00:00 +0000
tags: konvoluutioneuroverkko teoriaa
categories: konenäkö_v1.0
---

# Konenäkö v1.0 - osa 1 - Karhuntunnistin konvoluutioneuroverkolla

Tästä alkaa artikkelisarja, jossa käydään läpi yksinkertaisen konenäön, eli konvoluutioneuroverkon kouluttaminen fast.ai:lla. Artikkelin lähdekoodi on saatavilla Google Colab -projektina. Colab -ympäristössä voit kopioda koodin itsellesi ja ajaa sitä Googlen palvelimella. Tekemällä koodiin pieniä muutoksia, voit toteuttaa haluamasi konenäköä käyttävän luokittelijan. Projekti perustuu [fastbookin 2.luvun materiaaleihin](https://github.com/fastai/fastbook/blob/master/02_production.ipynb). 

<a href="https://colab.research.google.com/github/plassi/karhuntunnistin/blob/main/konenako_v1_0_clean.ipynb" target="_parent"><img src="https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667" alt="Open In Colab" data-canonical-src="https://colab.research.google.com/assets/colab-badge.svg"></a><br>
Yläpuolella olevasta napista saat projektin lähdekoodin auki Colabissa.

## Karhuntunnistin

Jos vastaasi tulee karhu, on sen lajista kolme vaihtoehtoa. Karhu voi olla metsässä liikkuva ruskeakarhu. Toisaalta karhu voi olla jääkarhu, joita legendan mukaan liikkuu Helsingin kaduilla. Yleisesti kotiympäristöissä tavattu karhulaji on kuitenkin teddykarhu, johon sen metsässä tai Helsingin kaduilla tavattavia heimotovereita ei tule sekoittaa. Onneksi tällaisten, mahdollisesti vaarallisten sekaannusten mahdollisuutta voidaan ehkäistä tekoälyn avulla.

Artikkelisarjassa toteutettava konvoluutioneuroverkko luokittelee kuvia sen perusteella, esiintyykö kuvassa ruskeakarhu, jääkarhu vai teddykarhu.

Koodia kannattaa kokeilla aina ohjelmointia opiskellessa itse, sillä se on tehokkain keino oppia ja oivaltaa järjestelmien toimintaa.

Tässä sarjan ensimmäisessä artikkelissa tutustutaan aluksi keinotekoisen neuronin, sekä monikerroksisen- ja konvoluutioneuroverkon rakenteisiin. Nämä kaikki ovat matemaattisia malleja, mutta mikäli matematiikka ei ole leipälajisi, ei syytä huoleen. Sarjassa ei matematiikka ole pääosassa, vaan tarkoituksena on toteuttaa konenäkö mahdollisimman käytännönläheisesti.

## Keinotekoinen neuroni

Tutustutaan pikaisesti neuroverkkojen perusosiin. Kuvassa 1 on esitetty biologisen neuronin kaavio. Kuten biologisessa neuronissa on neuronien välillä eri vahvuiset yhteydet ja aksonissa signaalia kuljettava toimintapotentiaali, on keinotekoisessa neuronissa painotetut sisääntulevat kaaret sekä summa- ja siirtofunktiot.

![Biologinen neuroni]({{ site.baseurl }}/images/1024px-Components_of_neuron.jpg)
Kuva 1. Biologisen neuronin kaavio

Kuvasta 2 nähdään keinotekoisen neuronin kaavio. Keinotekoiseen neuroniin syötetään signaalit (X1, X2, Xn..) ja jokainen signaali kerrotaan sisään menevien kaarien painoilla (w1, w2, w3). Painotetut signaalit lasketaan summafunktiossa yhteen ja ulosmenevä signaali "suodatetaan" mallin arkkitehtuuriin valitulla siirtofunktiolla, jonka tehtävä on varmistaa esimerkin funktiossa, että syöte pysyy 0:n ja 1:n välissä.

![Keinotekoinen neuroni]({{ site.baseurl }}/images/800px-Artificial_Neuron.svg.png)
Kuva 2. Keinotekoisen neuronin kaavio

Konvoluutioneuroverkon solmut ovat keinotekoisia neuroneja. 

## Konvoluutioneuroverkko

Konvoluutioneuroverkko on saanut inspiraationsa biologisesta näköhermostosta ja sitä sovelletaan konenäköön. Konenäköä voidaan käyttää muuhunkin kuin varsinaisten kuvien luokitteluun, sillä monenlaista tietoa voidaan esittää kuvana. Konenäkö kykenee esimerkiksi äänen tunnistukseen sen kuvan perusteella. Toisaalta esimerkiksi tiedoston tiivisteistä voidaan muodostaa kuvia ja konenäön avulla tunnistaa niistä haittaohjelmia.

Konvoluutioneuroverkko perustuu monikerroksiseen, yhdensuuntaiseen, vahvasti yhtenäiseen neuroverkkoon. Yhdensuuntaisuus tarkoittaa tässä, että verkossa tieto liikkuu vain yhteen suuntaan. Vahva yhtenäisyys tarkoittaa, että kerroksessa kukin neuroni on yhteydessä seuraavan kerroksen jokaiseen neuroniin. Neuroverkko on näiden ominaisuuksien lisäksi painotettu, eli siinä on solmujen välisillä kaarilla jokin paino. Nämä painot, eli neuronien välisten yhteyksien "vahvuudet" ja niiden muuttaminen on keskeisessä asemassa neuroverkon kouluttamisessa.  

![Monikerroksinen neuroverkko]({{ site.baseurl }}/images/Multi-Layer_Neural_Network-Vector-Blank.svg.png)
Kuva 3. Monikerroksinen neuroverkko

Kuvassa 3 on esitetty monikerroksisen neuroverkon rakenne. Kuvassa vasemman puoleiset pisteet ovat solmuja sisään menevälle datalle, eli niistä muodostuu syötekerros. Toisena välissä on kolmen neuronin ns. piilotettu kerros. Kolmantena on kahdesta neuronista koostuva tulostekerros, josta luetaan neuroverkon ennusteet.

Todellisuudessa käytetyt mallit ovat kuitenkin huomattavasti suurempia. Karhuntunnistimessa koulutusdatan kuvien sivun koko on 128 pikseliä, joten sisäänmeneviä solmuja on 128 x 128 = 16384. Piilotettuja kerroksia on syväoppivassa neuroverkossa kymmenistä satoihin, mistä käsite syväoppiminen tulee. Tulostekerroksessa solmuja on yhtä monta, kuin neuroverkolle on koulutettu luokkia, karhuntunnistimessamme niitä on kolme, yksi jokaista lajia kohti. 

Konvoluutioneuroverkko poikkeaa itse asiassa tavanomaisesta monikerroksisesta neuroverkosta siten, että osa sen kerroksista on konvoluutio- ja pooli-kerroksia. Tämä aihe vaatii täysin oman käsittelynsä, mutta siitä saa hyvin kiteytettynä tietoa [tästä Youtube-videosta](https://www.youtube.com/watch?v=2-Ol7ZB0MmU).

## Lopuksi

Raapaisimme nyt kevyesti pintaa teorian osalta siitä, mistä neuroverkoissa on kyse. Tätä tietoa ei kuitenkaan artikkelisarjassa käytännössä tarvita, sillä kaikki matematiikka on pitkälle kehitetyissä fast.ai:n kirjastoissa piilotettu käyttöliittymän alle. Pyrin kuitenkin avaamaan, mitä eri vaiheissa pinnan alla tapahtuu. 

Seuraavassa artikkelissa siirrytään tarvittaviin perustyökaluihin, sekä niiden käyttöönottoon.

Heräsikö artikkelista ideoita, ajatuksia, kysymyksiä? Ehkä korjausehdotuksia? Kirjoita alla olevaan kommenttilaatikkoon tai lähetä yksityisesti vaikka LinkedIn-viestinä.

## Linkkejä

1. [fastbook/01_intro.ipynb](https://github.com/fastai/fastbook/blob/master/01_intro.ipynb) - fastbookin luku, jossa on neuroverkon historiaa ja teoriaa
1. [A friendly introduction to Convolutional Neural Networks and Image Recognition](https://www.youtube.com/watch?v=2-Ol7ZB0MmU) - Video, jolla on selitetty hyvin, kuinka konvoluutioneuroverkko toimii
1. [Wikipedia: Syväoppiminen](https://fi.wikipedia.org/wiki/Syv%C3%A4oppiminen)
2. [Datanamin artikkeli](https://www.datanami.com/2017/05/10/machine-learning-deep-learning-ai-whats-difference/) - Tekoälyn termistöä

*Kuvien lähde Wikimedia Commons*