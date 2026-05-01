// Service Worker básico para permitir a instalação como PWA
const CACHE_NAME = 'cko-audit-v1';
const ASSETS = [
  './',
  './index.html',
  './manifest.json'
];

// Instala o service worker e guarda os ficheiros essenciais em cache
self.addEventListener('install', (event) => {
  event.waitUntil(
    caches.open(CACHE_NAME).then((cache) => {
      return cache.addAll(ASSETS);
    })
  );
});

// Responde com cache quando estiver offline
self.addEventListener('fetch', (event) => {
  event.respondWith(
    caches.match(event.request).then((response) => {
      return response || fetch(event.request);
    })
  );
});
