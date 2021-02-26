---
layout: post
title: "oppimatka syväoppimiseen"
author: "Lassi Puurunen"
date: 2021-02-26 00:00:00 +0300
categories: perusteet
---

# Oppimatka syväoppimiseen

Olen jo pidempään miettinyt, että opinnoistani tekoälyn parissa voisi olla hyödyllistä kirjoittaa blogia. Hyötyä kirjoittamisesta tulee sekä itselleni, käsitteiden ja ajatusten jäsentämiseksi, että mahdollisesti muillekin vastaavanlaisessa tilanteessa oleville – koodaustaitoisille, joilla on mielenkiintoa koneoppimisen ja tekoälyn alalle, ja jotka nyt etsivät tietä alkuun tai hakevat oppia tositoimiin.

Tässä vaiheessa on sopivaa kertoa hieman omasta taustastani. Olen 1982-vuosimallin tekijä, pelannut tietokoneiden kanssa lähes koko elämäni. Ohjelmointia ja tietojenkäsittelyä tieteenä olen alkanut opiskella järjestelmällisesti kuitenkin vasta 2017. Viimeiset kolme vuotta on mennyt alan opinnoissa korkeakoulussa. Korkeakoulu on antanut paljon näkemystä tietojärjestelmien syvällisempään toimintaan, mutta käytännön opit olen saanut pääasiassa verkossa yleisesti saatavilla olevista materiaaleista, joihin tulen tässäkin blogissa nojautumaan.

## Pohjatietoa

Saadakseen sisällöstä eniten irti, on lukijan hyvä hallita Python-kielen perusteet. Opin itse Pythonin, sekä data-analyysin perusteet https://www.mooc.fi/ -sivustolta löytyvältä Data analysis with Python – kurssilta, jota suosittelen lämpimästi. Tuolta kurssilta saa kätevästi aluksi Pythonin perusteet data-analyysin näkökulmasta, sekä koneoppimisen perusteet.

Toinen suositukseni on Youtubessa oleva sarja Crash Course AI. Se on hauskasti toteutettu, erittäin tiivis tietopaketti tekoälystä. Sarjasta saa hyvin katsauksen tekoälyn alasta ja erityisesti neuroverkkojen mahdollisuuksista.

Opiskeltuani jo aiemmin teoriaa ja myös kokeiltuani itse neuroverkkojen ohjelmointia Tensorflowlla ja Keraksella, etsin hetki sitten tietoa, kuinka aloittaisin neuroverkkojen ja syväoppimisen toteuttamisen käytännössä, oikeissa sovelluksissa. Törmäsin sitten verkkokeskusteluissa fast.ai:n (https://course.fast.ai/) tarjoamiin oppimateriaaleihin. Oppimateriaaliin kuuluvat kirja, dokumentaatiot, videot ja yhteisö, jotka ovat kaikki vapaasti saatavilla.

## fast.ai

fast.ai:n materiaali osoittautui heti alusta lähtien hyvin käytännönläheiseksi. Tositoimiin, eli isojen, syväoppivien neuroverkkojen koulutus aloitetaan heti, sivuten samalla koneoppimisen perusteita ja teorioita. Tässä kurssissa on ilmeisesti tarkoitus näyttää kokonaiskuva ensin ja siirtyä sitten yksityiskohtiin. Tällainen toimintatapa on, kurssin pitäjien mukaan, akateemikoille kauhistus. Toisaalta tapa tarkastella asioita ensin käytännön tasolla on erittäin tehokas keino oppia kaivattua käytännön soveltamista. Kurssilla sanottua: ”Voidaksesi ajaa Ferraria, ei sinun tarvitse tietää tarkalleen kuinka sen moottori toimii.” Kurssin pitäjät sanovatkin kurssin sopivan jokaiselle, joilla on perusohjelmointitaito. Muita alkutason vaatimuksia ei periaattessa ole.

fast.ai:n oppimateriaaliin liittyvän kirjan toisen luvun loppuun päästessäni, tuli vastaan kappale blogin kirjoittamisen merkityksestä ja hyödyllisyydestä oppijalle, joten tässä sitä nyt ollaan. Tämän blogin tärkein tarkoitus on siis toimia oppimispäiväkirjanani syväoppimisen ja neuroverkkojen alalle.

Seuraavassa kirjoituksessa mennään suoraan asiaan. Esittelen, kuinka koulutin neuroverkon tunnistamaan karhulajeja.

## Linkkejä artikkelista

1. [MOOC.fi](https://www.mooc.fi/) Etsi täältä kursseista Data analysis with Python
2. [Crash Course AI](https://thecrashcourse.com/courses/ai)
3. [course.fast.ai](https://course.fast.ai/)
