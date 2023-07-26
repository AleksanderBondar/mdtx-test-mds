---
author: src/data/forestry/content/authors/michal.md
first_category: React Native
second_category: Flutter
third_category: Mobile
feature_image: "/uploads/rn_flutter.png"
createdAt: 2022-02-21T18:00:00.000+00:00
title: Hybrid development, React Native or Flutter?
short_description: React vs Flutter an up to date framework comparison

---
In terms of key decisions to make when thinking about app development the first one is to decide on either hybrid or native app development. Both are very popular with some well known native apps like WhatsApp and Spotify and hybrid apps including the likes of Instagram and Uber. Both approaches also have their pros and cons and depending on the circumstances each can be the right one to pick. While that choice will probably require quite a bit of brainstorming and figuring out the goals and aims of the product, let's look at what lies ahead if you decide on hybrid development.

## Flutter vs React Native

While not the only frameworks you can choose from, Flutter and React Native are the two leading platforms, so the simple decision is to turn to one of them. Both are created by tech giants, Facebook released React Native in March of 2015 and Google released Flutter in April of 2018. React Native is more widely adopted as it was released earlier, but Flutter has been gaining popularity and has recently taken the top spot becoming the most popular framework. Similarly for the size of both communities whether you’re going by Stack Overflow, GitHub or dev.to Flutter is catching up despite React Native having a 3 year head start. For a while it was basically a choice between an established tool and a fresh solution that’s gaining popularity, but now they’re just two major frameworks each with its own advantages.

## The ins and outs

First let’s take a look at some technical aspects, not in some very detailed way but just to get an idea on what each of them aims to do best. Each framework differs quite a bit in how it is constructed and how it works and that in turn means either a bit of a learning curve or some digging for community made solutions:

* **language**: React Native uses widely known JavaScript, Flutter uses Dart which is a custom object oriented language made by Google. While this might seem like React Native is the easy pick here Dart might be preferable as it should be very intuitive for those familiar with object oriented programming.
* **libraries/components**: Flutter relies on built-in libraries, React Native relies on third party libraries. This again comes down to preference, one has more of a starter toolkit the other offers you a buffet of user provided solutions, which you’ll have to find and pick yourself.
* **architecture**: Flutter uses a layered architecture of widgets while React Native uses a bridge between the Native and JavaScript threads. In short this means that Flutter is geared towards gradual app building via small and simple components while React Native makes more use of native functions, but can increase the size of the app which in turn can create some performance issues.

Some key differences are already apparent, React Native is more of a customizable tool that you should fit to what you need and Flutter aims to be more of an out of the box tool which gets you everything you need right off the bat. To further drive that point let’s take a look at some details on ease of use.

* **testing**: React Native offers no built in testing functions, you’ll need third party apps like Appium or Jest. Flutter offers a number of features for testing units, widgets and integrations.
* **documentation**: React Native has extensive documentation, however it focuses on helping those already familiar with JavaScript and some app development practices. Flutter has robust documentation with detailed video tutorials and graphics which will help you start from scratch and features like debugger and Flutter inspector which offer additional help. Little wonder since JavaScript is way more widely adopted than Dart but still an advantage if you’re starting out.
* **performance**: though this is a hotly debated topic, the basic fact is Flutter is faster and consistently runs at 60 frames per second. React Native does experience some issues and can be a bit slower, the best evidence for that is the existence of popular performance improving third party apps like Proguard.
* **complex projects**: React Native can be used even for more complex apps, but you’ll likely need to implement at least some bits of native development in relation to some kinks of the particular platforms. Flutter and its Dart are still fairly new and focus on simpler and faster development so they might lack what is needed for more complex or niche projects and using it for those wouldn't make much sense.

## Community driven vs out-of-the-box

I think the differences in both approaches are now quite clear and as usual the decision comes down to circumstances and personal preference. React Native focuses on providing developers with a good base and a variety of (often third party) tools which you can pick and choose from to get exactly what you need for your app. Relying on dev experience and community provided solutions makes sense since JavaScript is so widely adopted and those who know it and start using the framework will know exactly where to look for what they need. Flutter on the other hand has some learning curve since Dart is pretty new and not nearly as widely adopted, but throws in a ton of help to make it easier to get a hang of everything. It also focuses on faster time-to-market, better performance and more of a one size fits all approach to development. Any dev either familiar with Dart or object oriented programming or with the time to learn it will definitely find it worthwhile even if only for working on simpler projects or MVP applications and it's in no means limited to just that.