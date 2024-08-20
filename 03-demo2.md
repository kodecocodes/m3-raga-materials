 The first block of code you'll see are the package installation instructions. These use pip, they python package manager. The --quiet flag suppresses output, which is convenient in a Jupyter. If you want, you can run these commands in a terminal window without --quiet to see what goes on when a package is installed.

 The next segment sets the API keys. Normally you want to keep these hidden in a config file or environment variable, but that is beyond the scope of this lesson.

 Then, we create a search schema.

 Next, we create the search index.

 In the following section, we assign some sample data (I generated it with ChatGPT) about television shows.

 Then, you can see the creation of the search client, and upload of the documents.

 Next, run an empty query to see all the documents in the index.

 The exciting part of this lesson is here! This shows how to perform a term query.

 The last bit cleans up your created index. Make sure to shut down the services you created on Azure after you're done playing around. You dont incur any unexpected cloud fees!