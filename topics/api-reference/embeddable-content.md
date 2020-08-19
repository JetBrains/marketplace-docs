[//]: # (title: Embeddable Content)  

You can embed marketplace content onto your web-site. Currently, the next embeddable content is available:

 - Plugin Card
 - Install to IDE button

**How to**
Go to the plugin dashboard embeddable content section. Choose the **distribution type**. Include this content on your web-site. If you're not a plugin author and you don't have permissions to edit plugin, use the codes in the section below.


**Distribution type**
There are two possible embeddable distribution. 
 - `iframe`
 - `<script>`
 
We recommend using the `script` distribution type because it handles the `Content Security Policy` limitations such as redirecting to the Marketplace page.

**Including script**
In order to include the script copy the `script` code on the page or use the following snippet
```html
<script src="https://plugins.jetbrains.com/assets/scripts/mp-widget.js"></script>
```
After including the script on the page, the global variable `MarketplaceWidget` should be available on your page. To setup the widget you need to call the function `setupMarketplaceWidget` and provide it with the arguments below

 - `@param type` - `card` or `install`
 - `@param id`     - plugin id
 - `@param root` - the root container. Can be a valid `CSS Query` or `HTMLElement`

```html
<script src="https://plugins.jetbrains.com/assets/scripts/mp-widget.js"></script>
<script>  
  MarketplaceWidget.setupMarketplaceWidget('install', 8554, "#root");  
</script>
```

**Including iframe**
In case, it's impossible for you to include the script on the page you can also include an `iframe`. Please, use the code below.

**Card**
```html
<iframe frameborder="none" width="384px" height="319px" src="https://plugins.jetbrains.com/embeddable/card/<id>"></iframe>
```

**Install button**
```html
<iframe frameborder="none" width="245px" height="48px" src="https://plugins.jetbrains.com/embeddable/install/1347"></iframe>
```

**Limitations of the iframe option**
Due the `Content-Security-Policy` we can't redirect the user to Marketplace page. 
