# Eclipse plugin for Hibernate Search

This is the repository of Hibernate Search plugin for Eclipse. It is in development as a part of Google Summer of Code. Some more info can be found in the blog: http://bdshadow.blogspot.ru/. This repository must be taken in account together with my fork of Hibernate Tools: https://github.com/bdshadow/jbosstools-hibernate, where I add extension points to pkug my HSearch tools in.

# The plan
* **Mechanism of adding configuration (hibernate.properties or hibernate.cfg.xml) via gui by extending similar mechanism of Hibernate Tools.**
If we speak about extending existing Hibernate Tools, I suppose it to look like this:
https://drive.google.com/open?id=0B6NhNcM1nZzneG00TUZjQVFlME0&authuser=0
Later it would be great to extend it for Inifispan - different config files + no Hibernate ORM. So I expect it to detect what is in use and make a similar gui for Infinispan
* **Rebuilding the whole index mechanism (+ ability to parameterize MassIndexer)**
I mean extend ConfigurationsViewActionGroup and add a new action to the console like this: https://drive.google.com/file/d/0B6NhNcM1nZznNzNuNlVzZXM1RjQ/view?usp=sharing, which would open a new window with MassIndexer parameter options: a dropdown list with Indexers (if hibernate.search.massindexer.factoryclass is set, then use it as default chosen), field with number of threads, batch size, etc...
* **A tool similar to Luke to "see" what is in the index, and with which documents it has been indexed**
It is one more action in ConfigurationsViewActionGroup. The detailed interface should be defined more precisely and be prioritized, but I think will look similar to Luke's Overview (https://drive.google.com/file/d/0B6NhNcM1nZznMERDaHlHVC12SFk/view?usp=sharing) and Documents (https://drive.google.com/file/d/0B6NhNcM1nZznMUdYb2E5OVNZX1U/view?usp=sharing) tabs.
* **A tool which has a dropdownlist of the "Analyzers" defined in the Search application, and an input text. One could paste some text in the input box, and you would show how that gets split up in different text tokens**
I think of it as also one more action in ConfigurationsViewActionGroup . It must open a new Editor. The interface will be very similar to HQL Editor. But the dropdown list will show Analyzers. Then you put some text into the editor, Run the chosen analyzer and get a result in a separate view.
* A tool which combines the two above a bit: it shows which Analyzer is used for the field by default - but also allow to override it by picking an option from the list - and then highlight which documents from those in the index have matching.


