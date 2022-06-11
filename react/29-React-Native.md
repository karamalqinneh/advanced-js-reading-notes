## React Native

React Native is an open-source UI software framework created by Meta Platforms, Inc. It is used to develop applications for Android, Android TV, iOS, macOS,
tvOS, Web, Windows and UWP by enabling developers to use the React framework along with native platform capabilities

## Native Components

In Android development, you write views in Kotlin or Java; in iOS development, you use Swift or Objective-C. With React Native, you can invoke these views with JavaScript
using React components. At runtime, React Native creates the corresponding Android and iOS views for those components. Because React Native components are backed by the
same views as Android and iOS, React Native apps look, feel, and perform like any other apps. We call these platform-backed components Native Components.

React Native comes with a set of essential, ready-to-use Native Components you can use to start building your app today. These are React Native's Core Components.

- React Native also lets you build your own Native Components for Android and iOS to suit your app’s unique needs. We also have a thriving ecosystem of these
  community-contributed components. Check out Native Directory to find what the community has been creating.

## Core Components

React Native has many Core Components for everything from form controls to activity indicators. You can find them all documented in the API section. You will
mostly work with the following Core Components:
![image](https://user-images.githubusercontent.com/90922969/172328340-a1b0e545-38b8-4832-b54c-6a15f1f8cfcc.png)

## Implementation

The working principles of React Native are virtually identical to React except that React Native does not manipulate the DOM via the Virtual DOM. It runs in a background process (which interprets the JavaScript written by the developers) directly on the end-device and communicates with the native platform via serialized data over an asynchronous and batched bridge
React components wrap existing native code and interact with native APIs via React's declarative UI paradigm and JavaScript.
While React Native styling has a similar syntax to CSS, it does not use HTML or CSS.[20] Instead, messages from the JavaScript thread are used to manipulate native views. With React Native developers have to write native code in the languages of the aimed platform such as Java or Kotlin for Android, Objective-C or Swift for iOS, and C++/WinRT or C# for Windows 10.

Microsoft builds and maintains React Native for Windows and React Native for macOS.
