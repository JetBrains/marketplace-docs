[//]: # (title: Embeddable Content)

You can embed Marketplace content onto your website. Currently, the following embeddable content is available:
 - Plugin Card,
 - Install to IDE button.

### How to

1. Go to the plugin dashboard embeddable content section.
2. Choose the **distribution type**.
3. Include this content on your website.
4. If you're not a plugin author and don't have permission to edit the plugin, use the codes in the section below.

**Distribution type**

There are two possible embeddable distributions: 
 - `iframe`,
 - `script`.
 
We recommend using the `script` distribution type because it handles the `Content Security Policy` limitations, such as redirecting to the Marketplace page.

### Including script

In order to include the script copy the `script` code on the page or use the following snippet:
```html
<script src="https://plugins.jetbrains.com/assets/scripts/mp-widget.js"></script>
```

After including the script on the page, the global variable `MarketplaceWidget` should be available on your page. To set up the widget, you need to call the function `setupMarketplaceWidget` and provide it with the following arguments:

 - `@param type` - `card` or `install`,
 - `@param id`   - plugin id,
 - `@param root` - the root container. Can be a valid `CSS Query` or `HTMLElement`.

```html
<script src="https://plugins.jetbrains.com/assets/scripts/mp-widget.js"></script>
<script>  
  MarketplaceWidget.setupMarketplaceWidget('install', 8554, "#root");  
</script>
```

### Including iframe

In case you can't include the script on the page, you can also add an `iframe`. Please, use the code below.

**Card**
```html
<iframe frameborder="none" width="384px" height="319px" src="https://plugins.jetbrains.com/embeddable/card/<id>"></iframe>
```

**Install button**
```html
<iframe frameborder="none" width="245px" height="48px" src="https://plugins.jetbrains.com/embeddable/install/1347"></iframe>
```

**Limitations of the iframe option**

Due to the `Content-Security-Policy`, we can't redirect the user to the Marketplace page. This case affects the situation when a user has no IDE available for the installation, and we show the link *Get From Marketplace*.
