[//]: # (title: Plugin Recommendations)

The IntelliJ Platform IDEs may recommend a plugin for installation in one of the following cases:

 * If a project contains files of types which are unsupported by the running IDE but are supported by a plugin
   available in the plugin repository.
   
 * If a project was created in n different IDE installation which had the plugin installed, and includes shared
   settings (modules, facets, artifacts, or run configurations) configured using the plugin.

IntelliJ Platform IDEs only show plugin suggestions in the appropriate context, so they are meaningful to the user.

<warning><p>Features implemented by third-party plugins are subject to review and approval by JetBrains Marketplace, and must meet <a href="https://plugins.jetbrains.com/legal/approval-guidelines">the approval criteria</a>. We may establish additional criteria on a case-by-case basis and reserve the right to reject the feature implementation.</p></warning>

The [`feature extractor`](https://github.com/JetBrains/intellij-plugin-verifier/tree/master/intellij-feature-extractor/) tool catalogs these types of features for a plugin. It works by statically analyzing the bytecode of a plugin to extract values passed to the IntelliJ Platform APIs that support extending features in the above list. 

However, if values are dynamically evaluated in a plugin, the `feature extractor` may return incomplete results.

If you cannot find your plugin in [the list of features](https://plugins.jetbrains.com/feature/), you can either make your code easier for the analysis or ask JetBrains to add manually any missed feature types.

## File Type

A plugin can [support specific file types](https://plugins.jetbrains.com/docs/intellij/registering-file-type.html). When there is a file with a specific extension, pattern or name open in an IDE, a hint will be shown to users prompting them to install your plugin.

Both variants are supported by the `feature extractor`:
* Extend [FileTypeFactory](https://upsource.jetbrains.com/idea-ce/file/idea-ce-4f9b5f89b2a19ce700b1373a465c16b28ed8ad52/platform/platform-api/src/com/intellij/openapi/fileTypes/FileTypeFactory.java) and feed supported file extensions/exact file name matches in `createFileTypes(FileTypeConsumer)`, values of `FileTypeConsumer` are analyzed.

* Register `com.intellij.fileType` extension point (available in 2019.2+), all attributes are analyzed.

A suggestion to install plugins which support the _\*.d_ Extension Type:

![File Extensions Type of Feature](feature_extractor_extensions.png)

Refer to [Registering a File Type](https://plugins.jetbrains.com/docs/intellij/registering-file-type.html) to provide this feature in a plugin.

<warning>
    <p>
        Please note, that a file type won't get recommended if it conflicts with a bundled file type.
    </p>
</warning>

## Run Configuration Type

When you want IDEs to show that your plugin supports Run Configuration Type, you need to implement [ConfigurationType](https://upsource.jetbrains.com/idea-ce/file/idea-ce-4f9b5f89b2a19ce700b1373a465c16b28ed8ad52/platform/lang-api/src/com/intellij/execution/configurations/ConfigurationType.java) and implement the `getId()` method. The `feature extractor` analyzes the value of `getId()`.

A suggestion to install plugins that support the *Run D App* Configuration Type:

![Configuration Type of Feature](feature_extractor_configuration.png)

Refer to [Run Configurations](https://plugins.jetbrains.com/docs/intellij/run-configurations.html) to get more information about how to declare this feature in your plugin.

## Facet Type

To support a Facet Type feature, you should extend [FacetType](https://upsource.jetbrains.com/idea-ce/file/idea-ce-4f9b5f89b2a19ce700b1373a465c16b28ed8ad52/platform/lang-api/src/com/intellij/facet/FacetType.java), and pass `stringId` to its constructor. The value of the `stringId` parameter will be analyzed by the `feature extractor`.

A notification to install plugins that support the *jangaroo* Facet Type:

![Facet Type of Feature](feature_extractor_facet.png)

Refer to [Facet](https://plugins.jetbrains.com/docs/intellij/facet.html) for additional information.

## Module Type

If you want IDEs to show a prompt that your plugin can support creating specific Module Types, you should extend [ModuleType](https://upsource.jetbrains.com/idea-ce/file/idea-ce-4f9b5f89b2a19ce700b1373a465c16b28ed8ad52/platform/lang-api/src/com/intellij/openapi/module/ModuleType.java) and pass the `id` parameter for your Module Type to its constructor. The `feature extractor` will evaluate the values of `id`.

See [Module](https://plugins.jetbrains.com/docs/intellij/module.html) and [Supporting Module Types](https://plugins.jetbrains.com/docs/intellij/module-types.html) for more information about supporting Module Types.

## Artifact Type

To support specific Artifact Types, extend [ArtifactType](https://upsource.jetbrains.com/idea-ce/file/idea-ce-4f9b5f89b2a19ce700b1373a465c16b28ed8ad52/java/compiler/openapi/src/com/intellij/packaging/artifacts/ArtifactType.java), and pass an `id` parameter to its constructor. The value of the `id` parameter is analyzed by the `feature extractor`.

An example suggestion to enable a plugin which supports a *dm.bundle* Artifact Type:

![Artifact Type of Feature](feature_extractor_artifacts.png)

## Dependency Support

To support a specific dependency you should declare a tag like `<dependencySupport kind="java" coordinate="org.junit:org.junit" displayName="Junit"/>` in the plugin.xml file.

