---
layout: post
title: Persona Card
date: 2018-01-04 06:20:00
tags: web
---

  Persona Card is a new approach to one of the UX methodologies, persona, which automatically creates the demographic part of personas based on reliable data. I used **the 2015 Korean Media Panel Survey dataset** where the respondents recorded their media usage every 15-minute for three days, and visualized it with **d3.js**. The web-based visualization shows how the data-driven approach can be aggregated with the conventional approach of persona.
<br />
- **targe user**: UX designers working in the media field
- **main functions**
  - to help target users to identify different groups of media users
  - to help target users to compare different groups of media users
- **dataset**
  - [the 2015 Korean Media Panel Survey dataset](http://stat.kisdi.re.kr/Library/Library_Detail4.aspx#) (Accessed: 10-Nov-2016)
  - consists of 2 parts: (1) demographic information (2) behavioral information (media usage journal)

![personacard]({{ site.baseurl }}/images/personacard.png)
<br />

- **visualization**
  - _Purpose of the primary medium usage_(d15AA1\~d15AA96) _and Purpose of the secondary medium usage_(d15AB1\~d15AB96) include watching live terrestrial TV shows, reading books, playing games, etc. As they are the most interesting part to designers to distinguish different groups of media users, they are the basis for the main visualization, treemap①. If a user clicks any cell of the treemap, she or he will see the relevant persona card on the right side with the percentage written on it②. Although it is another interesting topic to study the interaction of the primary and secondary media usage, it is not considered and those two are simply added.
  - _Time spent for each purpose of the medium usage_(d15time1\~d15time40) is represented by the color(saturation) of the treemap, while its count is represented by the size. In other words, the size indicates how many users choose that purpose as their primary or secondary ones and the color how long users stay in the medium for that purpose. If a user clicks to see the relevant persona card, she or he will not only see the average time spent for that purpose per day③, but also the average of the total time spent on all media per day④. It is thus possible to grasp how engaged the persona is with that purpose of medium usage.
  - _Sex_(d15gender) _and Age_(d15age) play a vital role in persona creation in that humans cannot imagine a person without those information. Persona Card replaces the conventional photo of persona with a proper illustration. For example, of those who read books most of the time, about 50.93% are female and the rest are male; about 57.24% are in their 10s and the rest are in their 20s, 30s, 40s, or so. So this group is represented by the illustration of a teenage girl⑤.
  - _Primary medium type_(d15MA1\~d15MA96) _and Secondary medium type_(d15MB1\~d15MB96) are hardware types such as Home TVs, Smartphones, Basic mobile phones, etc. Though these are not reflected in the treemap, persona cards provide their rankings⑥.

:exclamation: The working example is being prepared.
