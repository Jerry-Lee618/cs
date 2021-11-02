1、IDE加载maven依赖总是失败，提示outOfMemory

The solution is to set 
-Xmx1g (or more) in Maven VM options for importer (yes, it is a separate option!). Go to "Settings/Preferences -> Build Tools -> Maven -> Importing", and find the option there.
