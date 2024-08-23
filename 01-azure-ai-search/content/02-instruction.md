Microsoft describes Azure AI Search as designed to scale to any workload involving retrieval augmented generation. With it, you can create a **vector database**, prepared from enterprise data, knowing that your information is secure, compliant with regulators, and built around responsible AI practices.

> NOTE: If you're working with outdated information sources, Azure AI Search was previously called 'Azure Cognitive Search'. 

Azure AI Search provides access to uploaded data - as well as generative AI search - in a way that isn't limited by how many users can use your application. 

Searching for information is the basis of all applications that provide text output or vectorized information. Typically, apps are built to look through **unstructured documents**, like spreadsheets and PDFs, or **structured data**, like you'd find in a well-normalized SQL databse.

With the advent of large language models (LLMs), the technique of **retrieval augmented generation** centers around providing information from traditional data sources to create effective prompts, providing a foundation for conversational interaction.

[TODO FPE: Maybe the term 'search service' needs introducing before the points below? It isn't super clear to me!]
Creating a search service can involve working with:
- Vector searches.
- Searches that match full text.
- Hybrid approaches. 

Search service creation can also involve indexing data with **vectorization** and **chunking**, as well as **text analysis** to break human language into its basic buidling blocks (such as nouns and verbs). 

There is also support for autocomplete, search based on spatial information, as well as options for fuzzy searches and complex options for specifying the parameters of search for text, vector, and hybrid models. 

An Azure serch service exists as an **intermediate layer** between un-indexed raw information in your organization and an app you build to take user inputs and provide useful output via an index. You build your search app based on APIs that work with all kinds of techniques for data analysis, including matching patterns, sorting, tuning results for relevance, and ranking of results based on inferred meaning rather than verbatim matches.

[TODO FPE: Maybe another heading somewhere around here to break up the text?]
Another great benefit of Azure AI Search is that it can interconnect with other services using **indexers** and **skillsets**. An indexer helps you ingest information from Azure data sources. Skillsets are things that are AI-based, like searches based on images, or custom creations from Azure Machine Learning.

Inside the search service, the main purpose is to provide indexing and querying capabilites:

**Indexing** is a process by which you provide content for your service and make it easily searchable. Text input is broken down into **inverted indexes** - where information is organized numerically, based on word location within the data instead of 'which data contains what words'. This means the search system can find all the places where a word is located without having to search every line of text in the system. 

Vectors can also be provided as input, and are stored in an efficient, easily-machine-searchable format. Azure can index information uploaded in JSON format. It can also use an indexer to convert your data into that format. 

Indexing can be extended to images, using techniques like **optical character recognition** or **image descriptions**. As for large documents containing entirely human-readable information, those can be translated between languages, or have information extracted about its organization.

**Querying** does the opposite - it gets useful information out of your data. Once an index has searchable information added to it, your app can take questions from your users and provide responses. If you use semantic ranking, you can use the underlying meaning of initial search results to determine the most useful information to provide back to users.

Azure AI Search is useful for **searching raw text**, as well as generating **vector similarity results**, providing a balanced set of capabilities for optimal search effectiveness. It's also good at combining different types of information into a search system based on structured text and vectors. All this is possible while maintaining strict control over how your organization's information is used.

# Comparison to LangChain
TODO: NOT READY BEFORE LANGCHAIN LESSONS COMPLETED

The basic steps of setting up a search index are creating it, loading it with data, and then searching it. 

To create a search, you'll be using the **Python API**, providing a way to organize the information you want to search. Then, you'll move your data into Azure by uploading JSON (alternatively, you can have Azure download your information from many Microsoft data storage solutions). Finally, you'll perform searches against your service (again, in Python for this example).

Setting up a basic data index is pretty simple. After making sure you have the dependencies for Azure installed, and endpoints determined, you need to create an `AzureKeyCredential` from your search api key. Then, you need to make sure you're importing the correct items from the Azure dependencies installed with pip for the rest of the script to work.

Next, it's time to create the `SearchIndexClient`, based on the endpoint and the `AzureKeyCredential` created. Fields for the index are set up after this, comprised of name-type pairs describing the fields your information will be organized into, and the types of information represented.

The next step is creating a `SearchIndex` from a name, the fields prepared in the prior step, a suggestor (built with a name and some source fields), and an array of scoring progfiles (which empty for this example). After the SearchIndex is created, it is created on the server side.

For this demo, the next stage is to build an array of JSON objects containing the data organized into the fields you set out in the `SearchIndexClient`. This is uploaded to a `SearchClient` (comprised of the endpoint for search, the name of the index, and the `AzureKeyCredential`).

To run an empty search, you can provide a Kleene star for matching "any" search text with the simple query type and fields to show in the results. This should show all the documents in the index.

To run a search with a keyword, set `search_text` to your word, and perform the search again.

This isn't too impressive, but it shows you the very basics to get started! 
