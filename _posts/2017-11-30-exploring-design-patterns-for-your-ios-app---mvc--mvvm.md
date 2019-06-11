---
layout: post
comments: true
author: Rolly Ceballos
image: /uploads/design-notes.jpg
categories:
  - design
tags:
  - mobile
  - mvc
  - mvvm
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

<span class="image fit">![](/uploads/mvc-diagram.jpg)</span>

> The ViewController's in the UIKit framework is full of delegate relationship with underlying views to update the views with datasources - e.g. UITableViewControllers with UITableViews

On a multi-screen iOS app (as is typical on a full product app) the project will have multiple MVC groups. And it looks like the diagram below (ref from CS193P **Stanford’s Develop IOS 11 app with Swift**)&nbsp;

<span class="image fit">![](/uploads/diagram-mvc-model.jpg)</span>

> UI transitions are handed over between controllers only. The business logic or UI flow is maintained in the controllers.

When an app transitions from the first screen on app launch to the next it passes the focus of responsibility to a new ViewController. This design encourages encapsulation of each screen and simplifies code logic for each view controller to focus on the screen in the foreground. It is highly encouraged as a best practice in MVC that each controller only take care of one screen at a time to avoid a controller getting too monolithic to handle for e.g. a screen for iPhone and iPad in Universal apps. This&nbsp;**preference/practice** makes&nbsp;**MVC** particularly similar to&nbsp;**MVP**.&nbsp;**Model-View-Presenter** pattern enforces one controller-view relationship in a web application, while&nbsp;**MVC** in web apps have one controller that directs to different views but handles the state of a user’s session. Don’t get yourself confused of implementing MVC and MVP in mobile apps and web apps.

As a precaution an iOS app should never look like the following diagram below.

<span class="image fit">![](/uploads/mvc-not-working.jpg)</span>

> This is a messy way of implementing an app. It becomes very difficult for new developers to follow the UI flow with this structure, and can leave view controllers with too many logic.

The UIKit Framework library (contains UITableViewController, UINavigationController, UITabBarController) was built from the ground up with delegation pattern or uses protocol-oriented programming to keep the controller and views in-sync with action triggers like a button press or text entry in a text field to define next actions. All UI interaction depends on this design and has been so ever since the CocoaTouch library was introduced for developers to start building iOS apps.

**Model-View-ViewModel**

The&nbsp;[MVVM](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel){: target="_blank"}&nbsp;model was developed by Microsoft for the Windows Presentation Foundation or the .NET Framework. As with any Microsoft app architecture this pattern has the added layer of data-binding between the view and model to ‘simplify’ event-driven programming for user interfaces. It somehow makes the round-trip update of view-controller-model on UI input from the user. It does, however, require additional components to build this additional layer as the Swift iOS libraries does not inherently do data-binding automatically (or probably never will).

<span class="image fit">![](/uploads/mvvm-diagram.png)</span>

To quote from the&nbsp;[Wikipedia](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel?fbclid=IwAR1Om1x1o859nNlKqN4AngwdflgSqxXJlNe653_AGjmRMgLM07jlrkW4Oqg){: target="_blank"}&nbsp;entry

“The view modelis an abstraction of the view exposing public properties and commands. Instead of the controller of the MVC pattern, or the presenter of the MVP pattern, MVVM has a binder. In the view model, the binder mediates communication between the view and the data binder. The view model has been described as a state of the data in the model”

This pattern becomes very useful for hybrid/cross platform frameworks available in third-party IDE tools like Xamarin and ReactNative as it also fits pretty well with C\# and Javascript for its web event-driven approach.

**What Do I Recommend?**

I personally use MVC in all my iOS projects back when we only had Objective-C and even with Swift. The UIKit framework library and all the Xcode enhancements to extensively use Storyboards, IBActions, IBOutlets and delegation patterns are based on the MVC pattern. It’s more pragmatic for any real&nbsp;**native** iOS developers to use MVC. There are derivative design patterns that can go away from the basic MVC architecture but I advise not to stray too far otherwise any future SDK improvements will become less beneficial.

Mobile app developers who are using cross-platform tools like Xamarin or ReactNative can pursue MVVM as it fits the framework very well. I would say that most developers in these group adopts this pattern more than anything else - C\# is .NET.

I hope this helps iOS developers see the motivation between MVC and MVVM and decide for themselves which fits better for future projects.