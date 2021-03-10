---
layout: post
title: "Oppimatka syväoppimiseen"
author: "Lassi Puurunen"
date: 2021-03-01 00:00:00 +0000
tags: päiväkirja oppiminen pohjatietoa linkkejä
---

# Oppimatka syväoppimiseen

Olen jo pidempään miettinyt, että opinnoistani tekoälyn parissa voisi olla hyödyllistä kirjoittaa blogia. Hyötyä kirjoittamisesta tulisi itselleni, käsitteiden jäsentämiseksi kokonaisuuteen, sekä mahdollisesti muille vastaavanlaisessa tilanteessa oleville – ohjelmointitaitoisille, jotka haluavat tositoimiin tekoälyn ja syväoppivien neuroverkkojen kanssa.

Tässä vaiheessa on sopivaa kertoa hieman omasta taustastani. Olen 1982-vuosimallin tekijä, pelannut tietokoneiden kanssa lähes koko elämäni. Ohjelmointia ja tietojenkäsittelyä tieteenä olen alkanut opiskella järjestelmällisesti kuitenkin vasta 2017. Viimeiset kolme vuotta on mennyt alan opinnoissa korkeakoulussa. Korkeakoulu on antanut paljon arvokasta näkemystä tietojärjestelmien ja -rakenteiden syvällisempään toimintaan, mutta käytännön opit olen saanut pääasiassa verkossa yleisesti saatavilla olevista materiaaleista, joihin tulen tässä blogissakin pääasiassa nojautumaan.

## Pohjatietoa

Saadakseen sisällöstä eniten irti, on lukijan hyvä hallita ohjelmoinnin perusteet, millä vain ohjelmointikielellä, kuitenkin mieluiten Pythonilla. Mikäli et omaa vielä ohjelmointitaitoa, suosittelen [MOOC.fi](https://www.mooc.fi/) -sivustolta löytyvää Ohjelmoinnin Moocia. Samalta sivultolta löytyvältä, Data analysis with Python -kurssilta, voi oppia perusteet, aluksi Python kielestä, sekä myöhemmin data-analyysista ja koneoppimisesta.

Hieman kevyempänä katsauksena aiheeseen, suosittelen PBS:n tiedeohjelmistoon kuuluvaa sarjaa, [Crash Course AI](https://thecrashcourse.com/courses/ai). Se on hauskasti toteutettu, tiivis tietopaketti tekoälystä. Sarjasta saa kattavan katsauksen tekoälyn alasta ja neuroverkkojen mahdollisuuksista. Sarjan materiaalit mahdollistavat myös esimerkkien harjoittelun käytännön ohjelmoinnin tasolla.

Opiskeltuani jo aiemmin teoriaa ja kokeiltuani [Tensorflow:n](https://www.tensorflow.org/tutorials) ja sen korkeamman tason kirjaston, [Keras:n](https://keras.io/getting_started/intro_to_keras_for_engineers/), harjoitusmateriaaleja, etsin tietoa, kuinka aloittaisin neuroverkkojen ja syväoppimisen toteuttamisen käytännössä, oikeissa sovelluksissa. Törmäsin siten verkkokeskusteluissa fast.ai:n [course.fast.ai](https://course.fast.ai/) tarjoamiin oppimateriaaleihin. Oppimateriaaliin kuuluvat kirja, dokumentaatiot, videot ja yhteisö, jotka ovat kaikki vapaasti saatavilla.

## fast.ai

fast.ai:n materiaali osoittautui heti alusta lähtien hyvin käytännönläheiseksi. Tositoimiin, eli isojen, syväoppivien neuroverkkojen koulutukseen ryhdytään heti, sivuten samalla koneoppimisen perusteita. Kurssin rakenteesta selvitetään videomateriaaleissa, että tarkoituksena on harjoitella ensin soveltamaan neuroverkkoja laajasti ja myöhemmässä vaiheessa siirtyä tutkimaan niiden toimintaa yksityiskohtaisemmin. Kurssin pitäjien mukaan, tapa tarkastella asioita ensin käytännön tasolla on hedelmällisin tapa lähteä lähestymään aihetta. Kurssilla todettua: ”Voidaksesi ajaa Ferraria, ei sinun tarvitse tietää tarkalleen sen toimintaa.” Kurssin pitäjät sanovat kurssin sopivan jokaiselle perusohjelmointitaidon omaavalle. Mielestäni tämä pitää paikkansa tähän mennessä, kahdessa ensimmäisessä luvussa olleiden materiaalien perusteella.

fast.ai:n materiaalissa tuli sitten toisen luvun lopussa vastaan kappale, jossa kerrottiin blogin kirjoittamisen merkityksestä ja hyödyllisyydestä oppijalle. Koska blogin kirjoittamisen hyödyt esitettiin nyt niin vakuuttavasti, tässä sitä nyt sitten ollaan. Aion kirjoittaa tähän blogiin opintomatkastani neuroverkkojen soveltamiseen, sekä niiden perusteista. Tulen myös blogissa seuraamaan tekoälyn alan kehitystä ja pohtimaan sen vaikutuksia laajemmin.

Seuraavassa artikkelissa mennään kuitenkin suoraan käytännön asiaan. Esittelen siinä, kuinka koulutin neuroverkon tunnistamaan karhulajeja.

Seuraava artikkeli: [Konenäkö v1.0 - osa 1 - Karhuntunnistin konvolutiivisella neuroverkolla]({{ site.baseurl }}/tekoalyn-ohjelmointi-pythonilla/konen%C3%A4k%C3%B6_v1.0/2021/03/11/konenakov1-konvoluutioinen-neuroverkko.html)

## Linkkejä artikkelista

1. [Crash Course AI](https://thecrashcourse.com/courses/ai)
2. [MOOC.fi](https://www.mooc.fi/) Täältä kurssit 'Ohjelmoinnin Mooc' ja 'Data analysis with Python'
3. [Tensorflow](https://www.tensorflow.org/tutorials) tutorials
4. [Keras](https://keras.io/getting_started/intro_to_keras_for_engineers/) Introduction to Keras for Engineers
5. [course.fast.ai](https://course.fast.ai/)
