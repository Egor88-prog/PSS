Кулинарная мастерская — вариант 6.
Лабораторная работа № 8: препроцессор Sass (синтаксис SCSS).

Команды выполняются из корня папки проекта.
Node.js и npm должны быть предварительно установлены.

Восстановление зависимостей (папка node_modules не поставляется):
    npm ci

Разовая сборка — создаёт styles.css в корне проекта:
    npm run build
    (то же самое: npx sass --no-source-map scss/styles.scss styles.css)

Режим наблюдения — пересобирает styles.css при каждом сохранении
исходников. Терминал должен оставаться открытым; остановка — Ctrl+C:
    npm run watch
    (то же самое: npx sass --watch --no-source-map scss/styles.scss:styles.css)

Исходники стилей лежат в папке scss:
    _tokens.scss       общие значения: цвета, отступы, радиусы
    _mixins.scss       миксины panel() и focus-ring()
    _base.scss         раскладка, типографика, списки, таблицы, сетки
    _components.scss   меню, ссылки, карточки, форма и их состояния
    _motion.scss       переходы, @keyframes, пауза, prefers-reduced-motion
    styles.scss        точка входа: @use "base"; @use "components"; @use "motion";

К HTML-страницам подключается готовый styles.css, а не исходники SCSS.
Изменения вносят только в файлы папки scss/: ручная правка styles.css
будет потеряна при следующей сборке.
