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
  <li id="question1"><strong>Total doctoral recipients from US Universities from 1959-1962 and 2016 to 2019 and the source?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Year ?DoctoralRecipients ?NSFTable
WHERE {
  indo:Year ?p ?o .
  ?s rdf:type indo:Year .
  ?s sio:SIO_000300 ?Year .
  ?s indo:hadDoctoralRecipients ?b .
  ?b sio:SIO_000300 ?DoctoralRecipients .
  ?c indo:hasPart ?b .
  ?c rdfs:label ?NSFTable .
  FILTER ((?Year >1959 && ?Year <1963) || (?Year >2015 && ?Year <2020))
  }
      </pre>
	 </li>
  </ul>
  <img src ="../images/QUERY1RESULTS.png" style="width:100%; height:100%">  
 <caption>Fig 1. Blazegraph Workbench Output for the Query 1</caption>  
  </li>  
  <li> </li>
  
  <li id="question2"><strong>Institute with maximum doctoral recipient in US in 2019?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?Rank ?TotalDoctoralRecipients
WHERE{
  ?s rdf:type indo:Institute.
  ?s indo:hasDoctoralRecipientsRankBySex ?o .
  ?s indo:name ?Institute.
  ?o sio:SIO_000300 ?Rank .
  ?s indo:hadDoctoralRecipients ?v.
  ?v sio:SIO_000300 ?TotalDoctoralRecipients .
  Filter(?Rank=1)
}
      </pre>
	 </li>
  </ul>
 <img src ="../images/cQUERY2RESULT.png" style="width:100%; height:100%">  
 <caption>Fig 2. Blazegraph Workbench Output for the Query 2</caption> 
  </li>  
   <li> </li>
   
  <li id="question3"><strong>How many female doctoral recipients in 2019 were from University of California Berkeley, in Mathematics and Computer Science graduate program?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?OfferedDegree ?TotalInDegree ?FemaleInDegree
WHERE{ 
  ?i rdf:type indo:Institute.
  ?i indo:hadDoctoralRecipients ?v.
  ?i indo:name ?Institute .
  ?i indo:offersGradDegreeIn ?g .
  ?g indo:name ?OfferedDegree .
  ?g sio:SIO_000300 ?TotalInDegree .
  ?g indo:hasDemographics ?d .
  ?d rdf:type indo:Female .
  ?d sio:SIO_000300 ?FemaleInDegree .
  FILTER (?Institute = "UniversityOfCaliforniaBerkeley" && ?OfferedDegree = "MathematicsAndComputerScience")  
}
      </pre>
	 </li>
  </ul>
 <img src ="../images/cQUERY3RESULTS.png" style="width:100%; height:100%">  
 <caption>Fig 3. Blazegraph Workbench Output for the Query 3 part of NSF 2019 Doctoral Recipients Survey Results Table 3 </caption> 
  </li>  
  <li> </li>
   
  <li id="question4"><strong>how many female doctoral recipients in 2019 were from University of California Berkeley, in Mathematics and Computer Science graduate program?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?TotDocRec ?OfferedDegree ?TotalInDegree ?FemaleInDegree
WHERE{ 
  ?i rdf:type indo:Institute.
  ?i indo:hadDoctoralRecipients ?v.
  ?v sio:SIO_000300 ?TotDocRec .
  ?i indo:name ?Institute .
  ?i indo:offersGradDegreeIn ?g .
  ?g indo:name ?OfferedDegree .
  ?g sio:SIO_000300 ?TotalInDegree .
  ?g indo:hasDemographics ?d .
  ?d rdf:type indo:Female .
  ?d sio:SIO_000300 ?FemaleInDegree .
  FILTER (?Institute = "UniversityOfCaliforniaBerkeley" && ?OfferedDegree = "MathematicsAndComputerScience")  
}
      </pre>
	 </li>
  </ul>
 <img src ="../images/cQUERY4RESULTS.png" style="width:100%; height:100%">  
 <caption>Fig 4. Blazegraph Workbench Output for the Query 4. Combined data points frompart of NSF 2019 Doctoral Recipients Survey Results Table 3 and 4.</caption> 
  </li>  
  
</ol>

  
</content>
