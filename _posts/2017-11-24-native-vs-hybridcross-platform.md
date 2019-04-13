---
layout: post
comments: true
author: rolly
image: /uploads/notes-image.jpg
categories: [opinion,architecture]
tags:[hybrid,mobile]
---
This is an existential question for every mobile developer - especially for those who are deciding to start their career or are just starting.
<!--more-->
**What is the difference between Native vs Hybrid/Cross-Platform development tools?**Native development is using plain vanilla Xcode using Objective-C or Swift, and Java (an Android derivative) and, Eclipse or Android Studio. Hybrid/Cross-Platform development tools is anything that doesn’t fall under it - to put it simply. Any development tools claiming they build ‘native code’ is a marketing gimmick - e.g. Xamarin and React-Native. Why do they claim they build native code? All hybrid/cross-platform tools still need to create a skeleton project using the native languages for iOS and Android for it to be compiled on each platform. They build an engine around it so developers use either Javascript or C\# (or any other language) as the main language to build apps. The native part of the project is inaccessible to hybrid/cross-platform developers. They all work the same way. Skeleton native app (with access to native APIs) - integration engine - bytecode from C\# or JS.

**Which one is better?**I can’t answer this question - obviously from bias but I can answer a similar question - **why do hybrid/cross-platform tools exist?**When the mobile industry boom started a lot of companies took a couple more years to adopt a mobile platform strategy. When a need for mobile solutions is needed there aren’t enough mobile developers around to work for them or looked for cost-effective solutions. Frameworks like Phonegap emerged to allow HTML5 web developers to build mobile apps. On this initiative cross-platform tools grew to address a single-code for iOS and Android platforms. By the numbers it looks cost-effective and faster. History though say otherwise. Phonegap reached its limits in optimizing its engine to work as fast as native code. Animations and screen transitions are fluid in native apps, HTML5 hybrid apps weren’t. Xamarin and React-Native introduces their own new engines and received a new following.

For aspiring mobile developers which tools to use is a question of personal preference. Not all companies can afford projects for full native applications - and invest on cross-platform tools. There is novelty in being able to build apps for iOS and Android. iOS and Android native developers, however, are premium jobs that companies hire for because of rarity and technology they offer for mobile solutions.