# Тарас Иванов (Как мы в 4 раза ускорили мобильную версию ВКонтакте)

Первая версия ВК работала на WAP

Сейчас это 6 млн пользователей в сутки, PWA версия.
Единый бэкенд
React + VKUI (OpenSource)

Платформа росла быстрее, чем оптимизировалась

До улучшения
Время отрисовки страницы 75% перцентиля была не менее 8 сек.

Производительность сайта сейчас 2,5 сек. Web Vitals (попасть в зеленую зону)

Web Vitals - это концепция гугла (набор метрик, которые позволяют объективно определить производительность сайта)
1) TTFB (Time To First Byte) # Белый экран
2) FCP (First Content) время до того, как на экране появится хоть что-нибудь | Например появилась только шапка
3) LCP () время до того, как на экране появится полезный контент | Страничка с активными элементами

Как измерить:
Lighthouse, Performance | Используется только для дебага
Либо пакет npm web-vitals (~3Kb) (обертка над new PerformanceObserver) | Используется в runtime

# Как повлиять на эти метрики?

Убрать все блокирующие запросы
Заинлайнитть CSS чтобы отрисовать лэйаут
Перенести верстку лейаута в самый верх страницы
Браузеру будет достаточно первого чанка HTML, чтобы отрисовать страницу

rel-"preload" //css-om дерево начнет строиться раньше

# Как это делали в VK

- Настраиваем сборщик
- Тришейкаем все, что нужно
- По возможности нарезаем код на бандлы и подключаем их по необходимости
=== Настройка сборщика webpack (ускорил рендер страницы на 3 секунды)
- Избавились от дублей кода
- Early Hints (обновление от Google), позволяет начать загружать assets до того, как от сервера пришел основной ответ (200)
Можно передать запрос с заголовком 103, чтобы браузер начал раньше скачивать assets
- dns-prefetch и серверные заголовки early-hints
- StaticManager (генерация Inline CSS)
 - отложить исполнение inline-кода после загрузки всех JS-файлов
 - onLoad-событие не подходит
 - Нужен свой механизм для отслеживания готовности страницы StaticManager

StaticManager позволяет откладывать загрузку скриптов
При этом был использован Proxy, который откладывал пользовательские события в очередь и выполнял их в порядке очереди после загрузки всего приложения
как результат - сокращение времени на 21-27% в разных сервисах

=== Другое решение 
Critical Path
Рендерить страницу целиком, не скачивая CSS-бандлы
А в шапку inline-css стили, независимо от содержания страницы

- Вычисляем список всех минимально необходимых CSS-правилв
- Бэкенд просел на 2.5%, но фронт выиграл на 3 - 3.5%

Полностью избавились от блокирующих запросов

А что насчет пользовательских событий
Вешаем на все активные действия pointer-events: none;
Время такой блокировки будет несущественно маленьким и незаметным для пользователя

Tools:

WebPageTest, позволит провести эксперименты не модифицируя код
Повесить defer на все скрипты