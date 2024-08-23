The first block of code you'll see are the package installation instructions. These use 'pip', the Python package manager. 

The --quiet flag suppresses output, which is convenient in a Jupyter. If you want, you can run these commands in a terminal window without --quiet to see what goes on when a package is installed.
[TODO FPE: I'm not sure if ' --quiet ' is okay formatted like this in the text, or if it should be shown as inline code/other]

The next segment sets the API keys. Normally, you want to keep these hidden in a `config` file or environment variable, but that's a little beyond the scope of this lesson.

Then, you'll create a search schema.

After the search schema is created, you'll create the search index.

In the following section, you'll assign some sample data about television shows (this example is generated with ChatGPT).

Then, you can see the creation of the search client and upload of the documents.

Next, run an empty query to see all the documents in the index.

The exciting part of this lesson is here! How to perform a term query:

The last bit cleans up your created index. Make sure to shut down the services you created on Azure after you're done playing around, so that you dont incur any unexpected cloud fees!
