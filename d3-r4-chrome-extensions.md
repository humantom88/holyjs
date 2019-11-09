#  Я заберу у тебя все данные и ты об этом даже не узнаешь. Я — браузерное расширение

HeadHunter

Доступ плагина к сайту дает запрашивает разрашение к сайту

- Первый пермишен Tabs and ActiveTab может запустить все что угодно, и исполнять кастомный код
- Debugger (Chrome Devtools Protocol) может регулировать поведение пользователя на странице
- Proxy and WebRequest очень много плагинов включают доступ к настройкам прокси браузера и пустить в обход
- All_urls
- Remove BrowsingData - подчищает/читает историю браузера
- Site Access - переключить на On Click, чтобы не следил за тобой
---
- background scripts
- последняя часть манифеста - content-script.js - позволяет скачать код с удаленного сервера и его исполнить

Content Scripts
- имеет свой environment (isolated world), имеет доступ к дом, кукам, стораджу, пермишенам 
- не имеет доступа к JS нашей страницы, а JS нашей страницы не имеет доступа к JS content-script'а
- поток исполнения

chrome.runtime.sendMessage

Векторы атаки
- background-scripts
- content-scripts
ущерб веб-сайтам
вычислительным ресурсам

С этим вообще ничего не сделать

FastProxy майнит криптовалюту за ваш счет
friGate3 proxy helper

ContentScripts не могут
- фейколвые страницы
- тело ответа 
- service worker

Защита от атаки
- contentsecuritypolicy (не защищает на уровне inline-script в хроме, но работает в Mozilla)

whitelist - при сборке сложить все стили в один json и отправить на клиента
все, что не в whitelist отправляем в аналитику

хащита
```js
// proxify
error.stack.includes('anonymous')
```

Проксировать
- Document API
- Post API
