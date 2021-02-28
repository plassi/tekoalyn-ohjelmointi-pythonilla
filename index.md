Tietoa tekoälyn perusteista ja neuroverkkojen teoriasta on jo kerääntynyt ja nyt on aika harjoittaa neuroverkkoja käytännössä.

Tämä blogi on päiväkirjani oppimismatkasta tekoälyn ohjelmointiin Pythonilla ja sen pitkälle kehitetyillä tekoälykirjastoilla, fast.ai:lla ja PyTorchilla.

Tulen kirjoittamaan blogiin lisäksi tekoälyn perusteista ja soveltamisesta, sekä seuraan alan kehitystä.

<ul>
  {% for post in site.posts %}
    <li>
      {{ post.date | date: "%d.%m.%Y" }}<br>
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
