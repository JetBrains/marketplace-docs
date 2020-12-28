[//]: # (title: Free functionality in a paid plugin)

To allow users who have not purchased a license for the plugin to use part of the functionality for free, you should set an `optional` parameter in `product-descriptor` to *true*.

 ```xml
 <product-descriptor code="PPAIDPLUGIN" release-date="20201225" release-version="20201" optional="true"/>
 ```
With an optional attribute, the IDE will not check a license on a startup and plugin will be loaded.
It is up to the plugin to decide what functionality requires a license. It is also supposed that if the paid functionality is called, the plugin can check if the license is obtained and, if not, request the user to activate the license.

You can use the following `requestLicense` method to open the Register dialog, when it is needed:

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
You can see the usage of this method in [our demo plugin](https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/51208c42e2692cee1843595f345a2319caa5660a/src/main/java/actions/MakeCoffeeAction.java#L81).