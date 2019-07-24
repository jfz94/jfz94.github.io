---
layout: post
title: What is Conga Composer?
---

<div style="text-align:justify;">
<p>Conga composer is a tool which makes document generation easy and accurate. With Conga composer we are able to merge our data into templates in order to improve our document automation in Salesforce.</p>

<p>If, like me at first, you can't think of how to use this tool, think about automating documents like contracts, invoices, brochures and even payments for any kind of business.</p>

<p>The part that concerns me, is the correct configuration of Conga Composer in the org that you are interested to use it. So, firstly, you should download the app in the appExchange page.</p>

<p>Once you have done that, a lot of dependencies should have been created like an app or custom objects like Conga Query, Conga Template or Conga Email Template. </p>

<p>What I've learned about that merging process, is that each object has a particular function.</p>
	<ul>
		<li><span span style="font-weight:bold;">Conga Query</span>: Object that keep SOQL queries where you request the fields that you will need to display in your template.</li>
		<li><span span style="font-weight:bold;">Conga Template</span>: Object that keep your templates in Salesforce where you'll write the fields needed with the help of the tool included in the package called <a href="https://support.getconga.com/Conga_Composer/Creating_Composer_Templates/Composer_Template_Basics/03_The_Template_Builder">Template Builder</a>.</li>
		<li><span style="font-weight:bold;">Conga Email Template</span>: Object that keep your email templates in Salesforce. Similar to the Conga Template object but instead of keeping templates that later can be used as an attachment, here what is stored is the content of an email with the fields that should be merged like a customer's name.</li>
	</ul>

<p>Firstly, we must know how to create a Conga Composer solution by us. In order to achieve that goal, I found very useful this <a href="https://support.getconga.com/Conga_Composer/Building_Composer_Solutions/Using_Composer/02_Create_a_Conga_Composer_Solution_Manually">link</a>.</p>

<p>Basically, in that link is explained that you need a custom button called "Conga Composer" for example, with the basic setup in order to complete the process. The button will contain values such as the session id, serverUrl or the record Id from which we will merge the fields.</p>

<p>Once you have completed this step, I recommended you to use another custom button and start adding the custom logic for your manual solution adding attributes to the button such as reportId (if you have decided to use reports instead of queries), queryId (if you are using a conga query), the templateId and the CongaEmailTemplateId.</p>

<p>As said in the last paragraph, the automation can be done using reports instead of queries. I've builded the whole process using queries and using <a href="https://support.getconga.com/Conga_Composer/Gathering_Data_for_Composer/Data_Gathering_Basics/Dynamically_Filter_Reports_and_Queries_with_pv_values">dynamic reports</a>.</p>

<p>One important drawback when using dynamic reports, is that we are using the field label instead of the API name, so if our org has some fields translated in other languages, the merge won't be done correctly so I recommend you to use always the queries path for merging fields in Conga Composer. It's also important to be sure that the users allowed to execute this automated process can have visibility to the report.</p>

<h2>Template Builder</h2>

<p>An important thing to know when using Conga Composer is the data that will be shown in the Template Builder. In Conga, the master object, the object identified with the ID parameter in our solution URL or button, determines what data is displayed in the Template Builder. In that tool, is displayed custom and standard fields.</p>

<p> Check this <a href="https://support.getconga.com/Conga_Composer/Creating_Composer_Templates/Composer_Template_Basics/04_About_Data_in_the_Template_Builder">link</a> if you still have doubts regarding why some fields that you may expect to appear in the Template Builder are not being showed. For me, this link is basic to understand how Conga works and understand the field visibility in that basic tool of the merge process. </p> 

<h2>IF statements in Conga Composer</h2>

<p>If fields (also called “if statements”) allow you to compare two values and display document content based on the result of the comparison as Conga Composer official documentation explain.</p>

<p> What I can say about "if statements" in Conga Composer that are very simple to be build. The difficulty comes when you start nesting more than one "if", using custom fields, etc but they are a great way to display different content, including hide, varying on different conditions for example the Status field of a contract.</p>

<p>If in your template you need "if statements", I'll recommend you to check this <a href="https://support.getconga.com/Conga_Composer/Creating_Composer_Templates/Word_Templates/Advanced_Word_Templates/How_to_Create_IF_Fields_in_a_Microsoft_Word_Template">link</a> of the Conga official site, in which there's a video and best practices to follow.</p>
</div>