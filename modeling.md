---
layout: default
title: Modeling Snippets
---

[Institute Modeling](#institute) | [Demographic Modeling](#demographics) |  [Fine Field of Study](#finefield)

<article class="mb-5" id="modelingsnippets">
<content>
  
  
<h2 id="modelingabout">Ontology Composition</h2>
  <p>Our ontology is designed around the central institute class (indo:Institute). We include the entities and attributes based on the factors affecting graduate mobility. These factors were based on the information gathered through the literature survey and the available heterogeneous resources. we modeled our ontology in a five-level hierarchy system to allow our users to get as general as the institute's overall doctoral recipients statistics or as specific as the fine field of study statistics. <a href="#fig1">Figure. 2</a> represents the top-level conceptual diagram of our ontology depicting the major classes. Currently the system is modeled to store the statistical values for each class (sio:hasValue) but can be expanded to incorporate any other information related to an institute.</p>
    
	<img src="../images/TopLevel.png" style="width:100%; height:100%"/>  
  <caption id="fig1">Fig 1. A conceptual diagram depicting the top-level classes of our Institute Demographic Ontology.</caption>
	
  <article class="mb-5" id="institute">
<content>
  
  
<h3>Institute Modeling</h3>
  <p>We identified nine explanation types, each with different foci and generational needs, from a literature review we conducted in the computer science and adjacent explanation science domains of philosophy and social sciences. Utilizing the schema provided by our explanation ontology, we can encode the generational needs of these explanation types as OWL restrictions. Below for each explanation type, we present our description, a prototypical question they can address in a clinical setting and the logical formalization of the explanation type. The explanation types are:</p>
  
  <h3 id="demographics"> Demographic Modeling </h3>
  <p class="message">We depict logical formalization of our encoding of the generational needs for explanation type in <a href="https://www.w3.org/TR/owl2-manchester-syntax/">Manchester OWL syntax</a>, in that classes in the OWL restriction are referred to via their labels, and the color highlights are similar to those that can be viewed in Protege. These logical formalizations presented against the <strong>OWL restrictions</strong> label for each explanation type are a representation of the <strong>sufficiency conditions</strong> mentioned before the restrictions.</p>
 
 <h3 id="finefield"> Fine Field of Study Modeling </h3>
  <p class="message">We depict logical formalization of our encoding of the generational needs for explanation type in <a href="https://www.w3.org/TR/owl2-manchester-syntax/">Manchester OWL syntax</a>, in that classes in the OWL restriction are referred to via their labels, and the color highlights are similar to those that can be viewed in Protege. These logical formalizations presented against the <strong>OWL restrictions</strong> label for each explanation type are a representation of the <strong>sufficiency conditions</strong> mentioned before the restrictions.</p>
 
 </content>
 
 
