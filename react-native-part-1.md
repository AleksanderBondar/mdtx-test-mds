---
first_category: React Native
second_category: Mobile
third_category: ''
createdAt: 2022-01-02T23:00:00Z
title: 'React Native: why and when to use it'
short_description: A brief outline of React Native and its pros and cons
author: src/data/forestry/content/authors/michal.md
category: ''
feature_image: "/uploads/react_native.png"

---
The ever increasing capabilities of smartphones have caused an explosion of mobile apps for iOS and Android. They’ve become so commonplace you can find an app for almost anything. The common issue is not every app is on every platform and often you'll need to look for an alternative, which might just not be as good. Hell you might even think about making your own app that works just right. Well when it comes to that there’s one popular framework that can prove quite handy.

## Just a simple hackathon project

React Native started out as a internal hackathon project aimed at solving Facebook’s key issue with maintaining its app for different platforms. It’s easy to imagine how having separate code bases for different iterations of such a big app would be problematic. Facebook already had React as a framework since 2013 and they needed a way for it to fit different platforms without having to do the work separately for each one (and then doing additional work with fixing bugs, implementing updates etc. for each platform separately) That lead to the idea of the aforementioned hackathon and React Native, an open source framework for building apps for android, iOS and web applications all while using a single code base. Facebook took it for a bit of a spin internally in the following years, before eventually releasing it to the public in early 2015.

## For apps big and small

Yes, Facebook's app is gigantic compared to almost everything else, but using one code base instead of two or more will still let you avoid multiplying the amount of work you need to do, even while working on the smallest project. On the technical side, to simplify it as much as possible, React Native interprets JavaScript written by developers and communicates it to native platforms via a bridge, using serialized data. You don't really have to bother yourself with that, as it all happens under the hood while it runs in the background, you can just focus on the code. If we’re talking about that it might be more convincing to just take a quick look at the basic advantages React Native provides:

* **code re-usability**: the main draw is using the same code for all platforms, making cross-platform development quicker and requiring much less work,
* **performance**: React Native runs almost as fast as native code and much faster than other JavaScript frameworks,
* **UI focus**: devs can easily create a simple to use and intuitive UI which is far more likely to attract users,
* **fast refresh**: you can run the app while updating it or while modding the UI and instantly see the changes in real time,
* **bustling community**: React Native not only enjoys support from Facebook, it's also open-source with a very large dev community and a multitude of third party libraries.

## React Native vs native development

That said, React Native despite its immense popularity, isn't 100% perfect and does have some drawbacks. While code is reusable cross-platform it still might need some tweaking for specific uses. You do get some handy components out of the box and you still have a ton of third party libraries in case you need some custom ones. However you might need a bit of help from a native developer to sort out some platform-specific kinks, especially for more complicated projects. Alternatively you’ll need to learn about those yourself which will contribute to the learning curve, which admittedly is not that steep in the case of React Native. However if the project is sufficiently complex you might ask yourself if sticking with React Native is really worth it vs. just opting for native development.

## Is it worth it?

When weighing the benefits, it really depends on what you’re working on and what you’re planning to work on in the future, because the choice as usual is not a no-brainer. For complex platform specific projects native development might still be better than custom fitting it to React Native. On the other hand if you’re looking to get into mobile app development without having to learn Swift for iOS and Kotlin for Android, React Native is probably the way to go. Down the road nothing will stop you from getting the hang of the intricacies of some native platforms for specific projects, while still being able to work on simpler mobile apps while you get there. To make it short React Native is a really good starting point, especially considering its popularity. If you’re still on the fence stay tuned and soon we’ll talk a bit more in depth about what’s new and how it compares to other frameworks.