[//]: # (title: Documentation Page)

If your plugin needs not only a marketing or features overview page, but user-facing documentation, 
a **Documentation** page is coming into play.

Unlike [Custom pages](custom-pages.md), the **Documentation** page is specifically designed to host documentation artifacts on a separate tab. 
This is not a single page but a full-fledged help instance with its structure, navigation, and even a search area. 
Similar to the one you're reading right now. 

You can use not only a common Markdown but a variety of semantic markup elements and attributes tailored specifically to create documentation, 
like:

* tabs
* complex tables
* videos
* collapsible blocks
* sophisticated code snippets
* notes, tips, and warnings.

Under the hood, the ability to author and publish documentation is supported by the [Writerside plugin]() for IntelliJ IDEs.

What you need is:
* create a documentation folder alongside your plugins' code or a separate docs repository;
* write the actual content with the help of templates, live preview and assistance; 
* commit and push the result;
* promote a **Run configuration** to publish your content.