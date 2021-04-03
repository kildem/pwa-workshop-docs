# PWA Workshop, 2021 edition

The web platform is versatile, capable, and can go far beyond the browser tab while keeping its open and universal nature. We call “progressive” the web apps built using the latest browser APIs to achieve a new level of user experience. In this framework-agnostic workshop, we’ll convert a “classic” web application to progressive using Workbox 6 - the latest version of the service worker automation library. So you can do the same with an app you or your company is developing now!

### During this hands-on task-based training you will learn about:

* Progressive Web App concept pillars
* Service Worker API fundamentals
* Current platforms' PWA support (and workarounds when needed)
* Workbox library - an industry-standard in the automation of network-related PWA tasks

### On the practical side, every participant will build an app which is:

* Installable on all modern desktop and mobile operating systems
* Offline-ready: the app itself, smart caching strategies for the data it consumes, and network-resilient data sending
* Ready for being extended by the next PWA features coming to the web
* Following the modern web development flows for building a service worker
* Also, I share lots of practical tips & tricks, both technical and UX, review real-life PWA examples, explain how to avoid common pitfalls, and how to deal with edge cases.

### Expected level:

* Basic knowledge of JavaScript is required
* The knowledge of any framework(s) is not required

# Let's start!

## Schedule

* 11:00 AM - 12:30 PM - 1.5 hours Session 1
* 12:30 PM - 12:45 PM - 15 minutes break
* 12:45 - 2:15 PM - 1.5 hours Session 2
* 2:15 - 2:45 PM - 30 minutes break
* 2:45 - 4:15 PM - 1.5 hours Session 3
* 4:15 - 4:30 PM - 15 minutes break
* 4:30 - 6:00 PM - 1.5 hours Session 4

## Content

### 1. What are Progressive Web Apps (PWA)

Putting aside the marketing component of this popular term, let's look at the technical details: what exactly makes an application progressive, and why PWA can be a new era in the development of the web.

- Prerequisites for the occurrence
- Formal definition
- Benefits for users and developers
- Opportunities and installation of a web application are the two main vectors of PWA development
- Current state of the art with support across platforms, operating systems, and browsers


### 2. The service worker API is the backbone of PWA functionality

Most of the capabilities of progressive web applications are implemented using the Service Worker API. To understand what exactly we will automate using Workbox, we will study the basic ideas of this API and write a service worker ourselves.

- Similarities and differences with other browser workers
- Service worker life cycle
- Main events
- Registration in the application
- Debugging in the browser
- An example of a naive implementation of shell caching for offline work
- Difficulties to be solved and details to be considered before deploying a service worker to production


### 3. Workbox - automation of network tasks in PWA

After getting acquainted with the API of the service worker, we realized that to implement even the basic offline readiness of the application, a fairly wide range of knowledge and skills of working with service workers and not only is required. The Workbox library provides a comfortable abstraction layer for automating common network tasks for service workers.

- Functionality and construction principle of Workbox
- Choice of tools
- Offline readiness of an application in a service worker using Workbox methods
- Integration with application build
- Runtime caching, strategies and plugins
- Recipes - the next level of abstraction in Workbox 6

### 4. Advanced techniques for using Workbox

The Workbox library allows you to extend the service worker and PWA as a whole both in width, adding functionality beyond caching, and in depth, fine-tuning the behavior of the base modules.

- Workbox-window module for registering a service worker in an application
- Online app version update
- Background sync
- Expanding functionality with our own plugins and strategies

### 5. Push notifications

PWA is not only offline readiness and optimal work with network requests, but also the ability to deliver information directly to users' devices at any time in the form of push notifications.

- Required components and life of notification from registration to delivery to the device
- Handling the push event in the service worker
- Request permission to receive notifications in the app
- Best Practices for Successful Subscriptions

### 6. Installing Apps on Devices

To give our web application "official" PWA status, we need to add one more feature - the ability to install on users' devices.

- Web Manifest: Tasks, BOM
- Tools for generating web manifest and graphic assets
- Connecting to the app and testing
- Different approaches to help with installation in different browsers
- Placing PWAs in App Stores

### 7. Overview of other APIs in the service worker and PWA family

We've covered the most basic and commonly used features that can dramatically improve the user experience. But this is far from a complete set of APIs and specifications from the ever-growing family of PWA capabilities of the web platform. For the sake of completeness, consider some of them.

- Background download
- Periodic background sync
- Registering file types
- File system access
- Access to hardware capabilities

### Practical part

The practical part of the course consists of modernizing the front-end part of a web application from a "regular" one to a PWA. To make the project realistic, the application will be built on one of the popular front-end frameworks, but knowledge of this framework and its specific tools will not be required: all the necessary assemblies will be provided. In addition, all the techniques, methods, practices studied in the course, and the code from the examples will be applicable to any web application. During the course, the following functionality will be added to the application:

- Offline readiness of the application shell
- Interactive version upgrade process
- Caching responses from API and CDN using appropriate strategies
- Installing the app on devices
- Configuring and sending push notifications
