---
layout: default
title: Competency Questions
---
[Questions](#competencyquestions) | [SPARQL Queries](#sparql) 

<article class="mb-5" id="competencyquestions">
  
<h2>Example of Competency Questions</h2>
  <p>We have crafted a set of competency questions to demonstrate the use of our ontology for aspiring graduate students or someone who would want to use our system for understanding an institute's doctoral recipients demographics. We first present a table of our competency question list and the corresponding candidate responses. We then present SPARQL query implementations for these questions. Each query is exactly the one used on Blazegraph Workbench to retrieve the demonstrated results; screenshots from the platform.</p>
  <p>In our example, a female student wants to understand the demographic of the doctoral recipients for University of California, Berkeley to make a decision on whether to enroll in their Mathematics and Computer Science doctoral program. </p>
  <table>
<thead>
  <tr>
    <th>Example Competency Question</th>
    <th>Candidate Response</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><a href="#question1">(Q1).</a>A given year's total doctoral recipients from US institutes between 1958 and 2019. For example, how many total doctoral recipients were there from 1960-62 and 2016-19 from US institutes?</td>
    <td>The number of doctoral recipients for the provided years. The information source is also available.</td>
  </tr>
  <tr>
    <td><a href="#question2">(Q2).</a>US institute that graduated the most doctorates in a given year and the binary gender representation of those students. For example, what is the US Institute with the maximum doctoral recipients in 2019 and how many of them were females?</td>
    <td>The institute's name with highest number of doctoral recipients. The number of institiute's doctoral recipients from the required binary gender.</td>
  </tr>
  <tr>
	  <td><a href="#question3">(Q3).</a>Number of &lt;marginalized community&gt; doctoral recipients from institutes at a given location. For example, provide the number of female doctoral recipients from institutes in California.</td>
    <td>Name of doctoral granting institutes at the provided location. Total doctoral recipients from those institutes for year 2019. Number of those students from the required marginalized community. <br>Source of information can also be provided. </td>
  </tr>
  <tr>
    <td><a href="#question4">(Q4).</a>Institute with the most doctoral students in a given field of study. How many of those were from their marginalized community? For example, how many female doctoral recipients in 2019 were from University of California Berkeley, in Mathematics and Computer Science graduate program?</td>
    <td>Institute's name with maximum doctoral recipient from the required field of study. The number of total doctoral recipient and doctorates from that field. The number of students from the required marginalized community in the field of study. This query integrates datapoints from multiple NSF tables and the source of information can be provided.</td>
  </tr>
  <tr>
    <td><a href="#question5">(Q5).</a>The percentage of &lt;marginalized group&gt; doctoral recipients in a particular institute or its program in a given year? (response provided rounded of to nearest integer). This could also be used to compare the &lt;marginalized community&gt; percentages among programs or institutes. For example, what was the percentage of female doctoral recipients from University of California, Berkeley and Walden University in 2019? </td>
	<td>Institute's name, overall total doctoral recipient from the institute or from its mentioned programs. Number of these doctoral recipients from the required marginalized community and the percentage (currently nearest integer). The source of information can also be extracted.  </td>
  </tr>
</tbody>
</table>


<h3 id="sparql">SPARQL Queries</h3>
<ol>
  <li id="question1"><strong>How many total doctoral recipients were there from 1960-62 and 2016-19 from US institutes?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix indoi: <http://www.semanticweb.org/neha/2021/indo_individual#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Year ?DoctoralRecipients ?NSFTable
WHERE {
  indo:Year ?p ?o .
  ?s rdf:type indo:Year .
  ?s sio:SIO_000300 ?Year .
  ?s indoi:hadDoctoralRecipients ?b .
  ?b sio:SIO_000300 ?DoctoralRecipients .
  ?c indoi:hasPart ?b .
  ?c rdfs:label ?NSFTable .
  FILTER ((?Year >1959 && ?Year <1963) || (?Year >2015 && ?Year <2020))
}
      </pre>
	 </li>
  </ul>
  <figure>
  <img src ="../images/QUERY1RESULTS.png" style="width:100%; height:100%">  
  <figcaption>Fig 1. Blazegraph Workbench Output for the Query 1</figcaption>  
  </figure>
  </li>  
<br><br>
  
  <li id="question2"><strong>What is the US Institute with the maximum doctoral recipients in 2019 and how many of them were females?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix indoi: <http://www.semanticweb.org/neha/2021/indo_individual#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?Rank ?TotalDoctoralRecipients ?Female
WHERE{
  ?i rdf:type indo:Institute.
  ?i indoi:hasDoctoralRecipientsRankBySex ?r .
  ?i indoi:name ?Institute.
  ?r sio:SIO_000300 ?Rank .
  ?i indoi:hadDoctoralRecipients ?v.
  ?v sio:SIO_000300 ?TotalDoctoralRecipients .
  ?i indoi:hasDemographics ?d .
  ?d rdf:type indo:Female .
  ?d sio:SIO_000300 ?Female .
  Filter(?Rank=1)
}
      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../images/cQUERY2RESULT.png" style="width:100%; height:100%">  
 <figcaption>Fig 2. Blazegraph Workbench Output for the Query 2</figcaption> 
 </figure>
  </li>  
  <br><br>
   
  <li id="question3"><strong>Provide the number of female doctoral recipients from institutes in California.</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix indoi: <http://www.semanticweb.org/neha/2021/indo_individual#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?TotalDoctoralRecipients ?Female
WHERE{ 
  ?i rdf:type indo:Institute.
  ?i indoi:inState ?s.
  ?i indoi:hadDoctoralRecipients ?dr.
  ?dr sio:SIO_000300 ?TotalDoctoralRecipients .
  ?i indoi:name ?Institute .
  ?i indoi:hasDemographics ?d .
  ?d rdf:type indo:Female .
  ?d sio:SIO_000300 ?Female .
  FILTER(?s = "California")
}
      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../images/cQUERY3RESULTS.png" style="width:100%; height:100%">  
 <figcaption>Fig 3. Blazegraph Workbench Output for the Query 3 part of NSF 2019 Doctoral Recipients Survey Results Table 3 </figcaption> 
 </figure>
  </li>  
<br><br>
   
  <li id="question4"><strong>How many female doctoral recipients in 2019 were from University of California Berkeley, in Mathematics and Computer Science graduate program?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix indoi: <http://www.semanticweb.org/neha/2021/indo_individual#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?TotDocRec ?OfferedDegree ?TotalInDegree ?FemaleInDegree
WHERE{ 
  ?i rdf:type indo:Institute.
  ?i indoi:hadDoctoralRecipients ?v.
  ?v sio:SIO_000300 ?TotDocRec .
  ?i indoi:name ?Institute .
  ?i indoi:offersGradDegreeIn ?g .
  ?g indoi:name ?OfferedDegree .
  ?g sio:SIO_000300 ?TotalInDegree .
  ?g indoi:hasDemographics ?d .
  ?d rdf:type indo:Female .
  ?d sio:SIO_000300 ?FemaleInDegree .
  FILTER (?Institute = "UniversityOfCaliforniaBerkeley" && ?OfferedDegree = "MathematicsAndComputerScience")  
}
      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../images/cQUERY4RESULTS.png" style="width:100%; height:100%">  
 <figcaption>Fig 4. Blazegraph Workbench Output for the Query 4. Combined data points frompart of NSF 2019 Doctoral Recipients Survey Results Table 3 and 4.  </figcaption>
 </figure>

  </li>  
  <br><br>
    
  <li id="question5"><strong>What was the percentage of female doctoral recipients from University of California, Berkeley and Walden University in 2019?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix indo: <http://www.semanticweb.org/neha/2021/indo#>
prefix indoi: <http://www.semanticweb.org/neha/2021/indo_individual#>
prefix sio:<http://semanticscience.org/resource/>

SELECT DISTINCT ?Institute ?TotDocRec?FemaleInDegree ?PerFemaleDR
WHERE{ 
  BIND (xsd:integer((?FemaleInDegree/?TotDocRec)*100) AS ?PerFemaleDR) .
  ?i rdf:type indo:Institute.
  ?i indoi:name ?Institute .
  ?i indoi:hadDoctoralRecipients ?dr .
  ?dr sio:SIO_000300 ?TotDocRec .
  ?i indoi:hasDemographics ?d .
  ?d rdf:type indo:Female .
  ?d sio:SIO_000300 ?FemaleInDegree .
  FILTER (?Institute = "UniversityOfCaliforniaBerkeley" || ?Institute = "WaldenUniversity")
}
      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../images/cQUERY5RESULTS.png" style="width:100%; height:100%">  
 <figcaption>Fig 5. Blazegraph Workbench Output for the Query 5 part of NSF 2019 Doctoral Recipients Survey Results Table 3 </figcaption> 
 </figure>
  </li>  
  
</ol>

