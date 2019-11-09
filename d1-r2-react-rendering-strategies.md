# React rendering strategies
## Get the most out of performance keep bots happy
---
Miguel Angel Duran @midudev, youtube.com/midudev
 
Enabler frontend at Adevinta

fotocasa app

---

15 seconds to interactivity at the beginning

performance score growth from 19 to 68 percent 

How do they achieved this?

Quick recap
+ Server Side Rendering (SSR) (Denied, low time to Interactivity)
+ Static Rendering (Next.js, Gatsby) (Deined, not enough flexibility)
+ Client Side Rendering (CSR) (Denied, low TTFB)
+ SSR + CSR (Accepted)

SSR with (re)hydration

React: ReactDOM.hydrate()
Vue: app.$mount('#root')

TTFB - Time To First Byte
SEO - Search Engine Optimization
TTI - Time to interactive

Hydration is god, but i still want to
+ SEO
+ Flexibility
+ User Experience (UX)
+ Developer Experience (DX)

---

## React rendering strategies

Dynamic Rendering
+ by route
+ by components

----
At route level:
* if client is a boot - prerender to the bot a full page
* if normal client - minimal HTML first
---

- Fast TTFB
- Hydration data is gone
- Only changes on the server side

- Client Side Rendering for user
- Bad first paint
- Userful technique for perf experiments
- free resources from your server

---

Does Yandex/Google like it?

---

At component level:
```
<DynamicRendering userAgent={universalUserAgent}>
    {isBot ? children : typeof window !== 'undefined' ? <LazyContent>children></LazyContent>}
</DynamicRendering>
```

If it is a bot - make it on server
If it is a client - make it on client with lazy loading

---

***if you want to be crawled faster - use SSR***

## Static rendering Demo
### You lose interactivity

So it's the best way when you sure that you don't need interactivity

npm i react-static-content

DymanicRendering at component level + Static Rendering

ProgressiveHydrationUsage
// photo

---
### Libraries:

vue-lazy-hydration

React:
react-preredered-component,
react-progressive-hydration
