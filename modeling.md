---
layout: default
title: Modeling Snippets
---

[Institute Modeling](#institute) | [Demographic Modeling](#demographics) |  [Fine Field of Study](#finefield)

<article class="mb-5" id="modeling">
<content>
  
  
<h2 id="modelingabout">Ontology Composition</h2>
  <p>Our ontology is designed around the central institute class (indo:Institute). We include the entities and attributes based on the factors affecting graduate mobility. These factors were based on the information gathered through the literature survey and the available heterogeneous resources. we modeled our ontology in a five-level hierarchy system to allow our users to get as general as the institute's overall doctoral recipients statistics or as specific as the fine field of study statistics. <a href="#fig2">Figure. 2</a> represents the top-level conceptual diagram of our ontology depicting the major classes. Currently the system is modeled to store the statistical values for each class (sio:hasValue) but can be expanded to incorporate any other information related to an institute.</p>
    
	<img src="../images/TopLevel.png" style="width:100%; height:100%"/>  
  <caption id="fig2">Fig 2. A conceptual diagram depicting the top-level classes of our Institute Demographic Ontology.</caption>

  
<h3 id="institute">Institute Modeling</h3>
  <p class="message">Each class and attribute is introduced as necessary to construct a model of the institute's doctoral recipient information. We note that all the required institute statistics are based on its demographics (indo:DoctoralRecipients) and the graduate programs (indo:FieldOfStudy) it offers. <a href="#fig3">Figure. 3</a> provides the conceptual diagram of our Institute class modeling.</p>
  
  <img src="../images/institute.png" style="width:100%; height:100%"/>  
  <caption id="fig3">Fig 3. A conceptual overview of our Institute Demographic Ontology's institute class. The arrows depict the subclass relationship between classes while the dashed arrows depict the property association between two classes.</caption>
  
  <h3 id="demographics"> Demographic Modeling </h3>
  <p class="message"></p>
 
 <h3 id="finefield"> Fine Field of Study Modeling </h3>
  <p class="message"></p>
 
 </content>
 
 
