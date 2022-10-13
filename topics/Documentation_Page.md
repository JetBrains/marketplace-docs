[//]: # (title: Documentation Page)

If your plugin needs not only a landing page with a features' overview but user-facing documentation, 
the **Documentation** page is coming into play.

Unlike [Custom pages](custom-pages.xml), the **Documentation** page is designed to host documentation 
in a separate tab. 

This is not a single page but a full-fledged help instance with a structure, a table of contents, and in-topic navigation. 
Like the one you're reading right now. 
You can check some more examples here: [Grazie Professional](https://plugins.jetbrains.com/plugin/16136-grazie-professional/docs), [Rust](https://plugins.jetbrains.com/plugin/8182-rust/docs), and [Edu Tools](https://plugins.jetbrains.com/plugin/10081-edutools/docs).


If you are asking yourself why you should bother about writing documentation for your plugin, here are a few tips:
* Documentation makes your solution discoverable and searchable. When product documentation is online, 
external search engines will bring it to everyone who types the keywords into the search query.
* Documentation helps you to stand out and communicate features of a plugin better so that your customers get the most out of it.
* Documentation makes your product look more professional and reliable and helps build trust in it.
* Documentation is a way to support your current users. If they find answers in documentation, this will decrease the support load, which is crucial for a small team. Good documentation also often leads to higher rating of a plugin.

You can use not only common Markdown but a variety of semantic markup elements and attributes tailored 
specifically to create documentation, like:

* tabs
* complex tables
* videos
* collapsible blocks
* smart code snippets
* notes, tips, and warnings.

Under the hood, the ability to author and publish documentation is supported by the [Writerside plugin]() for IntelliJ IDEs,
which lets you write docs inside your development environment without switching to a separate tool.

On top of that, it has a built-in live preview that displays the docs in the way they will appear on the web, 
and a possibility to build docs locally so that you can review them without running a build on a CI/CD.

We’re going to have run configurations on TeamCity prepared for you, so that you’ll be able to run builds, 
check docs on staging and then promote updates to
your documentation pages. 

This run configuration includes more than 100 automated tests that run during the build and check the integrity and quality
of your content, and a detailed build log to let you know if something goes wrong.

What you need to do is:
* download the plugin [here](https://plugins.jetbrains.com/plugin/20158-writerside);
* create a documentation folder alongside your plugins' code or a separate docs repository;
* write the actual content with the help of templates, live preview, and assistance; 
* commit and push the result;
* promote a successful build to publish your content to the Documentation tab.

For more information, refer to the [Writerside plugin help](https://plugins.jetbrains.com/plugin/20158-writerside/docs).