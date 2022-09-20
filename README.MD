# JetBrains Marketplace Documentation

This is the repository for [JetBrains Marketplace Documentation](https://plugins.jetbrains.com/docs/marketplace/?from=GH-README) site.

## Getting Started

1. Ask for permission to commit to this repository in the [Administration](https://youtrack.jetbrains.com/newIssue?project=ADM) project.
2. Install the [Stardust](https://helpserver.labs.jb.gg/help/stardust/1.0/installing-stardust.html) plugin into your IntelliJ-based IDE.
3. Create a new project from version control using this repository [Git link](https://github.com/JetBrains/marketplace-docs.git).

## Contributing

* All major changes should be added in separate branches and require PR.
* Please use [this checklist](https://helpserver.labs.jb.gg/help/stardust/1.0/review-checklist.html) when reviewing someone's changes.
* Follow the [content guidelines](https://helpserver.labs.jb.gg/help/stardust/1.0/creating-content.html) and use the Stardust notation only (without Markdown).
* Follow the [SEO guide](https://docs.google.com/document/d/1UI54LSP0mUR-R_FRDs2OKmlAyGhX70OLjKTBhNRzHxQ) for every topic.
* All topics should be named in lowercase with hyphens (something-like-this.md).
* All images should be named in lowercase with hyphens and in .PNG or .GIF formats.

## Deploying

After every commit the project is being automatically built. Only the changes in the `master` branch are deployed automatically to the site.
If the deployment was successful you should find an automatic notification in [this Slack channel](https://jetbrains.slack.com/archives/C0241UU8BLK).
Usually it takes up to 1 hour to build and deploy the documentation.
You can check for build errors [here](https://buildserver.labs.intellij.net/buildConfiguration/Documentation_Teamware_MarketplaceDocs?branch=%3Cdefault%3E&buildTypeTab=overview&mode=builds) and for deployment errors [here](https://buildserver.labs.intellij.net/buildConfiguration/Documentation_Supplementals_WebHelpPromoters_MarketplaceDocsPromoterTopicsImages?branch=%3Cdefault%3E&buildTypeTab=overview&mode=builds).
