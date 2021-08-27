[//]: # (title: Preparing an IDE for tests with a Marketplace Demo environment)


Marketplace Demo works with [Sales Systems Marketplace Demo](https://mp.jpf-demo.aws.intellij.net) and runs on the [test server]( https://master.demo.marketplace.intellij.net/). That is why the IDE has to be additionally configured to work with it instead of the production JetBrains Account / Sales System and Marketplace.

1. Please go to Help | Edit Custom Properties... to open the idea.properties file in the editor and add:

```jb.service.configuration.url=https://mp.jpf-demo.aws.intellij.net/testservices/JetBrainsAccount.xml>```

2. Then use Help | Edit Custom VM Options... to open the IntelliJ IDEA 2018.2.app.vmoptions file (or similar depending on your version) in the editor and add:

```-Didea.plugins.host=https://master.demo.marketplace.intellij.net/>```

<note>
<p>To route the IDE requests to the Marketplace Demo instance, you are modifying the internal parameters of the IDE. Don't forget to remove these custom VM Options and Properties after testing. Otherwise, your IDE experience could be disrupted at any time.</p>
</note>

Alternatively, you can add plugins to the IDE from the disk:

<img src="installfromthedisk.png" alt="Plugin Manager"
width="706"/> 
