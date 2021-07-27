---
layout: default
title: Competency Questions
---
[Questions](#competencyquestions) | [SPARQL Queries](#sparql) 

<article class="mb-5" id="competencyquestions">
<content>
  
  
<h2>Example of Competency Questions</h2>
  <p>We have crafted a set of competency questions to demonstrate the use of our ontology for aspiring graduate students or someone who would want to use our system for understanding an institute's doctoral recipients demographics. We first present a table of our competency question list and the corresponding candidate responses. We then present SPARQL query implementations for these questions.</p>
  <table>
<thead>
  <tr>
    <th>Example Competency Question</th>
    <th>Candidate Response</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><a href="#question1">(Q1).</a> How many doctorar recipients were their in a given yearfrom US institutes. <br> Example,Year wise doctoral recipients in the United States of America for year range 1958-2019 </td>
    <td>The entire NSF doctoral recepients survey 2019 Table 1 data points</td>
  </tr>
  <tr>
    <td><a href="#question2">(Q2).</a> Institute with maximum doctoral recipients in 2019. Its location. <br>How many of those were males and females. <br>What is the source of the information</td>
    <td>Name and location of the institute with maximum doctoral recipient for 2019<br> Number of Males and Females comprising the total number of doctoral recipients from that institute<br>Provenance - the NSF Doctoral Recipients Survey Table number and title</td>
  </tr>
  <tr>
    <td><a href="#question2">(Q3).</a>Institute with maximum doctoral student in a given field of study (example Life Science). <br> It's location. How many of those were males and how many of those were females</td>
    <td>The name and location of the institute with maximum doctoral recipient in the given field (say Life Science),<br> the number of males and females graduated from the institute in the given field.</td>
  </tr>
</tbody>
</table>

<h3 id="sparql">SPARQL Queries</h3>
<ol>
  <li id="question1"><strong>Total doctoral recipients from US Universities from 1958 and the source?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix rdfs:<http://www.w3.org/2000/01/rdf-schema#>
prefix owl:<http://www.w3.org/2002/07/owl#>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix sio:<http://semanticscience.org/resource/>
prefix prov: <http://www.w3.org/ns/prov#>

SELECT ?Year ?DoctoralRecipients ?NSFTable
WHERE {
  indo:Year ?p ?o .
  ?s rdf:type indo:Year .
  ?s sio:SIO_000300 ?Year .
  ?s indo:hadDoctoralRecipients ?b .
  ?b sio:SIO_000300 ?DoctoralRecipients .
  ?b indo:hasPart ?c .
  ?c sio:SIO_000300 ?NSFTable .
  }

      </pre></li>
      <li><strong>Response</strong> <br>
  <table>
<thead>
  <tr>
    <th>Year</th>
    <th>DoctoralRecipients</th>
    <th>NSFTable</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>1958</td>
    <td>8773</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>1959</td>
    <td>9213</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>1960</td>
    <td>9722</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>1961</td>
    <td>10413</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>1962/td>
    <td>11500</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>........</td>
    <td>..........</td>
    <td>.........................................</td>
  </tr>
  <tr>
    <td>2015</td>
    <td>54886</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>2016</td>
    <td>54809</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>2017</td>
    <td>54554</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>2018</td>
    <td>55103</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
  <tr>
    <td>2019</td>
    <td>55703</td>
    <td>NSF_Table1_DoctoralRecipients<br>USUniversities2019</td>
  </tr>
</tbody>
</table>
  </li>
  </ul>
  </li>
  
</ol>
  </content>
