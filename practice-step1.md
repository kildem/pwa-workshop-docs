# Step 1 - App shell with a handmade service worker

We want all resources for our app to be cached by the service worker, and ensure they’re sent to the page without hitting the network on subsequent visits.

Service workers are very manual. They don’t provide any automation for accomplishing this goal, but they do provide a way for us to accomplish it ourselves.

:exclamation: In this step we only work with the files in `dist\prog-web-news` folder :exclamation:

1) Create `service-worker.js` file:

```javascript
const PRECACHE = "precache-v1";
const RUNTIME = "runtime";

const PRECACHE_URLS = [
  "index.html",
  "./",
  "main.34827f39578469476a05.js",
  "polyfills.25b2e0ae5a439ecc1193.js",
  "runtime.359d5ee4682f20e936e9.js",
  "styles.c2761edff7776e1e48a3.css",
  "assets/img/pwa-logo.png",
];

self.addEventListener("install", (event) => {
  console.log("[Service worker] Install event");
  event.waitUntil(
    caches.open(PRECACHE).then((cache) => cache.addAll(PRECACHE_URLS))
  );
});

self.addEventListener("activate", (event) => {
  console.log("[Service worker] Activate event");
  const currentCaches = [PRECACHE, RUNTIME];
  event.waitUntil(
    caches
      .keys()
      .then((cacheNames) => {
        return cacheNames.filter(
          (cacheName) => !currentCaches.includes(cacheName)
        );
      })
      .then((cachesToDelete) => {
        return Promise.all(
          cachesToDelete.map((cacheToDelete) => {
            return caches.delete(cacheToDelete);
          })
        );
      })
  );
});

self.addEventListener("fetch", (event) => {
  console.log("[Service worker] Fetch event for", event.request.url);

  // Assume that everything on app's origin is app shell
  if (event.request.url.startsWith(self.location.origin)) {
    event.respondWith(
      caches.match(event.request).then((cachedResponse) => {
        if (cachedResponse) {
          return cachedResponse;
        }
        return caches.open(PRECACHE).then((cache) => {
          return fetch(event.request).then((response) => {
            return cache.put(event.request, response.clone()).then(() => {
              return response;
            });
          });
        });
      })
    );
  } else {
    // Assume that everything outside app's origin is API or CDN
    event.respondWith(
      caches.match(event.request.clone()).then((response) => {
        return (
          response ||
          fetch(event.request.clone()).then((r2) => {
            return caches.open(RUNTIME).then((cache) => {
              cache.put(event.request.url, r2.clone());
              return r2.clone();
            });
          })
        );
      })
    );
  }
});

```

2) Add service worker registration code to `index.html`

```html
<script>
```
```javascript
// Feature detection
if ('serviceWorker' in navigator) {

  // Postponing service worker installation until all core resources were loaded
  window.addEventListener('load', () => {

    navigator.serviceWorker.register('/service-worker.js')
      .then((registration) => {

        console.log('[App] Service worker registration succeeded:', registration);

        // If updatefound is fired, it means that there's a new service worker being installed.
        registration.addEventListener('updatefound', () => {
          
          var installingWorker = registration.installing;
          console.log('[App] A new service worker is being installed:', installingWorker);

        });
      })
      .catch((error) => {
        console.log('[App] Service worker registration failed:', error);
      });

  });
} else {
  console.log('[App] Service workers are not supported.');
}
```
```html
</script>
```

To mimic version update do the following:
- Iterate number in `const PRECACHE = "precache-v1";` after `v`
- Add this line to `index.html` and also iterate number there
```html
<div style="position: absolute; top: 23px; right: 16px; z-index: 1; color: #fff">v2</div>
```
