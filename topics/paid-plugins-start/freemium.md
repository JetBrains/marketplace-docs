[//]: # (title: Freemium plugins)

<p>Freemium plugins offer some features at no cost in addition to paid features. The reasons for implementing this model can be different, from helping you attract new users, or simply making some profit without going fully paid.</p>

<chapter title="How does it look for users?"
         id="how-does-it-look" 
         level="3"/>

<p>Users will see an explanatory note under the “Get” button that informs them about paid features.</p>

<img src="free-paid-example.png" alt="An example of how the tag looks like"
width="706"/>

<p>Starting from 213.* version of IDE, such plugins are marked with the “Freemium” tag and the <emphasis>“Install a version with limited functionality for free or activate the 30-day trial for full access”</emphasis> note:</p>

<img src="ide-freemium.png" alt="Freemium tag in IDE"
width="706"/>

<p>While they have the “Freemium” tag along with the “Paid” tag in the older IDE versions:</p>

<img src="old-ide-freemium.png" alt="Freemium tag in old IDEs"
width="706"/>

<chapter title="How to make your plugin freemium?"
id="how-to-make-your-plugin-freemium"
level="3"/>

<list type="decimal">
        <li><control>Submit the request and create a product code</control>
             <p>Please <a href="submit-a-request-to-sell-plugins-at-the-marketplace.md">submit a request</a> via the <a href="https://plugins.jetbrains.com/build-and-market#form">Apply to Marketplace</a> form. After that, you will be contacted by our vendor success team via email with further steps. One of these steps is to create a <a href="obtain-a-product-code-from-jetbrains.md">Product Code</a> and provide it in the reply.</p>
        </li>
        <li>
            <p><control>Prepare your plugin</control></p>
            <p>Make the following changes to your code to prepare your plugin for publishing:</p>
            <chapter title="Define additional parameters"
             id="define_additional_parameters"
             initial-collapse-state="collapsed"
             hide-from-structure="true"
             level="5">
                  <procedure>
                      <p>You must define the following parameters in the plugin descriptor (plugin.xml):</p>
                      <code style="block" lang="XML" title="Parameters">product-descriptor code="PPAIDPLUGIN" release-date="20201225" release-version="20201" optional="true"</code>
                      <p>More information on these additional parameters can be found <a href="add-required-parameters.md">here</a>.</p>
                      <p>Please make sure the <code>optional</code> parameter in product-descriptor is set to <control>true</control>. Thanks to this optional attribute, the IDE will not check for a license on IDE startup, which allows us to install the plugin and start using it.</p>
                         <warning>
                                <p>Please note that the <code>optional</code> parameter can be set only once, with the first uploaded plugin version containing this parameter. So, you need to choose between freemium and fully paid models before uploading the first paid plugin version, as it can't be changed later.</p>
                         </warning>
                  </procedure>
             </chapter> 
             <chapter title="Implement license method"
             id="implement_license_method"
             initial-collapse-state="collapsed"
             hide-from-structure="true"
             level="5">
                  <procedure>
                       <p>It is up to the plugin developers to decide exactly what functionality will be available for free and what will require a license. To do that, please use the following <code>requestLicense</code> method that checks if a license has been obtained when the paid functionality is called.</p>
                       <code style="block" lang="Java"
                       initial-collapse-state="collapsed">
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
                        }</code>
                        <p>If a license is not activated, the <code>requestLicense</code> method can open the Register dialog and prompt the user to activate the license. Alternatively, you can add a button in the menu to activate the plugin using this <code>requestLicense</code> method or come up with your own way of using the method.</p>
                        <p>You can see the usage of this method in our <a href="https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/51208c42e2692cee1843595f345a2319caa5660a/src/main/java/actions/MakeCoffeeAction.java#L81">demo plugin</a>.</p>
                  </procedure>
             </chapter>
        </li>
        <li>
             <p><control>Upload and Release</control></p> 
             <p>The process of publishing is the same as for paid plugins. Please refer to this guide on <a href="uploading-a-new-plugin.md">how to upload</a> and <a href="release-plugin.md">release your plugin</a>.</p>
        </li>
</list>



