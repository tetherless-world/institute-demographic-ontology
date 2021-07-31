---
layout: default
title: Competency Questions
---
[Competency Question 1](#question1) | [SPARQL Queries](#sparql)

<article class="mb-5" id="competencyquestions">

<content>
<ol>
<li> <a href="#question1">(Q1).</a> <strong>General</strong>: A given year's total doctoral recipients from US institutes between 1958 and 2019. 
	<ul type = "circle">
	<li><strong>Example</strong>: How many total doctoral recipients were there from 1960-62 and 2016-19 from US institutes?
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
	<figure>
  		<img src ="../images/QUERY1RESULTS.png" style="width:100%; height:100%">  
  		<figcaption>Fig 1. Blazegraph Workbench Output for the Query 1</figcaption>  
 	</figure>
</li>

<li> <a href="#question1">(Q1).</a> <strong>General</strong>: A given year's total doctoral recipients from US institutes between 1958 and 2019. 
<ul type = "circle">
<li><strong>Example</strong>: How many total doctoral recipients were there from 1960-62 and 2016-19 from US institutes?
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
<figure>
<img src ="../images/QUERY1RESULTS.png" style="width:100%; height:100%">  
<figcaption>Fig 1. Blazegraph Workbench Output for the Query 1</figcaption>  
</figure>
</li>
</ol>

</content>
