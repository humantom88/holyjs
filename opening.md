# Nov 08 (Восьмая конференция)
## Открытие конференции

Алексей федоров 23derevo

---

Hashtag: \#HOLYJS

--- 
## Следующие события:

7-8 дек. Mobius MSK

10-11 апр HolyJS Piter

23-24 июня Mobius

---

## Спонсоры:
1. ManyChat 
2. Raiffeisen Bank
3. Ростелеком
4. Контур (guides.kontur.ru)
5. Sberbank
6. Альфа-банк

---

## Statically Dynamic
The full spectrum of web page rendering

There's no silber bullet in software engineering

Essentioal difficulty vs Accidental dificalty

Essential is inherent to the problem, that we solving
Accidental is not inherent to the problem, we make it on our own

Next.js, Apollo project as a solvation to reduce the accidental complexity

Reduce the javascript amount that sould be delivered to client side

Frameworks not gonna be a silver bullet,

But meta-frameworks can be

Filesystem is first real API

pages/index.js -> mysite.com

pages/blog.js -> mysite.com/blog

1. zero-configuration start
2. simple program exploration
3. automatic routing
4. build-in code splitting

All these idas solve the problems of the accidental difficulty

benefits of each approach (fully-static, fully)

Static advangtages:
1. Cheap scaling
2. High availability
3. Reduced backend load
4. O(1) TTFB
5. All-or-nothing code rollouts
6. Very-high throughput
7. great security model
8. Failures containt to built

Static shortcomings:
1. lengthy build process
2. small changes trigger full rebuild
3. full pre-build intractable at >N pages
4. SEO Suffers unless 100% pre-built
5. Perf suffers unless 100% pre-built
6. Not dynamic

SSR advantages
1. Quick build process
2. Small changes are instant
3. infinite pages

SSR shortcomings
1. Duplicate business logic on server and client
2. Complex ops and maintenance (readiness proes, alerts, metrics)
3. Very expensive
4. Practically always single region
5. Prone to stability problems and memory leaks
6. High dependence on ad-hoc caching services for scaling
7. Increased security attack surface (Node.js)
8. Duplicate monitoring, tracing and exception-reporting in both server and client
9. Unstable and unpredictable TTFB
10. Failures are catastrophic (500 page)

---

JAMstack

J = Javascript,
A = API,
M = Markup

JAMstack advantages
(ZEIT)

1. All the benefits of static
2. Single error reporting surface
3. Single debugging story
4. Great local dev story
5. Plugs into site


Preloading + parallelism yields = great performance

Landing page of your company like headless CMS

Solution: combine static site generation and SSR

---

## Introducing Incremental static site generation (iSSG)

Next.js ***per-page rendering options***

iSSG advantages

+ Highly available (toleragtes backend downtime)
+ Always global (html files in CDN)
+ Always fast(pre-rendered / tolerates backend slowness)
+ Scales infinitely
+ Cheap

Most applications can be modeled fully statically

Static is the new Dynamic

iSSG is coming soon to Next.js canary
@zeithq + @rauchg

---

Questions:
