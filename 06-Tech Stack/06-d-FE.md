# Front-end technology

## Web apps

- Have web-based front end which means we are going to use a combination of HTML, JavaScript and CSS.

## Angular and React 

- popularity.
  - in Google Trends, they are quite similar in popularity. Looking at stackoverflow.com, the numbers are actually quite close.

- capabilities.
  - Angular is a full-blown framework with a full set of capabilities, front and framework we need, such as data binding, state management, routing services, and lots more. Learning Angular can take time and it won't come easy even to developers with a lot of experience in web development. 
  - React, on the other hand, is more libraries than a full-featured framework. It focuses on the user interface side and is great at it. If other capabilities are needed then separate libraries should be used.React learning curve is much shorter and web developers can get up to speed with it in a matter of days while Angular training can take a few weeks, if not more.

## mobile apps

- Native apps
  - as the name suggests, use the native development platform for each mobile platform. For example, native iPhone development can be done using Objective-C or the Swift language with the Xcode development tool and using the iOS SDK. Android apps on the other hand, are developed mainly with Java, using Android Studio and the Android SDK. IOS's native apps environment is completely different from the Android one and you will have to have developers that expertise in each one of those environments. On the other hand, native apps offer full access to other phones capabilities including camera accelerometer, bluetooth file system, texts, and more. You are not limited in any aspect and you can take advantage of any feature you would like. In addition, native apps are very responsive and will offer the best user experience.

- Hybrid apps 
  - are the complete opposite of native apps. Hybrid apps provide thin native wrapper usually with tools such as phonegap, and in it, you will find a regular webpage, complete with HTML, JavaScript and CSS. You can think of hybrid apps as a glorified browser with limited phone capabilities but it's still a webpage and requires internet connectivity. Accessing phone capabilities such as accelerometer or camera can be a challenge with hybrid apps and there are a lot of limitations. In addition, hybrid apps provide inferior user experience compared to native apps and the graphics performance is limited.
  - In recent years, a new standard emerged called Progressive Web Apps or PWA. This standard allows hybrid apps to behave much more like native apps with offline capabilities, improve the hardware access and more. The PWA standout look quite promising and you should definitely keep an eye on it but it's still not mature enough. Apple added support for PWA in iPhone only in iOS version 11.3 and even in this version, it's still limited and not on par with Android support. So, it's definitely worth looking into but perhaps too early to actually use it. The biggest advantage of hybrid apps lies in the development time, aside from the native wrapper which do require a bit of learning,everything else is a regular web development. If your team knows how to develop web apps, they will know how to develop hybrid apps. It's that easy.

- cross platform apps
  - The cross platform approach works like this. The development is done in a specialized environment not linked directly to any of the mobile platforms. The leading cross platform environments today are Xamarin and React native. In Xamarin, you will develop in C Sharp using Visual Studio, while in React native, the development is done with JavaScript, using one of the many IDs supporting React native. After the development is done, you compile the application and the result is the native app for the selected platform. You will be able to compile the app for iOS and for Android and get native apps for both of them without writing a single line of Java or object. So, pro of using this approach are clear, we write the code once, it runs on both platforms as native apps.

  - There is usually a gap in supporting latest capabilities of the native operating system and the course platform tools always play catch-up with the various mobile platforms.
  - cross platform apps do not work well with heavy graphics.
  - for some scenarios, you will still have to resort to native programming especially when accessing specific sensors.

## desktop

- a desktop application, which will run on a PC, most chances are you are targeting Windows.

- WinForms 
  - is the oldest technology, introduced in 2001, together with (indistinct) introduction. It's similar in concepts to all the platforms, such as VB6, and is quite limited in its graphic capabilities. For example, try to implement rounded corners to a button. It's possible, but oh boy, it's so hard. On the other hand, developing in WinForms is quite easy and the learning curve is short.

- WPF
  - introduced in 2006, improve the situation dramatically.
  - It offers full control on the visuals and give complete freedom to visual designers. 
  - You literally can do whatever you want, but, and there is always a but, it's much more complicated than WinForms. 
  - In order to use WPF, you will have to learn new language, Xaml, which similar to HTML functions as a markup language to the user interface. Xaml is a very rich markup language and it's very easy to get lost in it. 

- UWP or Universal Windows Platform.

  - UWP is the effort done by Microsoft to unify all its screens, like PC, Xbox, Windows Form, Surface and more, to support a single UI platform. The result of this effort is UWP, which is quite similar to WPF, but with important differences.
    - it runs in a sandbox, meaning it does not have full access to all the operating system capabilities, similar to hybrid apps in mobile.
    - it runs on all Windows-based screen. So, if you want to develop an app for Windows and Xbox, that's the way to go.
    - it's much less mature than WPF.