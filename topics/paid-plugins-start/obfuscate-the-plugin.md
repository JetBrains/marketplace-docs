[//]: # (title: Obfuscate the plugin)

We recommend obfuscating your paid plugin before uploading it to the Marketplace. Every application can be hacked, but proper obfuscation makes doing so much harder.

Here are some of the most popular Java obfuscators:

* ProGuard
* JODE
* JavaGuard
* RetroGuard
* jarg
* yGuard
* ALLATORI
* DashO
* Zelix KlassMaster


## Zelix Klassmaster

At JetBrains, we have a lot of experience with [Zelix Klassmaster](https://www.zelix.com/klassmaster/index.html), so we are sharing some information about how to configure it. Information about Zelix configuration and tips for regarding the features is provided by *Eugene Zhuravlev*, the IntelliJ IDEA developer who implemented the licensing mechanism and Marketplace support in IntelliJ IDEA.

You can find the full documentation [here](https://www.zelix.com/klassmaster/docs/index.html), and we have been using the script file (not the UI tool.)

This is the configuration for the obfuscator we use for IntelliJ IDEA based products:

```java
trim deleteSourceFileAttributes=false
 deleteDeprecatedAttributes=false
 deleteAnnotationAttributes=false
 deleteExceptionAttributes=false
 deleteDebugExtensionAttributes=true
 deleteUnknownAttributes=false
 ;

obfuscate
 changeLogFileOut="ChangeLog.txt"
 keepInnerClassInfo=ifNameNotObfuscated // should be true to allow use of OpenAPI inner classes
 keepGenericsInfo=true
 aggressiveMethodRenaming=true
 obfuscateFlow=aggressive
 exceptionObfuscation=heavy
 encryptStringLiterals=enhanced
 legalIdentifiers=true
 lineNumbers=keep
 hideFieldNames=false
 hideStaticMethodNames=false
 randomize=true
 methodParameters=keepVisibleIfNotObfuscated
 localVariables=keepMethodParametersIfNotObfuscated
 methodParameterChanges=flowObfuscate
 obfuscateReferences=normal
 ;
```

And these are the most important features:

`trim` removes unused fields, methods, and classes. It’s a useful feature, but you should use it carefully. Normally we limit the scope to the licensing packages only. For example, `static final` constants are normally inlined by the compiler, but the fields and their values are preserved in the code. It might give additional "hints" to those analyzing the bytecode of your plugin.

`obfuscateFlow=aggressive` can tangle the control flow in the method, which complicates the addition of hacking code.

`encryptStringLiterals=enhanced` is very important. It encrypts the string literals, which also masks reflection calls, hardcoded signatures, and certificates.

`methodParameterChanges=flowObfuscate` is an additional protection level that complicates the decryption of scrambled string literals. It creates additional dependencies and connections between classes, which results in protection against getting classes from IntelliJ IDEA Community Edition (open source) and putting it in IntelliJ IDEA Ultimate Edition, expecting them to work.

`obfuscateReferences=normal` is important to configure for some packages and classes. If you are calling a method of an object from some package, let's say `javax.security.*`, the obfuscator will mask this call changing it to the reflection with the encrypted name of the method. With this feature, you are hiding the places where some important libraries are called, and without this feature, it would be very easyl to locate these pieces of code via links to the libraries.

We certainly recommend reading the full documentation to understand how obfuscation works. We believe that the plugins can use more aggressive obfuscation/scrambling than we do in IntelliJ IDEA, as we have a lot of APIs that we have to preserve on our side. Don't be shy about scrambling the code – it increases the protection a lot.


## ProGuard

<p>We have tried getting the same result with ProGuard (as it's free), and one of the major drawbacks was the lack of String Obfuscation support (Zelix option `encryptStringLiterals=enhanced`). Some users complement ProGuard with an additional paid string obfuscator (e.g. <a href="https://jfxstore.com/stringer/"/>), see <a href="https://medium.com/@anujjindal7/android-string-literals-obfuscation-in-code-6700a85d5cd1">this article</a></p>

By default, ProGuard can `shrink`, `optimize`, `obfuscate`, and `preverify`, and all four options are recommended. We would also recommend using `-overloadaggressively` for more aggressive obfuscation and `-applymapping ChangeLog.txt` to keep a log of changes. You can learn about more options [here](https://www.guardsquare.com/en/products/proguard/manual/usage#obfuscationoptions).


## Other

Similar features surely exist in other Java obfuscators, including free/open-source ones.

As of now, we haven’t been able to find any Kotlin obfuscators or Java obfuscators with Kotlin support, so we can't recommend much here. We are looking into the situation and we’ve started working with the Kotlin team to make sure that support for Kotlin is provided on the obfuscator’s side.
