---
layout: post
comments: true
author: rolly
image: /uploads/design-notes.jpg
categories:
  - opinion
  - architecture
tags:
  - hybrid
  - mobile
---

With all the hype in Youtube content creators nowadays aspiring iOS developers will have a rich collection of references to consume to learn Swift programming. I’d wish I’d have the same convenience back when I was starting my career in software engineering. However, too much of something can be overwhelming. A lot of ideas are abound and different groups of developers polarize to different design patterns on how to build iOS apps on the get-go. Developers get pulled into an MVC-vs-MVVM discussions and it can leave a young developer in a limbo.

I’d like to help out on clarifying where each pattern matters - MVC and MVVM. MVC - Model-View-Controller - is a pattern widely endorsed by Apple ever since the early days of Xcode on Mac development using Objective-C. MVVM - Model-View-ViewModel - has recently just been considered for Swift iOS app structure as an alternative to MVC but has been used in Microsoft’s ASP .NET Framework development.

**Model-View-Controller**

The MVC pattern as the acronym implies splits the “roles” of components in 3 “concerns” or camps. The Model, View and Controller.

To quote Paul Hegarty from Stanford’s **CS193P Developing iOS 11 Apps with Swift**.

* **Model&nbsp;**\- What your application is (but&nbsp;*not* how it is displayed)
* **Controller&nbsp;**\- How your&nbsp;*model* is presented to the user (UI logic)
* **View&nbsp;**\- The&nbsp;***controller’s*** minions

The MVC pattern has a few simple rules:

1. The&nbsp;**Controller** speaks to the&nbsp;**Model**
2. The&nbsp;**Controller** talks to the view - update, animation, transition to new controller/view
3. The&nbsp;**Model** and&nbsp;**View** never talks with each other, they are independent. The modelis not influenced by how it is presented, and the viewsare universal components such as buttons, switches and text fields that do not concern on how the model looks like. (see photo below)
4. The View ‘blindly’ talks to the Controller with protocol-oriented programming or delegation (delegates)

![The ViewController's in the UIKit framework is full of delegate relationship with underlying views to update the views with datasources - e.g. UITableViewControllers with UITableViews](/uploads/mvc-diagram.jpg "Model-View-Controller Diagram")