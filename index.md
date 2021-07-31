---
layout: default
title: Institute Demographic Ontology (InDO)
---

[Abstract](#abstract) | [Resources](#resources) | [Tools Used](#toolsused)


<h1 class="page-title" style="text-transform:uppercase;" id="header">INSTITUTE DEMOGRAPHIC ONTOLOGY (InDO)</h1>
<h3 style="color:dimgrey;">Neha Keshan, Kathleen Fontaine, James A. Hendler</h3>
<h3><a href="https://www.rpi.edu/">Rensselaer Polytechnic Institute</a></h3>
<p class="message">A website to navigate resources open-sourced via the associated KGSWC 2021 submission. Use the side navigation panel to explore different sections of the website and click on an add symbol for more navigation options under some sections.</p>

<hr>
<article class="mb-5" id="abstract">
<content>
  
  
<h2>Abstract</h2>
  <p>Graduate education institutes in the United States (US) have been working on programs to increase the number of students and faculty from marginalized communities. When choosing to pursue a doctoral degree, the common question is 'where is the best fit for me?' Aspiring graduate students may feel the need for a reference point - someone with a similar background who has experienced or is currently experiencing the doctoral process, whether that be a student or a faculty member. Currently, there is no single location where that question can be answered for those in marginal communities, however answering that question also has an impact on the student's post-graduation career path. In lieu of a single person, and to help provide information critical to answering the question, we built the Institute Demographic Ontology (InDO). InDO integrates US graduate institute's doctoral recipient demographic data with data describing broad field of study, fine field of study, and the pursued career path to produce a knowledge graph for each prospective student's query. The terminology is structured in five levels of hierarchy providing room for the most abstract top level (basic components used to describe an institute's demographics), to the most concrete bottom levels (particular graduate program offered by the institute, along with corresponding provenance). Our resource (InDO) could be used by students within a marginalized community in the US to infer whether a given institute has the resources to support a given program, based on demographic information such as number of doctorates awarded in a given field. We design a use case where an InDO-based knowledge graph is created incorporating some of the National Science Foundation (NSF) Doctoral Recipient Survey 2019 data. Our use case demonstrates the usage of InDO in the real world while providing a way to access NSF data in a machine readable format. Evaluation of our ontology is done with a set of competency questions created from the perspective of an aspirant marginalized graduate student who would be willing to use our system to gather information for making an informed decision. InDO provides an ontological foundation towards building a social machine as an aid to higher education and graduate mobility in the US.</p>
 </content>
 
 <hr/>
 <article class="mb-5" id="resources">
<content>
<h2>List of Resources </h2>
<ul>
 <table style="width:100%">
    <tr>
    <th>Resources</th>
    <th>Links</th> 
  </tr>
  <tr>
    <td>Ontology</td>
    <td><a href="ontology">Institute Demographic Ontology</a> </td> 
  </tr>
  <tr>
    <td>Demographics</td>
    <td><a href="modeling#demographics">Modeling</a> </td> 
  </tr>
    <tr>
    <td>NSF Doctoral Recipients Survey 2019 Example</td>
    <td><a href="nsfexample">Use Case</a> </td> 
  </tr>
   <tr>
    <td>Competency Questions </td>
    <td><a href="competencyquestions#sparql">SPARQL Queries</a> </td> 
  </tr>
   <tr>
    <td>Tools Used </td>
    <td><a href="index#toolsused">References to tools used</a> </td> 
  </tr>
</table>
  
 </ul>
 </content>
 
 <hr/>
 
 <article class="mb-5" id="toolsused">
<content>
  
  
<h2>Tools Used during Development</h2>
  <ul>
  <li>Ontology Editor: <a href="https://protege.stanford.edu/products.php#desktop-protege">Protégé 5.5.0</a></li>
  <li>SPARQL Queries ran on <a href="http://sparql.cancerdata.org/#splash">Blazegraph Workbench</a></li>
  <li>RDF Visualization generated with <a href="http://jimmccusker.github.io/rdfviewer/">RDFViewer</a></li>
  </ul>
  </content>

 
