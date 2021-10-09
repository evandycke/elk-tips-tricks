# Kibana best practices

## What Is Kibana ?

Kibana is a free, open-source analytics, monitoring, and visualization platform that was created in 2013 by Elastic. It offers a variety of features, that makes it a noteworthy competitor to other visualization tools, such as :
* Graphics Analytics
* Machine Learning
* Anomaly Detection
* Log Categorization
* Log Monitoring
* Flexible Data Visualization
* Data Exploration 
* Cloud Integration

Kibana's intuitive and straightforward user interface consists of 4 sections : 
1. Discover
2. Visualize
3. Dashboard
4. Settings

Having most features on display makes it one of the easiest tools to use and master, even for complete beginners.

## The Best Practices for Using Kibana for Data Visualization

Just because you have access to a specialized tool, doesn't mean your resulting graphics are going to be great without putting in the work. There are a few factors you need to take into consideration and practices to follow in order to create note-worthy visuals.

### Know Your Audience

Before you even start planning your graphics, you need to determine your audience. Your reporting dashboards are going to contain very different information depending on if your viewer is a systems administrator, a key company stakeholder or a business analyst. 

Take into account how knowledgeable your audience is on the topic you're sharing, along with their age group and attention span. This will help you determine the complexity of the data displayed and which key information to focus on. 

### Understanding your data
 
Visualizations are built upon the fields constructing your logs. So understanding these fields and the data they represent, is key to visualizing the data correctly.  

If you have configured parsing yourself, you should have a good idea on how your logs are structured. In other cases however, parsing is done automatically by Elasticsearch. In this case, the resulting list of fields is virtually unknown. 

Start with selecting fields from the list of available fields on the left. You will see the top five values for the field. Some field names are self-explanatory (e.g. 'bytes', 'clientip'), but others (e.g. 'name', 'auth') require some additional investigation.  

Add these enigmatic fields to the main log display area. Use Kibana queries to search through the logs. These actions will provide you with the context you need for the next steps.

### Aggregate the Data

It's impossible to represent massive amounts of data in a single graph. Instead, you need to profile and section it into categories that work well together. Kibana offers two types of data aggregation :
* Bucketing 
* Metrics

#### Data bucketing 

Data bucketing — also known as binning — is the process of sectioning-off sets of data that meet specific criteria defined by the user. It helps reduce minor observation errors and anomalies without distorting the data's integrity. 

#### Metrics

Metrics, as the name suggests, keep track of your system or infrastructure's metrics in real-time. When visualizing metric data, it helps with troubleshooting system problems.

### Defining what you want to visualize
 
Now that you know what data your logs are actually recording, you can begin to strategize your visualizations.  

First, define your goal by asking a simple question — what are you trying to analyze or monitor ? The answer to this question will determine how you visualize the data. Do you want to see a historical trend over time for a specific field? Do you want to see a breakdown of the top ten values for a specific field? If you are monitoring traffic to your website, do you want to see a geographical depiction of where the originating request is coming from ? And so forth.  

The answer to this question helps you with two decisions needed for the next step: 
1. Deciding what type of Kibana visualization to use (the Visualize page in Kibana provides you with a general description of each visualization)
2. Deciding which fields to use for the visualization. If you are shipping multiple types of logs, which is often the case, the answer helps you focus on the required log type as well. 

### Choose the Right Visuals

Choosing the right graphics depends largely on the type of data in question. Different charts focus on different elements and results, making this decision tie back to knowing your audience and what information you want to be at the centre of attention. 

For example, to showcase the composition of a data set, use pie charts and stacked charts. Trends work best with line graphs, while bubble charts compare two or more sets of data. Of course, different charts can be used on the same sets of data to highlight different findings.

### Avoid Ambiguity

Ambiguous graphs can be misleading, whether intentionally or not. To avoid that, make sure you use clear language and label your graphs when in doubt. Deceptive graphs are rarely wrong, but they take advantage of people's lack of attention to distort findings.

Some examples of misleading graphs include :
* Changing the baseline of the vertical axis to anything other than zero
* Manipulating the Y-axis to exaggerate or undermine findings
* Using the wrong figure — using pie charts to compare separate data sets
* Flipping the norm — switching dark and light colours for density, and left and right for positive and negative values

### Focusing on logs and using saved searches
 
You know what you want to visualize, and you know what log type and corresponding fields you most likely need to use. What next ? 

A recommended way to proceed is to use the Discover page in Kibana to search for the data you’re interested in and then saving your search. Once saved, this search will provide you with a starting point for single or multiple visualizations for building a dashboard. If you decide you want to analyze a different set of data, changing the saved search will change all the linked visualizations accordingly instead of having to change all of them individually.  

Saved searches can also be inserted into dashboards, allowing you to embed the Discover tab within a dashboard, giving you good visibility into relevant logs.

### Starting, and keeping it, simple
 
You don’t have to start with a fancy visualization containing multiple sub aggregations. Start simple and expand from there.  

If it’s a pie chart visualization for example, use the basic default settings to see a breakdown of the top five results for a specific field.

Preview the results, save the visualization and continue developing it by exploring the different configuration options.  

Try and avoid overcomplicating your visualizations. The desire to see it all in one place is understandable, but it makes no sense to crowd up a perfectly constructed visualization with a sub aggregation of an irrelevant field. 

### Customizing your visualizations (carefully)
 
Almost all visualization types feature an Option tab, under which appears a series of additional customization options depending on the visualization type. These options allow you to play around with the way the visualization is displayed and can be very useful in making your chart or graph more readable.  

Be careful though, and if it ain’t broken, don’t fix it. You may find your visualization transforming from a clear graphical depiction of the data you’re analyzing into an indiscernible mess.   

### The Art of Dashboarding
 
Once you’ve got your ducks – or visualizations – set in a row, it’s time to think of combing all your visualizations into a comprehensive dashboard. In practical terms, nothing could be simpler, but similar to visualizations, some thought needs to be given before you begin piling up all the individual visualizations.  

The main factor determining what your dashboard will look like is its purpose or goal. A system monitoring dashboard will look entirely different compared to a dashboard built ad-hoc to troubleshoot an issue in production.  

This factor also affects the number of datasources used for the dashboard. Multiple data sources are effective in getting a general overview of a system, but not useful for drilling down (drilling down, or selecting a field, in a visualization built on a specific datasource will render any visualization built on top of a different datasource useless).

The same best practices outlined above for visualizations apply for dashboards. Keep it as simple as possible, and don’t overcrowd a dashboard. Not every visualization you’ve built in the history of time needs to be included in the same dashboard. If possible, I usually try and avoid the need to scroll up and down in a dashboard. 
