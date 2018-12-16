---
layout: default
title: Panama Papers
subtitle: Study of the Biggest Leak in History
use-site-title: true
published: true
---
## {{page.subtitle}}  
<br>   
<br>   



### <span style="color:red"> Introduction to the Panama Papers </span>

Panama Papers involved hundred thousands of offshore accounts, millions of documents detailing top secret financial information were leaked in 2015 by an anonymous source. It is estimated that tax havens cost poor countries at least $170 billion in lost tax revenues each year making poorest people lose out and the inequality gap grow. Holding money in an offshore company is generally not illegal but it can be used to launder money, dodge sanctions, avoid taxes. Many people listed in the panama papers claimed being innocent.


<U><b> Some relevant numbers related to Panama papers </b></U>

- 11.5 millions leaked documents that detail financial and attorney–client informations
- More than 214,488 offshore entities involved.
- Some 4.8 millions leaked files were emails, 3 millions were database entries, 2.2 millions PDFs, 1.2 millions images, 320,000 text files, and 2242 files in other formats.
- 2.6 terabyte trove of data at the core of this investigation contains nearly 40 years of records.



<U><b> A word about the dataset before starting </b></U>

Unfortunately, we don't have access to big part of the data and metadata from the original leaks. So, we decided to enrich our data with other similar datasets found in [The International Consortium of Investigative Journalists](https://offshoreleaks.icij.org/pages/database) (ICIJ): *Paradise papers*, *Offshore leaks* and *Bahamas leaks*.

We combined all the datasets together to get more information, and then structured them in 3 relevant datasets. Each one represents a specified role of involved parties:


- <U><i>Entities:</i></U> is a company, trust or fund created in a low tax offshore jurisdiction.
- <U><i>Officers:</i></U> a person or a company who plays role in an offshore entity.
- <U><i>Intermediaries:</i></U> the link between someone seeking an offshore and an offshore service provider.

An other important dataset was used in our analysis which is :

-  <U><i>Edges:</i></U> they connect nodes from the above parts and describe the nature of the relation between them. This dataset was very important especially in network analysis.  


---

### <span style="color:red"> Outline of the project </span>

There is a huge amount of data, our work was to provide a detailed analysis of the dataset. We didn't focus our analysis on specific individuals. we tried instead to get a closer view about the involved countries and the distribution of the papers around the world.We will show you a brief presentation of the involved countries and the connection between them. Finally, we looked for any correlation between the implication of each country in the panama papers with international indexes. We will try to explain the correlation found between Financial Secrecy Index (FSI) and the countries.

<U><b> Research questions </b></U>

- What is the distribution of officers, entities and intermediaries around the world? It is based in specified countries or it is overspread? <br>
- Based on network analysis, how can we describe the relationship and the connection between those countries? <br>    
- Can we relate our rankings to other world known indicators such as Financial Secrecy Index (FSI)? <br>  

We will try to explain the phenomenon by analyzing the datasets in order to understand how much tax evasion is a very important tool for rich people. Our role is not to judge people or jurisdictions. We are just analyzing and interpreting the fact and maybe pushing towards the implementation of new tax regulations to prevent such aberrance.


###  <span style="color:red"> Involved countries </span>
The map below show the worldwide distribution of the three main kinds of actors : which are Offshore entities, intermediaries and officers. We notice that the three of them differ from each other on a global scale even though some countries are "well" represented in all three categories.

<b>PS:</b> We chose to present this map in a log scale to be more significant because the gap is very large between the countries.

<iframe src="countries.html" width="100%" height="400px"></iframe>

<U><b> Entities </b></U>

{% include entities.html %}

Regarding the offshore entities, the presence of economic global powers is clear : US and Russia. But they are other efficient hosting countries. Indeed, in Europe, Switzerland and Malta are leading with a very huge number comparing the other countries followed by Great Britain and Luxembourg. In South America, Panama has a large capital of offshore entities. In western Asia, United Arab Emirates is also leading. It is noticeable that a lot of top countries involved belongs to offshore financial centers according to FMI, which is very logic. Companies look for low tax offshore jurisdiction to maximize their benefits.

<U><b> Intermediaries </b></U>

{% include intermediaries.html %}

To fulfill a tax evasion, the offshore companies also need a go-between with a service provider, these intermediaries usually are law-firms, banks or middlemen that asks an offshore service provider to create an offshore firm for a client. The Intermediaries are once again most located in Hong Kong, Great Britain and Switzerland , as they are known for the privacy of their bank services. Still, the distribution of the intermediaries is very similar to the offshore entities distribution on a global scale. The intermediaries involve mainly in the phases of the identified decision-making cycle (advice, creation, maintenance, enforcement).

<U><b> Active intermediaries </b></U>

{% include active.html %}

Intermediaries play an important role in decision making, which involves more people and juridictions related to Panama papers. That's why, we want to understand more about them and plot the most active intermediaries. Mossack Fonseca worked with intermediaries in more than 100 countries all over the globe. Their most active clients by number of offshore company incorporations were from the United Kingdom, Hong Kong and Switzerland  .

<U><b> Officers </b></U>

{% include officers.html %}


Regarding the officers, It is noticeable to say that most countries involved in entities are present here, which is very logic. But, other countries appeared here, especially Germany, Italy and Russia. It means that officers may have a relationship with companies in those countries. We will explain that in the next part.


To conclude, countries involved in Panama papers are around the world. The offshore entities are not related to Panama or american and european countries. Companies, businessmen, football players and even politicians all around the world had an issue with Panama papers.

<U><b> 40 years of offshore companies opening and closing </b></U>

{% include incorporation.html %}

- *Incorporation year:* the date when an offshore entity was created.
- *Inactivation year:* the date when a client told the agent to deactivate the offshore entity which could be recreated at a later date.

The leaked files from Panama-based law firm Mossack Fonseca contain nearly 40 years of data. Mossack Fonseca’s clients have been rapidly deactivating companies since 2005. The number of incorporations of offshore entities has been decreasing rapidly since 2003.

---


### <span style="color:red"> Network </span>

While it’s true that investigating simple relationships in data could be handled by a relational database, they’re not an especially satisfactory fit, as they represent data as tables, not networks. The ICIJ organization has been using graph database technology to draw links between members of the tax avoiding global elite and bank account held in offshore tax haven.
A network analysis will be held to understand these structures and discover connections in a very intuitive way.

In order to get valuable information from the network we constructed, we tried to use some algorithms to understand the importance of nodes according to their characteristics.


<U><b> Importance of nodes</b></U>

- *Degree centrality:* This algorithm puts into light the countries that have  the biggest number of connections.
This number can be interpreted in terms of the immediate risk of a country being involved in questionable business.


- *Page rank:* This algorithm computes the ranking of the countries in the graph based on the structure of the incoming links.
A country is important if it is pointed by other important countries


- *Betweeness centrality:* The betweenness centrality for each country is the number of the shortest paths that pass through the country.
High betweenness countries are often critical to collaboration across different groups.

Those metrics were the tool that we used to determine the top three most important countries in the network: United Kingdom, Switzerland and Hong Kong.

<iframe src="distributions_of_centrality.html" width="100%" height="400px"></iframe>

This map represents the distribution of degree centralities. This map shows us that a lot of european countries are important in the leaks. No surprise here since the European Parliament's Panama Papers Committee of Inquiry was heavily accusing European governments to have been complicit with money launderers and tax evaders for over 20 years:


<U><b> Importance of edges </b></U>

Another interesting result was obtained by the use of  the edge betweenness centrality:
One could think that the most important edges would be between the countries mentioned above but instead of that the most important ones where between first world countries and third world countries.
The most important edge in our network was the one between Switzerland and Mali.

Since switzerland seems to be an important player in this network the following map  shows the connections of the entities based in switzerland and other world countries:

{% include edges.html %}



The result is not surprising again since the paper revealed that 1,339 Swiss lawyers, financial advisors and other middlemen had set up more than 38,000 offshore entities over the past 40 years.

As a consequence the inter-governmental Financial Action Task Force (FATF) called on the Swiss to do more to thwart financial crime. However, the  EU also has been pushing a new Anti-Tax Avoidance Package. It is now introducing a new rule that requires the largest companies operating in the EU to disclose key information on where they make their profits and where they pay their tax in the EU on a country-by-country basis.

In order to get a more intuitions about the graph connections and relation we decided that we will create a weighted graph from countries where each link represent the number entities linked to countries:

<iframe src="https://labs.graphistry.com/graph/graph.html?dataset=PyGraphistry%2FEP7QQDISPK&type=vgraph&viztoken=10196f5402e3593bbe47976aab86ae4ef3c1fe08&usertag=fe496517-pygraphistry-0.9.56&info=true&play=0&workbook=459c7901a6f4abbc&fbclid=IwAR0U2eL5epXXPR-x1GrRwBoKCOE7z3W7NooY305tVUseviBkWmEJ5_OiFEw" width="100%" height="400px"></iframe>

To make our graph be interactive and highly sophisticated we decided to use  Graphistry. This library enables visual investigation of the graph, by putting the mouse on the node or the edge we will see all there attributes.

It also allow us to extract a lot of mathematical relations such as histograms (degree of nodes, edges in, edges out ...).

This graph represents the weighted projection of the bipartite graph, here we take into account the number of commun associations between countries as weights. It is clear that again some countries dominates the graph such as Switzerland, Hong Kong, Singapore ..


---

### <span style="color:red"> Financial Secrecy Index (FSI) and involved jurisdictions </span>

Our analysis has not stopped in just analyzing the involved countries and the connection between them. We instead wanted to find any correlation between the implication of each country in the panama papers with official indexes published by world wide organizations. We studied the correlation between Financial Secrecy Index (FSI) and countries involved in Panama papers.

<iframe src="fsi.html" width="100%" height="400px"></iframe>

The Financial Secrecy Index (FSI) ranks jurisdictions according to their secrecy and the scale of their offshore financial activities. It is a tool for understanding global financial secrecy, tax havens or secrecy jurisdictions, and illicit financial flows or capital flight.

We studied the correlation between the ranking of countries according to the financial secrecy and the ranking of involved countries in Panama papers. The results were relevant: we found correlations between 0.6 and 0.7. That means that the countries having a good ranking regarding Financial Secrecy Index (FSI) attract more offshore entities, which can be explained :

A company or private individual may create an offshore in countries where, preferably, regulations are weak, for example, no need to name the owner. These companies are usually limited liability companies and don’t conduct any business, they just own financial assets of their owner. In fact, this is the main point of Panama papers involved officers. Those countries are basically offshore center that provides financial services to nonresidents on a scale that is incommensurate with the size and the financing of its domestic economy. Secrecy jurisdictions use secrecy to attract illicit and illegitimate or abusive financial flows.




### <span style="color:red"> Conclusion </span>
Corruption and inequality feed off each other, creating a vicious circle between corruption, unequal distribution of power in society, and unequal distribution of wealth. As the Panama Papers showed, it is still far too easy for the rich and powerful to exploit the opaqueness of the global financial system to enrich themselves at the expense of the public good.


---

### <span style="color:red"> Full project </span>

The full project is available on a [github repository](https://github.com/mouadhhamdi/ADA-Project). It provides 2 Jupyter Notebook. A first one for cleaning the data from the different datasets downloaded from [The International Consortium of Investigative Journalists](https://offshoreleaks.icij.org/pages/database).The second one is the main project where we analysed the data, did the network analysis and studied the correlations. If you want more information about our project, please contact us via email (you can find them in About section)
