coreNlp_stopwords
=================

**This is a fork from the original 'coreNlp' project, developed by jconwell at [https://github.com/jconwell/coreNlp](https://github.com/jconwell/coreNlp).**

I have updated and tweaked this project to be a stopword-removal add-on to coreNlp v3.7.0. Feel free to use it if you like it.

Some considerations:

* As this is a personal project, I will not dedicate too much time to fix any references to jconwell or the original project. If you stumble into any of these, and it bothers you, please open an issue and report it.

* This project is a "quickie": probably, some things will be broken (I am almost sure the tests are). Please be patient.


Identifying Stopwords in CoreNlp
--------------------------------

CoreNlp doesn't have stopword identification built in, so I wrote an extension to its analytics pipeline (called Annotators) to check if a token's word and lemma value are stopwords.

By default, the StopwordAnnotator uses the built in Lucene stopword list, but you have to option to pass in a custom list of stopwords for it to use instead.  You can also specify if the StopwordAnnotator should check the lemma of the token against the stopword list or not.

For examples of how to use the StopwordAnnotator, take a look at StopwordAnnotatorTest.java 

Friendly API for building a new StanfordCoreNLP instance
--------------------------------------------------------

There is also a friendly api for configuring the analyzers you want to use when you create a new StanfordCoreNLP instance.  This beats building up a properly formatted string (in the correct order) of the list of analyzers CoreNlp will load.  There are also a set of static factory functions built around many common combinations of options.

Again, check out the unit tests for examples on how to use them.

NOTE: the unit tests actually create an instance of StanfordCoreNLP, so if you want to build the jar with maven you'll need to configure maven to have a larger heap size as several models require a fair bit of memory
