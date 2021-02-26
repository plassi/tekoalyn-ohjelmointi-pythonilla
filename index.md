Hei,

Olen 38-vuotias, lähes koko elämäni tietokoneiden parissa kaikenlaista tehnyt. Ohjelmoinnin ja sen opiskelun aloitin vakavissani kolmisen vuotta sitten. 

Tietoa tekoälyn historiasta, teoriasta ja perusteista on jo kerääntynyt ja nyt on aika opetella sen käyttöä.

Tämä blogi on oppimispäiväkirjani tekoälyn ohjelmoinnista Pythonilla ja sen pitkälle kehitetyillä tekoälykirjastoilla, fast.ai:lla ja PyTorchilla.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ site.baseurl }}/{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
