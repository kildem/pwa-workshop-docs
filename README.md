### Workshop contents

- **Intro and setting up the environment**
- [What are Progressive Web Apps (PWA). The service worker API is the backbone of PWA functionality.](theory.md)
- [Step 0 - Classic web application](practice-step0.md)
- [Step 1 - App shell with a handmade service worker](practice-step1.md)
- [Step 2 - App shell with Workbox](practice-step2.md)
- [Step 3 - Runtime caching with Workbox](practice-step3.md)
- [Step 4 - Caching missing pieces with the Workbox recipes](practice-step4.md)
- [Step 5 - Improving app update flow](practice-step5.md)
- [Step 6 - Replaying requests made offline](practice-step6.md)
- [Step 7 - Making app installable](practice-step7.md)
- [Review of other APIs to build a native-like app](other-apis.md)

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

## Your trainer: Maxim Salnikov

<img src="https://github.com/webmaxru/pwa-workshop-docs/raw/main/images/maxim.salnikov.jpg" width="200">

_Developer Engagement Lead at Microsoft_

Maxim Salnikov is an Oslo-based cloud and web front-end geek with a strong passion for the developer community building. He architects and builds complex web applications since the end of the last century, and has extensive experience with all aspects of web platform focusing on the apps managing real-time data from IoT devices, and Progressive Web Apps. He is a Google Developer Expert in Web Technologies & IoT, and a former Microsoft MVP in Development Technologies.

Maxim is a founder and active contributor to two conferences: Mobile Era and ngVikings - Nordics’ main conferences for mobile and Angular developers respectively. Also, he leads Norway’s largest meetups dedicated to web front-end and mobile: Angular Oslo, Mobile Meetup, Oslo PWA, Framsia.

Maxim is passionate about sharing his web platform experience and knowledge with the community. He travels extensively for visiting developers events and speaking/training at conferences and meetups around the world.

Invite me to speak at your event using this form: http://bit.ly/maxim-salnikov-speaker-request

## Schedule

* 11:00 AM - 12:30 PM - Session 1
* 12:30 PM - 12:45 PM - 15 minutes break
* 12:45 - 2:15 PM - Session 2
* 2:15 - 2:45 PM - 30 minutes break
* 2:45 - 4:15 PM - Session 3
* 4:15 - 4:30 PM - 15 minutes break
* 4:30 - 6:00 PM - Session 4

## Content

### Session 1
* Setting up the environment
* What are Progressive Web Apps (PWA)
* The service worker API is the backbone of PWA functionality
* Step 0 - Classic web application
* Step 1 - App shell with a handmade service worker

### Session 2
* Step 2 - App shell with Workbox
* Step 3 - Runtime caching with Workbox
* Step 4 - Caching missing pieces with the Workbox recipes

### Session 3
* Step 5 - Improving app update flow
* Step 6 - Replaying requests made offline

### Session 4
* Step 7 - Making app installable
* Review of other APIs to build a native-like app
* Questions and answers

---

## Setting up the environment

### Tools and browsers

We need a PC or Mac with installed (latest stable versions):
- Git
- Node 
- NPM

Browsers (latest stable versions):
- Browsers Chrome and/or Edge, optionally - Firefox

Good to have:
- Canary versions of Chrome and/or Edge

### Front-end stack description

We will use a simple blog application written in Angular. Production builds will be provided for the each step, so there is no need to set up Angular infrastructure (but it’s possible to set up the full build, if you wish). We will run some simple commands using npm scripts.

### Backend stack description

We will use a hosted Ghost engine as a backend.

### Using Lighthouse - our main metric of app’s progressiveness

Lighthouse analyzes web apps and web pages, collecting modern performance metrics and insights on developer best practices.

https://github.com/GoogleChrome/lighthouse

There are two options:
- As of version 60 Chromium engine now has a built in lighthouse test which is accessible on the Audits tab of the developer tools. DevTools -> Lighthouse -> PWA -> Generate report
- CLI tool
```
npm install -g lighthouse
lighthouse https://airhorner.com --view
```

The `--view` parameter will open the resulting report in a new browser window.

Test some websites using Lighthouse:
- https://airhorner.com/
- https://smashingmagazine.com
- Your company’s website?

## Practical part

The practical part of the workshop consists of modernizing the front-end part of a web application from a "regular" one to a PWA. To make the project realistic, the application was built using of the popular front-end frameworks (Angular), but knowledge of this framework and its specific tools is not required: all the necessary builds will be provided. In addition, all the techniques, methods, practices studied in the workshop, and the code from the examples ia applicable to any web application. During the practical part, the following functionality will be added to the application:

- Offline readiness of the application shell
- Caching responses from API and CDN using appropriate strategies
- Interactive version upgrade process
- Preserving data submitted by the user in offline mode for auto-resending it to the backend after getting internet connectivity
- Installing the app on devices

## Next step
[What are Progressive Web Apps (PWA). The service worker API is the backbone of PWA functionality.](theory.md)
