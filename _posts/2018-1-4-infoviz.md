---
layout: post
title: PersonaCard
date: 2018-01-04 06:20:00
categories: Notes
tags: d3.js
---

<h1>PersonaCard: A Data-driven Approach for Creating User Personas</h1>

  **Persona Card** is a new approach that creates the demographic part of personas qualitatively based on reliable data. In this work, we adopted the 2015 Korean Media Panel Survey dataset where respondents recorded their media usage every 15-minute for three days, and implemented the visualization with d3.js. The web-based visualization result shows how the data-driven approach can be aggregated with the conventional qualitative UX approach.
![personacard]({{ site.baseurl }}/images/personacard.png)

----

<h2>1. Introduction</h2>
  When designing a new product or service, UX designers assume their target. It is important because the target is the user they should focus on in User eXperience design. Most of them use the methodology of persona for that purpose, which is creating a fictional character of a prospective user. The details composing persona vary depending on the domain of the prospective product or service; for example, to make an educational mobile application, a student’s favorite subjects and weak subjects should be a part of persona. For this reason, personas have often been created at the discretion of the UX designer.
  In some ways, a persona is a representative of a group of people who share similar traits. If data is qualitatively and quantitatively sufficient, UX designers no longer need to delay in persona creation. With personas generated automatically from data, they can exercise the discretion in other phases such as in-depth interview.
  Persona Card is a new approach that creates the demographic part of personas qualitatively based on reliable data. In this work, we adopted the 2015 Korean Media Panel Survey dataset which contains a vast amount of information in the field of media usage. After exploring the dataset, we implemented the concept with d3.js, with the aim of helping UX designers in media related planning. This contributes to the qualitative and simultaneously quantitative development of UX design, which strengthens itself as a reliable design approach.
  
<h2>2. Design Approach</h2>
  After setting up the target user as UX designers, we simplified the user flow of UX designers when creating persona cards: (1) exploring and (2) analyzing.

<h3>2.1. Phase 1: Explore</h3>
  Before the user explores the dataset, it is assumed that the user wants to design a new product or service in the media related field. Whether the user adopts the top-down approach or the bottom-up approach, it is the behavioral traits of people within the multi-media environment what the user concerns most. For the former approach, the user has the specific target group with special behavioral traits in mind and looks it up at once; for the latter approach, on the other hand, the user wants to explore different types of people who engage themselves in specific media activities. Hence, the first phase of persona creation is defined to exploring the habits or actions of people, so as to limit the functionality of the visualization to fast and accurate persona generation.

<h3>2.2. Phase 2: Analyze</h3>
  If the user has decided on the target group in terms of their behavioral traits, the user wants more detailed information on the group. Although imagining and assuming a persona has relied largely upon qualitative ways, in this visualization, part of persona is created quantitatively based on real data by a simple interaction. With the data-driven persona, the user not only assures him- or herself that the persona is meaningful in the real world, but saves time for other design processes. Moreover, since the persona is created in the form of a card, it can be directly inserted to the persona the user is developing by conducting qualitative research.
  During the analysis, the user may not be convinced enough that the target users behave in a unique manner. For instance, the user wants to see the difference between those who mostly use computer graphics applications and those who mostly use word processors. For this reason, a simple and fast function for comparison is provided in the analyzing phase as well.

<h2>3. Data</h2>
  The data visualized in this work is based on the 2015 Korean Media Panel Survey which has been annually conducted by KISDI STAT from 2010. As persona relates mostly to the user behaviors within their environment, we focus on one version of the original data which comes in three different versions: media diary.
  The dataset consists of two parts: (1) demographic information and (2) behavioral information which respondents recorded by themselves every 15-minute for three days. The variables utilized in the visualization are as follows. (table)

<h2>4. Implementation</h2>
  The dataset is visualized using d3.js, which not only makes it easier to implement, but also makes the final visualization more accessible to anyone connected on the web. The dataset is put in into d3.js after being processed from a Stata dta file to a csv file.
  Sex and age (group) play a vital role in persona creation in that a person cannot exist without them. It is the same thing that humans cannot imagine a person without his or her sex and age. Thus, conventional personas have included a picture of a person on the top, whether it is real or fake.
  Data-based personas contain the percentages of sex and age group. For example, for the group of those who read books most of the time in 2015, about 50.93% were female and the rest were male. Similarly, about 57.24% were teenagers and the rest were in their 20s, 30s, 40s, or so. This information of percentages may interest statisticians, but this is unnecessary for UX designers as no human is 50.93-percent-female and 49.07-percent-male. Therefore, sex and age group are implemented by adopting the one most sex and age group of the selected group and translating them into a proper illustration. To make this clearer, the most sex and age group are written with percentages next to the illustration. Since sex and age group are illustrated twice, conventional color mapping on sex is not redundantly applied.
  Purpose of media usage was recorded twice through two variables because it is common to multi-task with more than one media. Since the relationship between primary media and secondary media is beyond the scope of this work, first- and second-media are integrated into one variable, which shows the most purpose of media usage. As this visualization is targeted for UX designers, purpose of media usage is considered the most important variable to distinguish different personas. Therefore, purpose of media usage is counted per day, and the most purpose of them is derived as a new key for the overall graph, the tree map. In other words, each persona is based on this newly derived variable, the most purpose of media usage per day.
  If the size of tree map reflects the number of those who share the same purpose of media usage, the color of each area of tree map tells the amount of time spent on the media. As size and color respectively shows frequency and amount, users of the visualization, UX designers, grasp the density of the media easily. Users also find the related information highlighted in big letters on the right side if they click each part of tree map. In addition, in order to minimize eye fatigue and effectively display each information, grayscale is used as a color scale for the tree map instead of a colorful color scheme.
  Time spent on each media is summed up for each person and averaged for each persona. That is, this variable does not appear on the tree map which shows the overall media usage of each person, but on the persona card which represents the average media usage of a group of people. Thus, users check how much time the persona spends on any media per day. Furthermore, as this bar graph superimposes time spent on the most purpose of media usage and time spent on all medias, users understand how engaged the persona is toward the most purpose of media usage.
  Media type is distinguished from purpose of media usage in that it is related to the medium. To be specific, if purpose of media usage is an action, media type is a device or a medium. As with time spent on each media, media type variable does not affect the tree map, but it appears on the persona card according to the ranking. It is written in text without graph.

<h2>5. Conclusion</h2>
  A new approach to create data-based personas has been implemented based on web. The 2015 Korean Media Panel Survey dataset is employed to help UX designers generate personas with regard to media usage. Data is selectively processed from the original dataset into meaningful information which is related to the image of persona, engagement, level of immersion, and media connections. The implemented result shows how the data-driven approach can be aggregated with the conventional qualitative UX approach. Additionally, for those who require more complicated and comprehensive information on each persona, the visualization can be further extended in terms of the relationship between primary and secondary media usage, the relationship between sex and age, and the relationship between time and place of media usage.

<h2>References</h2>
- [“KISDI STAT.”](http://stat.kisdi.re.kr/Library/Library_Detail4.aspx#) (Accessed: 10-Nov-2016).
