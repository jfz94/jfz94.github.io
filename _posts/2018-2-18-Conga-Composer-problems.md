---
layout: post
title: Conga Composer, common problems with solutions
---

<div style="text-align:justify;">
<p>In my previous post, I gave a general idea about Conga Composer and each of the elements that composed this merge process.</p>

<p>However, in this one I'll try to cover common problems that I've discovering while using Conga Composer.</p>

<h2>Reports and translated field labels</h2>

<p>Well, I don't know if this topic it should be categorized as a "problem", but once I tried to use dynamic reports with Conga because I hoped it will be a better solution for a specific task where I need to repeat more than a row in a table and despite, it is said in the official Conga Composer documentation, it seems weird that when using reports we take the field label name instead of the API name when doing the merge.</p>

<p>A big disadvantage of this is that if we have been translating the labels for different languages used in our org, the merge process won't be completed as expected. <span style="font-weight:bold">Solutions</span>: Use a different template for each language (not seems the better idea, for sure) or use SOQL Queries instead of reports.</p>

<h2> Picklists fields in if statements</h2>

<p>Regarding the previous "problem", the following topic maybe it should be categorized as a "reminder". When using IF statements with picklists fields you have to remember if we have been using reports or queries. For queries you should add the API Name of the picklist value that you want to add to the statement while for reports you should add the value.</p>

<p>For example: Let's imagine we are using a picklist field called Customer Priority and we want to use the none value:</p>
	<img src="/assets/images/picklist-value-conga-example.PNG" />
	<ul>
		<li><span style="font-weight:bold">Dynamic report option</span>: {IF "CustomerPriority" = "None" "CustomerPriority" "False value" } </li>
		<li><span style="font-weight:bold">Conga Query option</span>: {IF "CustomerPriority" = "0" "CustomerPriority" "False value" } </li>
	</ul>

<h2>Translated picklist values</h2>

<p>Another problem when using Conga Composer and also regarding the value of our picklists is displaying the value in the correct language of the user. For that, Conga Composer has an attribute called <a href="https://support.getconga.com/Conga_Composer/Customizing_Composer_with_Parameters/Composer_Parameter_Guide/TPV">TPV</a>.</p>

<p>If we add this setting to the custom button where we will add the merging process, we will be able to retrieve the translated values of the picklists.</p>

<p>I hope that with this post I can help some of you.</p>

</div>