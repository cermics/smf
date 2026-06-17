---
layout: page
cover-img: /assets/images/coriolis6.jpg
---

### Groupe de Travail Méthodes Stochastiques et Finance

#### Informations pratiques:
  Le mardi à 14h00,  Salle de séminaire du CERMICS, B211.  
  Contacts: <A HREF="mailto:aurelien.alfonsi[ at ]enpc.fr">Aurélien Alfonsi</A>,
  <A HREF="mailto:ahmed.kebaier[ at ]univ-evry.fr">Ahmed Kebaier</A>.
  
#### Future sessions

{% assign future =  site.data.smf | where_exp: "item", "item.status == 'future'" %}
{% for link in future %}
{% if link.sem == "scommun" %}
{{ link.date | date : "%B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}{% endif %}: **{{ link.AU }}**,  
*{{ link.TI }}*.
{% for sublink in link.PROG %}
 - {{ sublink.hour }}: **{{ sublink.AU }}**,  
 *{{ sublink.TI }}*.
{% endfor %}
{% else %}
{% include smf_one.html %}
{% endif %}

-------------------------
{% endfor %}

#### Past sessions 
{% assign year = "3000" %}

{% assign past =  site.data.smf | where_exp: "item", "item.status == 'past'" %}
{% for link in past %}
{% assign link_year = link.date | date : "%Y" %}
{% if link_year != year %}{% assign year = link_year %}<h3>{{ year }}</h3>{% endif %}
{% if link.sem == "scommun" %}
{{ link.date | date : "%B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}{% endif %}: **{{ link.AU }}**,  
*{{ link.TI }}*.
{% for sublink in link.PROG %}
 - {{ sublink.hour }}: **{{ sublink.AU }}**,  
 *{{ sublink.TI }}*.
{% endfor %}
{% else %}
{% include smf_one.html %}
{% endif %}

-------------------------
{% endfor %}


