GWSImmutableVMKit
=================

By using some Collections tricks to not to mutable something we can make 
View-Models immutable. For using Google Data Binding that gives us the edge 
to get Android Responsive Applications FeatureSet without the huge learning 
curve of RxJava or Agera.

This translates into once again being able to fast prototype applications 
without major refactoring to get to the polished product. AND, immutable view-models 
can also be flexible enough to bring in RxJava or Agera if we really need it.

The immutable power of the View-Models comes from two classes, the Util class 
which provides methods of with and  without to work with Maps and Lists that 
produce unmodified Collections instead of modified Collections..ie the immutable 
quality.

The rest of the immutable magic is in the GWSImmutableVMKIt class in the apply method.
The technique of Software Transactional Memory is used by 
`rootReference.compareAndSet(originalRoot, originalRoot.withViewState(function(viewState)))`
so that the call will be atomic and thread-safe.

OH, but there is MORE.

Google had to have some idea that some devs would assume that View-Models is 
just for MVVM and thus know that View-Models could be implemented for 
both MVC and MVP. One of the Tenants of Android is that you could use any 
Application Architecture pattern, even FLux.


Yes, you can implement View-Models for both MVC and MVP application 
architecture patterns using this library. There will be base classes for 
each application architecture pattern.



# Usage

if library, describe how to download library using jitpack than describe how to use the library.

I use jitpack to upload my libraries so you put this in your root buildscript:

```groovy
allprojects {
        repositories {
            jcenter()
            maven { url "https://jitpack.io" }
        }
   }
```
Than in the module buildscript:


```groovy
compile 'com.github.shareme:GWSImmutableVMKit:{latest-release-number}@aar'
```

# Developed By

![gws logo](art/gws_github_header.png)

<a href="http://stackoverflow.com/users/237740/fred-grott">
<img src="http://stackoverflow.com/users/flair/237740.png" width="208" height="58" alt="profile for Fred Grott at Stack Overflow, Q&amp;A for professional and enthusiast programmers" title="profile for Fred Grott at Stack Overflow, Q&amp;A for professional and enthusiast programmers">
</a>


Created by [Fred Grott](http://shareme.github.com).


# Credits

Credit goes to Konstantin Mikheev with his plux project:

[Phlux](https://github.com/konmik/Phlux)

although I do not think Konstantin realizes the gem he found.

I extend his idea and show that it can be applied to MVC, MVP, MVVM, etc.

# Resources

Resources can be found at the [GWSTheWayOfAndroid wiki](http://github.com/shareme/GWSTheWayOfAndroid/wiki).



# License

Copyright (C) 2016 Fred Grott(aka shareme GrottWorkShop)

Licensed under the Apache License, Version 2.0 (the "License"); you 
may not use this file except in compliance with the License. You may 
obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software 
distributed under the License is distributed on an 
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, 
either express or implied. See the License for the specific language 
governing permissions and limitations under License.