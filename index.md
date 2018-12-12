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

### Introduction to the Panama Papers

The Panama Papers involved hundred thousands of offshore accounts, millions of documents detailing top secret financial information were leaked in 2015 by an anonymous source. It is estimated that tax havens cost poor countries at least $170 billion in lost tax revenues each year making poorest people lose out and the inequality gap grow. Holding money in an offshore company is generally not illegal but it can be used to launder money, dodge sanctions, avoid taxes. Many people listed in the panama papers claimed being innocent.



##### Some relevant numbers related to Panama papers

- 11.5 millions leaked documents that detail financial and attorney–client informations
- More than 214,488 offshore entitie involved.
- Some 4.8 millions leaked files were emails, 3 millions were database entries, 2.2 millions PDFs, 1.2 millions images, 320,000 text files, and 2242 files in other formats.
- 2.6 terabyte trove of data at the core of this investigation contains nearly 40 years of records.



##### A word about the dataset before starting

Unfortunately, we don't have access to big part of the data and metadata from the original leaks. So, we decided to enrich our data with other similar datasets found in ICIJ (The International Consortium of Investigative Journalists):Paradise papers, Offshore leaks and Bahamas leaks.

We combined all the datasets together to get more information, and then structured them in 3 relevant datasets. Each one represents a specified role of involved parties:

* **Entities:** is a company, trust or fund created in a low tax offshore jurisdiction.
* **Officers:** a person or a company who plays role in an offshore entity.
* **Intermediairies:** the link between someone seeking an offshore and an offshore service provider.

An other important dataset was used in our analysis which is :

-  **Edges:** they connect nodes from the above parts and describe the nature of the relation between them.
This dataset was very important especially in network analysis.  



---

### Outline of the project

There is a huge amount of data, our work will be to provide a detailed analysis of the dataset. We will not focus our analysis on individuals but we will instead be getting a closer view about the involved countries and the distribution of the papers around the world. We will try to find any correlation between the implication of each country in the panama papers with other finacial studies such as Financial secrecy index, Corruption ... and with any other interesting information we could get about those countries.

##### Research questions  
- What is the distribution of officers, entities and intermediaries around the world? It is based in specified countries or it is overspreaded? <br>  
- Can we relate our rankings to other world known indicators? <br>  
- What is the effect of suspecious investments on some countries? (Espcially top Tax havens) <br>  
- Does Mossack Fonseca have connections with entities (intermediary companies, clients, beneficiaries and shareholders) based in countries <br>  
- Which had a high degree of illicit outflows? <br>  


We strongly believe in the usefulness of this kind of project in order to get a better understanding of the worldwide organization of the tax evasion phenomenon. We think that it could help society realize the importance of the event. It could therefore push towards the implementation of new tax regulations to prevent such aberrance.


##### In quest of interactivity

One of the main guidelines for this project was to make it as interactive as possible. It comes from the idea that for a program to have the greatest impact as possible on the general public it needs to show at least as possible of code and it needs to be as intuitive as possible. That is why we are implementing as much effort as possible to release a web app that could be available to everyone. The web app development is discussed at the end of this website where we address the possible future directions to be undertaken. As a matter of transition some `jupyter notebook` scipts have been implemented which roughly show the kind of features that are intended to be implemented in the web app. The `jupyter notebook` scripts are available on the [github repository of the project](https://github.com/mouadhhamdi/ADA-Project).













----

### Tax Evasion

From our analysis it becomes very clear they are few countries able to attract, keep and hide large amount of money from foreign tax authorities. It is clear the main incentive to create offshore accounts/companies is the savings on taxes allowed by a lack of economic policies in those countries.     
The pattern to tax evasion becomes almost simple when spotlighted. A company or private individual may create a "Shell company" in the country of his choice, preferably where regulations are weak, for example, no need to name the owner. These shell companies, also called Offshore Entities, are usually limited liability companies and don't conduct any business, they just own financial assets of their owner. To fullfill a tax evasion, they also need a go-between with a service provider, these intermadiaries usually are law-firms, banks or middlemen that asks an offshore service provider to create an offshore firm for a client. Finally, bearers are the entities receiving shares from an offshore company, unfortunately bearer shares provide one of the deepest levels of secrecy.  

{% include Trump.html %}  




Nomenclature:  
- **Offshore Entity** : A company, trust or fund created in a low-tax, offshore jurisdiction by an agent.   
- **Officer** : A person or company who plays a role in an offshore entity.   
- **Intermediary**: A go-between for someone seeking an offshore corporation and an offshore service provider -- usually a law-firm or a middleman that asks an offshore service provider to create an offshore firm for a client.  


<br>   
<br>   

---

### Involved countries

The map above shows the worldwide distribution of the three main kinds of actors : which are Offshore entities, Intermediaries and Officers. We notice those three differ from each other on a global scale even though some countries are well represented in all three cathegories.
Regarding the offshore entities, we must notice the presence of the three economic global powers : USA, China and Russia. But they are, by far, not the more effcicient hosting countries. Indeed, in Europe, Switzerland is leading with more than 37 thousands hosted entities (10 times more than Russia), followed by Luxembourg and Great Britain. In South America, Panama has a large capital of offshore entities. In western Asia, United Arab Emirates is also leading.
The Intermediaries are once again most located in Switzerland and Great Britain, as they are known for the privacy of their bank services. Still, the distribution of the intermediaries is very similar to the offsore entities distribution on a global scale.
Finally, we notice the southern countries are more involved in the officer distribution. Usually officiers are settled in different juridiction than the company/private individual at the origin of the tax evasion.

<iframe src="https://github.com/elleuchkh/elleuchkh.github.io/blob/master/_includes/plot.html" width="100%" height="400px"></iframe>




### Network

<iframe src="https://labs.graphistry.com/graph/graph.html?dataset=PyGraphistry%2FEP7QQDISPK&type=vgraph&viztoken=10196f5402e3593bbe47976aab86ae4ef3c1fe08&usertag=fe496517-pygraphistry-0.9.56&info=true&play=0&workbook=459c7901a6f4abbc&fbclid=IwAR0U2eL5epXXPR-x1GrRwBoKCOE7z3W7NooY305tVUseviBkWmEJ5_OiFEw" width="100%" height="400px"></iframe>
#### Density maps

The tools that we developed in the frame of this project are able to show density maps representing the level of off-shore activities per country. The level of off-shore activity is actually simply measured by the number of financial actors per country repertoriated in the database. This tool has the ability to scale so that the user can be able to see some part of the world more in details. It can be very useful in the context of off-shore analysis because the most important actors are often established in small tax heavens.




#### Connection queries

We also provide a tool that let the user request a particular individual of the dataset. He/she can do so by querying its name and by applying filters concerning its nationality or its role in the financial system. When querying such an individual the database retrieves all its relationships. Then a graph is generated whose nodes are the items of the database that are directly conncted to the queried individual. Moreover the edges of the graph are used to label the relationship between two vertices of the graph. Then this graph is put in context in a map which gives much more sense to it. You can play with this tool running the `connection_query.ipynb` or the `main_pipeline.ipynb` files on our [github](https://github.com/adrienruault/ada_molmaru/tree/master/project).



#### Country connections

Another too that is available with our app is a feature that allows to choose a country and to query the countries that are the most closely related to the latter in terms of off-shore financial activities. It is a quite useful tool that allows to better understand the relationships between the countries.




From the raw dataset, we were able to designe a tool to query for types, names and locations
The provided dataset allow us to investigate for specific relationships  

![screenshot_webapp](img/France.png){:class="img-responsive"}

---


### Web App

As the aim of the project was to be able to share an intuitive web application for processing simple geographical queries on the Panama Papers dataset, we focused a lot our work on the exportation of the widget obtained after milestone 2. After some research, we understood that folium was not really suitted tp share the widget out of the jupyter notebook context. It also appeared that exporting the ipywidgets we used was pretty complicated. We finally found the library "Bokeh", which seemed to propose more solutions for the exportation of our app. We thus recoded our widgets on the basis of Bokeh maps, which were found to be a bit more complicated to use, but also provided new interesting fuctionalities. After the refactoring of the code, we tried to give a public access to our app, following the instructions of a [google tutorial](https://cloud.google.com/solutions/bokeh-and-bigquery-dashboards). This tutorial proposed to use a google cloud computing machine to host the Bokeh sever of the web app, in combination with docker to provide well suited containers. Unfortunately, it appeared that we did not have the required knowledge to achieve this task: we still get some issues with the Bokeh server that is not able to find or launch our python code. We are a bit disappointed because we wanted the web app to be ready for this deadline. However, we are still going to try releasing it for the presentation of january, as it was important for us to make this app shareable, and also because that we think we are not far from our goal. For the moment, the Bokeh application is avalaible on github and can be run on a machine with Bokeh installed (can be installed with pip). To run it, you can just go in the /project folder of our [ADA github repository](https://github.com/adrienruault/ada_molmaru.git), and run the command "bokeh serve --show ." (do not forget to download the data and to run the preprocessing as described in the README). Here is an overview of the generated app (run in localhost :'( ):  

![screenshot_webapp](img/webapp.png){:class="img-responsive"}


### Full Project

The full project is available on a [github repository](https://github.com/adrienruault/ada_molmaru/tree/master/project). It provides a Jupyter Notebook processing the data from the Panama Papers & Paradise Paper with a performant query tool to geographically display portions of actors involved in cash criminality. This tool was not implemented in this html page due to a lack of time and compliance between python's libraries and html.   
The datasets was downloaded from [The International Consortium of Investigative Journalists](https://offshoreleaks.icij.org/pages/database) website.
