---
layout: default
title: Competency Questions
---
[Questions](#competencyquestions) | [SPARQL Queries](#sparql)

<article class="mb-5" id="competencyquestions">

<h2>Example of Competency QUestions</h2>
	<p>We have crafted a set of competency questions to demonstarte the use of our ontology for aspiring graduate students or someone who would want to use our system for understanding an institute's doctoral recipients demographics. We first present a table of our competency question list and the corresponding candidate responses. We then present SPARQL query implementations for these questions.</p>
	<table>
		<thead>
			<tr>
				<th>Example Competency QUestion</th>
				<th>Candidate Response</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><a href="#question1">(Q1).</a> A given year's total doctoral recipients from US institutes between 1958 and 2019. <br>For example, how many total doctoral recipients were there from 1960-62 and 2016-19 from US institutes?</td>
				<td>The number of doctoral recipients for the required year/s. The information source is also available. </td>
			</tr>
			<tr>
				<td><a href="#question2">(Q2).</a> US institute that graduated the most doctorates in a given year and the binary gender representation of those students.<br> For example, what is the US Institute with the maximum doctoral recipients in 2019 and how many of them were females?</td>
				<td>The institute's name with highest number of doctoral recipients. <br>The number of institiute's doctoral recipients from the required binary gender. </td>
			</tr>
			<tr>
				<td><a href="#question3">(Q3).</a> Number of <marginalized community> doctoral recipients from institutes at a given location.<br> For example, provide the number of female doctoral recipients from institutes in California.</td>
				<td>Name of doctoral granting institutes at the provided location. <br>Total doctoral recipients from those institutes for year 2019. <br>Number of those students from the required marginalized community. <br>Source of information can also be provided. </td>
			</tr>
			<tr>
				<td><a href="#question4">(Q4).</a> Institute with the most doctoral students in a given field of study. How many of those were from their marginalized community?<br> For example, how many female doctoral recipients in 2019 were from University of California Berkeley, in Mathematics and Computer Science graduate program?</td>
				<td>Institute's name with maximum doctoral recipient from the required field of study. <br>The number of total doctoral recipient and doctorates from that field. <br>The number of students from the required marginalized community in the field of study. <br>This query integrates datapoints from multiple NSF tables and the source of information can be provided.</td>
			</tr>
			<tr>
				<td><a href="#question5">(Q5).</a> The percentage of <marginalized group> doctoral recipients in a particular program or the institute in a given year? (response provided rounded of to nearest integer).<br> This could also be used to compare the <marginalized community> percentages among programs or institutes.<br> For example, what was the percentage of female doctoral recipients from University of California, Berkeley and Walden University in 2019? </td>
				<td>Institute's name, overall total doctoral recipient from the program/institute. <br>Number of these doctoral recipients from the required marginalized community and the percentage (currently nearest integer). <br>The source of information can also be extracted.  </td>
			</tr>
		</tbody>
	</table>
