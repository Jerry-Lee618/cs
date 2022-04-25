1、IDE加载maven依赖总是失败，提示outOfMemory

The solution is to set 
-Xmx1g (or more) in Maven VM options for importer (yes, it is a separate option!). Go to "Settings/Preferences -> Build Tools -> Maven -> Importing", and find the option there.

2、[IntelliJ inspection gives "Cannot resolve symbol" but still compiles code](https://stackoverflow.com/questions/5905896/intellij-inspection-gives-cannot-resolve-symbol-but-still-compiles-code) 多模块工程，idea提示找不到symbol

First of all you should try File | Invalidate Caches and if it doesn't help, delete IDEA system directory. Then re-import the Maven project and see if it helps.

In some weird cases compiled classes may report wrong info and confuse IDEA. Verify that the classes from this jar report correct names using javap.
