[//]: # (title: Free functionality in a paid plugin)

<p>There is the option to offer basic or limited features in a paid plugin at no cost, much like a freemium model. Your plugin is marked with the “Some features of the plugin require a paid subscription” tag that informs users about paid features.</p>

<img src="free-paid-example.png" alt="An example of how the tag looks like"
width="706"/>

<p>The reasons for implementing this model can be different, from helping you ease the transition from being a free plugin to a paid one, or simply attracting new users.</p>

<p>To allow users who have not purchased a license for the plugin to use part of the functionality for free, you should set the <code>optional</code> <a href="add-required-parameters.md">parameter</a> in <a href="https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html?from=jetbrains.org">product-descriptor</a> to <control>true</control>.</p>

 ```xml
 <product-descriptor code="PPAIDPLUGIN" release-date="20201225" release-version="20201" optional="true"/>
 ```
<p>Thanks to this optional attribute, the IDE will not check for a license on IDE startup, which allows us to install the plugin and start using it.
</p>

<warning>
    <p>
        Please note, that once the plugin update with the <code>optional</code> parameter set to <code>"true"</code> is uploaded to Marketplace, you won't be able to switch your plugin back from freemium to fully paid model.
    </p>
</warning>

<p> It is up to the plugin developers to decide exactly what functionality will be available for free and what will require a license. To do that, please use the following <code>requestLicense</code> method that checks if a license has been obtained when the paid functionality is called.</p>

```Java
  public static void requestLicense(final String message) {
    // ensure the dialog is appeared from UI thread and in a non-modal context
    ApplicationManager.getApplication().invokeLater(() -> showRegisterDialog(message), ModalityState.NON_MODAL);
  }
  
  private static void showRegisterDialog(final String message) {
    final com.intellij.openapi.actionSystem.ActionManager actionManager = com.intellij.openapi.actionSystem.ActionManager.getInstance();
    // first, assume we are running inside the opensource version
    AnAction registerAction = actionManager.getAction("RegisterPlugins");
    if (registerAction == null) {
      // assume running inside commercial IDE distribution
      registerAction = actionManager.getAction("Register");
    }
    if (registerAction != null) {
      registerAction.actionPerformed(AnActionEvent.createFromDataContext("", new Presentation(), asDataContext(message)));
    }
  }

  // This creates a DataContext providing additional information for the license UI
  // The "Register*" actions show the registration dialog and expect to find this additional data in the DataContext passed to the action
  // - productCode: the product corresponding to the passed productCode will be pre-selected in the opened dialog
  // - message: optional message explaining the reason why the dialog has been shown
  @NotNull
  private static DataContext asDataContext(@Nullable String message) {
    return dataId -> {
      switch (dataId) {
        // the same code as registered in plugin.xml, 'product-descriptor' tag
        case "register.product-descriptor.code" : return "PPAIDPLUGIN";

        // optional message to be shown in the registration dialog that appears
        case "register.message" : return message;
        
        default: return null;
      }
    };
  }
```

<p>If a license is not activated, the <code>requestLicense</code> method can open the Register dialog and prompt the user to activate the license. Alternatively, you can add a button in the menu to activate the plugin using this <code>requestLicense</code> method or come up with your own way of using the method. </p>
<p>You can see the usage of this method in <a href="https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/51208c42e2692cee1843595f345a2319caa5660a/src/main/java/actions/MakeCoffeeAction.java#L81">our demo plugin</a>.</p>