[//]: # (title: Documentation Page)

If your plugin needs not only a marketing or features overview page but user-facing documentation, 
a **Documentation** page is coming into play.

Unlike [Custom pages](custom-pages.md), the **Documentation** page is specifically designed to host documentation artifacts 
in a separate tab. 

This is not a single page but a full-fledged help instance with a structure, a table of contents, and in-topic navigation. 
Similar to the one you're reading right now. 
You can check some more examples here: [Grazie Professional](https://plugins.jetbrains.com/plugin/16136-grazie-professional/docs), [Rust](https://plugins.jetbrains.com/plugin/8182-rust/docs), and [Edu Tools](https://plugins.jetbrains.com/plugin/10081-edutools/docs).


If you are asking yourself why you should bother about writing documentation for your plugin, here are a few tips:
* Documentation makes your solution discoverable and searchable. When product documentation is online, 
external search engines will bring it to everyone who types the keywords into the search query.
* Documentation helps you to stand out and communicate features of a plugin better so that your customers get the most out of it.
It makes your product look more professional and reliable and helps build trust in it.
* Documentation is a way to support your current users. If they get answers to their questions on the Documentation tab, they won't write bad reviews to get support, 
and it will also decrease the support load, which is crucial for a small company where everyone supports customers.

You can use not only common Markdown elements but a variety of semantic markup elements and attributes tailored 
specifically to create documentation, like:

* tabs
* complex tables
* videos
* collapsible blocks
* sophisticated code snippets
* notes, tips, and warnings.

On top of that, it has a built-in live preview that displays the docs in the way they will appear on the web, 
and a possibility to build docs locally so that you can review them without running a build on a CI/CD.

Under the hood, the ability to author and publish documentation is supported by the [Writerside plugin]() for IntelliJ IDEs, 
which lets you write docs inside your development environment without switching to a separate tool.

We’re going to have run configurations on TeamCity prepared for you, so that you’ll be able to run builds, 
check docs on staging and then promote updates to
your documentation pages. 

This run configuration includes more than 100 automated tests that run during the build and check the integrity and quality
of your content, and a detailed build log to let you know if something goes wrong.

What you need to do is:
* download the plugin [here]();
* create a documentation folder alongside your plugins' code or a separate docs repository;
* write the actual content with the help of templates, live preview, and assistance; 
* commit and push the result;
* promote a successful build to publish your content to the Documentation tab.

For more information, refer to the [Writerside plugin help]().