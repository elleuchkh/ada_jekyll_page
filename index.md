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

The Panama Papers involved hundred thousands of offshore accounts, millions of documents detailing top secret financial information were leaked in 2015 by an anonymous source. It is estimated that tax havens cost poor countries at least $170 billion in lost tax revenues each year making poorest people lose out and the inequality gap grow. Holding money in an offshore company is generally not illegal but it can be used to launder money, dodge sanctions, avoid taxes. Many people listed in the panama papers claimed being innocent.


##### <span style="color:green"> Some relevant numbers related to Panama papers </span>

- 11.5 millions leaked documents that detail financial and attorney–client informations
- More than 214,488 offshore entitie involved.
- Some 4.8 millions leaked files were emails, 3 millions were database entries, 2.2 millions PDFs, 1.2 millions images, 320,000 text files, and 2242 files in other formats.
- 2.6 terabyte trove of data at the core of this investigation contains nearly 40 years of records.



##### <span style="color:green"> A word about the dataset before starting </span>

Unfortunately, we don't have access to big part of the data and metadata from the original leaks. So, we decided to enrich our data with other similar datasets found in ICIJ (The International Consortium of Investigative Journalists):Paradise papers, Offshore leaks and Bahamas leaks.

We combined all the datasets together to get more information, and then structured them in 3 relevant datasets. Each one represents a specified role of involved parties:


- **<span style="color:blue"> Entities: </span>** is a company, trust or fund created in a low tax offshore jurisdiction.
- **<span style="color:blue"> Officers: </span>** a person or a company who plays role in an offshore entity.
- **<span style="color:blue"> Intermediairies: </span>** the link between someone seeking an offshore and an offshore service provider.

An other important dataset was used in our analysis which is :

-  **Edges:** they connect nodes from the above parts and describe the nature of the relation between them.
This dataset was very important especially in network analysis.  



---

### <span style="color:red"> Outline of the project </span>

There is a huge amount of data, our work will be to provide a detailed analysis of the dataset. We will not focus our analysis on individuals but we will instead be getting a closer view about the involved countries and the distribution of the papers around the world. We will try to find any correlation between the implication of each country in the panama papers with other finacial studies such as Financial secrecy index, Corruption ... and with any other interesting information we could get about those countries.

##### <span style="color:green"> Research questions </span>

- What is the distribution of officers, entities and intermediaries around the world? It is based in specified countries or it is overspreaded? <br>  
- Can we relate our rankings to other world known indicators? <br>  
- What is the effect of suspecious investments on some countries? (Espcially top Tax havens) <br>  
- Does Mossack Fonseca have connections with entities (intermediary companies, clients, beneficiaries and shareholders) based in countries <br>  
- Which had a high degree of illicit outflows? <br>  


We strongly believe in the usefulness of this kind of project in order to get a better understanding of the worldwide organization of the tax evasion phenomenon. We think that it could help society realize the importance of the event. It could therefore push towards the implementation of new tax regulations to prevent such aberrance.


###  <span style="color:red"> Involved countries </span>
The map show the worldwide distribution of the three main kinds of actors : which are Offshore entities, intermediaries and officers. We notice that the three of them differ from each other on a global scale even though some countries are represented in all three categories.

#### <span style="color:green"> Entities </span>

{% include entities.html %}

Regarding the offshore entities, the presence of economic global powers is clear : US and Russia. But they are other efficient hosting countries. Indeed, in Europe, Switzerland and Malta are leading with a very huge number comparing the other countries followed by Great Britain and Luxembourg. In South America, Panama has a large capital of offshore entities. In western Asia, United Arab Emirates is also leading. It is noticeable that a lot of top countries involved belongs to offshore financial centers according to FMI, which is very logic. Companies look for low tax offshore jurisdiction to maximize their benefits.

#### <span style="color:green"> Intermediaries </span>

{% include intermediaries.html %}

To fulfill a tax evasion, the offshore companies also need a go-between with a service provider, these intermediaries usually are law-firms, banks or middlemen that asks an offshore service provider to create an offshore firm for a client. The Intermediaries are once again most located in Switzerland and Great Britain, as they are known for the privacy of their bank services. Still, the distribution of the intermediaries is very similar to the offshore entities distribution on a global scale. The intermediaries involve mainly in the phases of the identified decision-making cycle (advice, creation, maintenance, enforcement).

**<span style="color:blue"> Active intermediaries </span>**

{% include active.html %}

Mossack Fonseca worked with intermediaries in more than 100 countries all over the globe. Their most active clients by number of offshore company incorporations were from Hong Kong, Switzerland and the United Kingdom.

#### <span style="color:green"> Officers </span>

{% include officers.html %}

Regarding the officers, It is noticeable to say that most countries involved in entities are present here, which is very logic. But, other countries appeared here, especially Germany, Italy and Russia. It means that officers may have a relationship with companies in those countries. We will explain that in the next part.

To conclude, countries involved in Panama papers are around the word. The offshore entities are not related to Panama or American and Europeen countries. Companies, busniessmans, football players and even politicians all around the world had an issue with Panama papers.




---


### Network

<iframe src="https://labs.graphistry.com/graph/graph.html?dataset=PyGraphistry%2FEP7QQDISPK&type=vgraph&viztoken=10196f5402e3593bbe47976aab86ae4ef3c1fe08&usertag=fe496517-pygraphistry-0.9.56&info=true&play=0&workbook=459c7901a6f4abbc&fbclid=IwAR0U2eL5epXXPR-x1GrRwBoKCOE7z3W7NooY305tVUseviBkWmEJ5_OiFEw" width="100%" height="400px"></iframe>



---

### World wide indexes and involved jurisdictions:

Our analysis has not stopped in just analyzing the involved countries. We instead wanted to get a closer view about them to find any correlation between the implication of each country in the panama papers with official indexes published by world wide organizations
(that we thought they could be helpful for our analysis).

#### Financial Secrecy Index (FSI)

The Financial Secrecy Index (FSI) ranks jurisdictions according to their secrecy and the scale of their offshore financial activities. It is a tool for understanding global financial secrecy, tax havens or secrecy jurisdictions, and illicit financial flows or capital flight.


We studied the correlation between the ranking of countries according to the financial secrecy and the ranking of involved countries in Panama papers. The results were relevant: we found correlations between 0.6 and 0.7. That means that the countries having a good ranking regarding Financial Secrecy Index (FSI) attract more offshore entities, which can be explained :

A company or private individual may create an offshore in countries where, preferably, regulations are weak, for example, no need to name the owner. These companies are usually limited liability companies and don’t conduct any business, they just own financial assets of their owner. In fact, this is the main point of Panama papers involved officers. Those countries are basically offshore center that provides financial services to nonresidents on a scale that is incommensurate with the size and the financing of its domestic economy. Secrecy jurisdictions use secrecy to attract illicit and illegitimate or abusive financial flows.


#### World Happiness Index



#### A brief word about corruption
Corruption and inequality feed off each other, creating a vicious circle between corruption, unequal distribution of power in society, and unequal distribution of wealth. As the Panama Papers showed, it is still far too easy for the rich and powerful to exploit the opaqueness of the global financial system to enrich themselves at the expense of the public good.



---


### Full Project

The full project is available on a [github repository](https://github.com/mouadhhamdi/ADA-Project). It provides 2 Jupyter Notebook. A first one for cleaning the data from the different datasets downloaded from [The International Consortium of Investigative Journalists](https://offshoreleaks.icij.org/pages/database).The second one is the main project where we analysed the data, did the network analysis and studied the correlations. If you want more information about our project, please contact us via e-mail (you can find the in About section)
