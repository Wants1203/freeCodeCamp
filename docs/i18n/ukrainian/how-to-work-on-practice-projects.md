# Робота над практичними проєктами

Для практичних проєктів ми використовуємо покроковий підхід, щоб кемпери вивчили основи. Проєкт складається з декількох файлів, які ми називаємо **кроками**. Ці файли називаються ідентифікаторами завдання, щоб уникнути проблем із перекладом. На жаль, через це важко знайти файл, пов’язаний з певним кроком.

Ми створили редактор завдань, який допомагає розв’язати цю проблему. Цей інструмент дозволяє орієнтуватись на доступні проєкти та кроки (за порядком). Існує також вбудований редактор коду, який можна використовувати для безпосередньої роботи з файлами.

## Використання редактора завдань

У цих інструкціях ви дізнаєтесь, як працювати над практичними проєктами за допомогою нашого редактора завдань.

### Запуск редактора

Щоб запустити редактор, переконайтесь, що знаходитесь у кореневому каталозі freeCodeCamp. Потім запустіть `pnpm run challenge-editor`, щоб запустити клієнта та API, який підтримує редактор.

Клієнт запуститься через порт `3300`, тому доступ можна отримати на `http://localhost:3300`. API запуститься через порт `3200`, щоб уникнути конфліктів з навчальним клієнтом та сервером. Це дозволить запустити програму freeCodeCamp одночасно з редактором, щоб ви могли перевірити свої зміни локально.

### Навігація по редактору

За замовчуванням ви побачите доступні `superblocks` — це сертифікації. Натисніть посилання сертифікації, над якою хочете працювати.

Ви перейдете до списку блоків. Це практичні проєкти. Натисніть посилання проєкту, над яким хочете працювати.

Ви перейдете до списку кроків проєкту. Якщо ви працюєте над наявним кроком, можна натиснути посилання кроку, щоб відкрити редактор. Якщо ви додаєте чи вилучаєте кроки, натисніть посилання `Use the step tools`, щоб перейти до інструментів для цього завдання.

### Редагування кроків

Якщо натиснути на крок, ви перейдете до редактора. Це базовий текстовий редактор, який пропонує підсвічування синтаксису.

Після того, як ви застосували зміни, натисніть кнопку `Save Changes`, щоб зберегти зміни. Ви отримаєте сповіщення браузера про те, що ваші зміни готові до внесення. Зауважте, що вам потрібно буде вручну використати `git` для зміни та внесення файлів — інструмент не зробить цього.

### Інструменти для кроків

Якщо натиснути посилання `Use the step tools`, ви перейдете до сторінки з інструментами кроку. Це дозволить додавати чи вилучати кроки проєкту.

#### Створення наступного кроку

Натисніть цю кнопку, щоб додати новий крок в кінці проєкту. У цьому кроці використовуватиметься код попереднього кроку як зерно.

#### Створення порожнього кроку

Введіть кількість кроків, які хочете додати. Потім натисніть кнопку, що створить задану кількість кроків в кінці проєкту.

#### Додавання кроку

Введіть номер кроку, який хочете додати. Потім натисніть кнопку `Insert Step`, щоб додати крок. Порядок наступних кроків буде змінено.

#### Видалення кроку

Введіть номер кроку, який хочете видалити. Потім натисніть кнопку `Delete Step`, щоб видалити крок. Номери наступних кроків автоматично оновляться.

#### Оновлення заголовків кроку

Використовуйте цей інструмент лише тоді, коли додали чи вилучили крок вручну. Цей інструмент змінить порядок номерів кроків.

## Використання скриптів вручну

Якщо ви хочете працювати над кроками вручну у локальному IDE, ви можете запустити скрипти керування кроками.

Папка `tools/challenge-helper-scripts` містить інструменти, які допоможуть зі створенням та обслуговуванням проєктноорієнтованої навчальної програми freeCodeCamp.

### Створіть новий проєкт

Запустіть `pnpm run create-project` у кореневому каталозі. Ця команда відкриє інтерфейс командного рядка, який допомагатиме. Після цього в англомовній навчальній програмі має з’явитися нове завдання, яке можна використовувати як перший крок проєкту. Наприклад, якщо ви створили проєкт під назвою `test-project` у сертифікації з адаптивного вебдизайну, завдання з’явиться у `curriculum/challenges/english/01-responsive-web-design/test-project`.

Якщо ви хочете створити нові кроки, наступні інструменти допоможуть.

### create-next-step

A one-off script that will automatically add the next step based on the last step in the project. The challenge seed code will use the previous step's challenge seed code.

#### Як запустити скрипт:

1. Перейдіть до каталогу проєкту.
2. Виконайте наступну команду:

```bash
pnpm run create-next-step
```

### create-empty-steps

A one-off script that automatically adds a specified number of steps. The challenge seed code for all steps created will be empty.

**Примітка:** цей скрипт також запускає [update-step-titles](#update-step-titles).

#### Як запустити скрипт:

1. Перейдіть до каталогу проєкту.
2. Виконайте наступну команду:

```bash
pnpm run create-empty-steps X # where X is the number of steps to create.
```

### insert-step

A one-off script that automatically adds a new step at a specified position, incrementing all subsequent steps (both their titles and in their meta.json). The challenge seed code will use the previous step's challenge seed code with the editable region markers (ERMs) removed.

**Примітка:** цей скрипт також запускає [update-step-titles](#update-step-titles).

#### Як запустити скрипт:

1. Перейдіть до каталогу проєкту.
2. Виконайте наступну команду:

```bash
pnpm run insert-step X # де X є місцем, куди потрібно вставити новий крок.
```

### delete-step

A one-off script that deletes an existing step, decrementing all subsequent steps (both their titles and in their meta.json)

**Примітка:** цей скрипт також запускає [update-step-titles](#update-step-titles).

#### Як запустити скрипт:

1. Перейдіть до каталогу проєкту.
2. Виконайте наступну команду:

```bash
pnpm run delete-step X # де X є номером кроку, який потрібно видалити.
```

### update-step-titles

A one-off script that automatically updates the frontmatter in a project's markdown files so that they are consistent with the project's meta.json. It ensures that each step's title (and dashedName) match the meta's challengeOrder.

#### Як запустити скрипт:

1. Перейдіть до каталогу проєкту.
2. Виконайте наступну команду:

```bash
pnpm run update-step-titles
```
