[//]: # (title: 5. Obfuscate the plugin)

We recommend you to obfuscate the paid plugin before uploading it to the plugins repository. Every application can be hacked, but proper obfuscation makes this job much harder.

Some of the popular Java obfuscators:

* ProGuard

* JODE

* JavaGuard

* RetroGuard

* jarg

* yGuard

* ALLATORI

* DashO

* Zelix KlassMaster

* and more...

##Zelix Klassmaster

At JetBrains, we had a lot of experience with [Zelix Klassmaster](https://www.zelix.com/klassmaster/index.html), so we are sharing some of the information on how to configure it. Information about Zelix configuration and tips on the features is provided by *Eugene Zhuravlev*, our IntelliJ IDEA developer who implemented the licensing mechanism and the Marketplace support in IntelliJ IDEA.

You can find full documentation at https://www.zelix.com/klassmaster/docs/index.html, and we have been using the script file (not the UI tool.)

Configuration of the obfuscator we use for IntelliJ IDEA based products:

```
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

The most important features:

`trim` - removes unused fields, methods, and classes. A useful feature, but you should use it carefully - normally we are limiting the scope to the licensing packages only. For example, `static final` constants are normally inlined by the compiler, but the fields and their values are preserved in the code. It might give additional "hints" to those analyzing the bytecode of your plugin.

`obfuscateFlow=aggressive` can tangle the control flow in the method which complicates adding the hacking code.

`encryptStringLiterals=enhanced` - very important. Encrypts the string literals which also masks reflection calls, hardcoded signatures and certificates.

`methodParameterChanges=flowObfuscate` - additional protection level complicating decryption of scrambled string literals. It creates additional dependencies and connections between classes, which results in the protection from getting the class from IntelliJ IDEA Community Edition (open source) and putting it to IntelliJ IDEA Ultimate Edition expecting it to work.

`obfuscateReferences=normal` - it's important to configure this feature for some packages and classes. The meaning of this feature is as follows: if you are calling some method of an object from some package, let's say `javax.security.*`, the obfuscator will mask this call changing it to the reflection with the encrypted name of the method. With this feature, you are hiding the places where some important libraries are called, and without this feature, it would be very useful to locate these pieces of code via links to the libraries.

We surely recommend reading the full documentation to understand how it works. We believe that the plugins can use more aggressive obfuscation/scrambling than we do in IntelliJ IDEA as we have a lot of APIs we have to preserve on our side. Don't be shy about scrambling the code too much - it increases the protection a lot.

The prices for Zelix Klassmaster start at US$239 (applies if your organization (i.e. your company) consists of no more than two people and has employed or contracted no more than two people at any one time in the twelve months prior to the order date.)

##ProGuard

We have tried getting the same result with ProGuard (as it's free), and one of the major drawbacks would be lack of Strings Obfuscation support (Zelix option `encryptStringLiterals=enhanced`). Some users are complimenting ProGuard with additional paid string obfuscator (e.g. https://jfxstore.com/stringer/, see also [this article](https://medium.com/@anujjindal7/android-string-literals-obfuscation-in-code-6700a85d5cd1).) By default, ProGuard is doing `shrink`, `optimize`, `obfuscate`, `preverify`, and all four options are recommended. We would also recommend to use `-overloadaggressively` for more aggressive obfuscation and `-applymapping ChangeLog.txt` to keep the log of changes. See more options [here](https://www.guardsquare.com/en/products/proguard/manual/usage#obfuscationoptions).

##Other

Surely, similar features exist in other Java obfuscators, including the free/open source one.

As of now, we couldn't find any Kotlin obfuscators or Java obfuscators with Kotlin support, so we can't recommend much here. We are looking into the situation right now and started working with Kotlin team to make sure that support for Kotlin is provided on the obfuscators side.
 