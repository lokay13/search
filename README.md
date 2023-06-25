# search

Пошук
Створіть власний фронтенд для пошуку Google, пошуку зображень Google і розширеного пошуку Google.

Передумови
Згадайте з лекції, що ми можемо створити HTML-форму за допомогою тегу <form> і можемо додати теги <input> для створення полів вводу для цієї форми. Пізніше в курсі ми побачимо, як писати вебпрограми, які можуть приймати дані форми на вхід. Для цього проєкту ми напишемо форми, які надсилають дані на реальний вебсервер, у цьому випадку – на Google.

Коли ви виконуєте пошук у Google, як, наприклад, коли вводите запит на домашній сторінці Google і натискаєте кнопку «Пошук Google», як працює цей запит? Спробуємо з’ясувати.

Перейдіть на сторінку google.com, введіть запит на зразок «Гарвард» у поле пошуку та натисніть кнопку «Пошук Google».

Як ви, мабуть, очікували, ви повинні побачити результати пошуку Google для слова «Гарвард». А тепер погляньте на URL-адресу. Починати слід з https://www.google.com/search, маршруту на вебсайті Google, який дозволяє здійснювати пошук. Але за маршрутом йде знак ?, за яким далі додаткова інформація.

Ці додаткові фрагменти інформації в URL-адресі відомі як рядок запиту. Рядок запиту складається з послідовності параметрів GET, де кожен параметр має ім'я та значення. Рядки запитів зазвичай мають формат:

field1=value1&field2=value2&field3=value3...
де знак = відокремлює ім'я параметра від його значення, а символ & відокремлює параметри один від одного. Ці параметри є способом для форм подавати інформацію на вебсервер, кодуючи дані форми у URL-адресі.

Погляньте на URL-адресу своєї сторінки результатів пошуку Google. Здається, існує досить багато параметрів, які використовує Google. Перегляньте URL-адресу (може бути корисно скопіювати / вставити її до текстового редактору) і переконайтеся, що ви можете знайти згадку про «Гарвард», наш запит.

Переглядаючи URL-адресу, ви побачите, що одним із параметрів GET в URL-адресі є q=Harvard. Це свідчить про те, що ім'я параметра, що відповідає пошуковому запиту Google, - q (ймовірно, скорочення від «query»).

Виявляється, хоча інші параметри надають корисні дані Google, для пошуку потрібен лише параметр q. Ви можете перевірити це самі, відвідавши https://www.google.com/search?q=Harvard, видаливши всі інші параметри. Ви повинні побачити ті самі результати Google!

Використовуючи цю інформацію, ми можемо фактично повторно створити фронтенд для домашньої сторінки Google. Вставте наведене нижче у файл HTML, який називається index.html, і відкрийте його у браузері.

<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Search</title>
    </head>
    <body>
        <form action="https://google.com/search">
            <input type="text" name="q">
            <input type="submit" value="Google Search">
        </form>
    </body>
</html>
Коли ви відкриєте цю сторінку в браузері, ви побачите (дуже просту) форму HTML. Введіть пошуковий запит, як «Гарвард», і натисніть «Пошук Google», і ви перейдете на сторінку результатів пошуку Google!

Як це працює? У цьому випадку атрибут action у form повідомляє браузеру, що коли форму подано, дані слід надсилати на https://google.com/search. А шляхом додавання поля input до форми, атрибут name якого був q, усе, що введе користувач в це поле, включається як параметр GET до URL-адреси.

Вашим завданням у цьому проєкті є створення власного фронтенду для пошуку Google, досліджуючи інтерфейс Google, щоб визначити, які параметри GET він очікує, та додавання необхідних HTML та CSS на ваш вебсайт.

З чого почати?
Завантажте код дистрибутива з https://cdn.cs50.net/web/2020/spring/projects/0/search.zip та розпакуйте його.
Умови завдання
Ваш вебсайт повинен відповідати таким вимогам.

Сторінки. Ваш вебсайт повинен мати принаймні три сторінки: одну для пошуку Google, одну для пошуку зображень Google і одну для розширеного пошуку Google.
На сторінці пошуку Google у верхньому правому куті сторінки повинні бути посилання для переходу до пошуку зображень або розширеного пошуку. На кожній з двох інших сторінок у верхньому правому куті має бути посилання для повернення до пошуку Google.
Текст запиту. На сторінці пошуку Google користувач повинен мати можливість ввести запит, натиснути кнопку «Пошук Google» і перейти до результатів пошуку Google для цієї сторінки.
Як і в Google, ваш рядок пошуку повинен бути відцентрований із закругленими кутами. Кнопка пошуку також повинна бути відцентрована та розташована під рядком пошуку.
Пошук зображень. На сторінці пошуку зображень Google користувач повинен мати можливість ввести запит, натиснути кнопку пошуку та перейти до результатів пошуку зображень Google для цієї сторінки.
Розширений пошук. На сторінці розширеного пошуку Google користувач повинен мати можливість вводити дані для наведених чотирьох полів (взято з власних параметрів розширеного пошуку Google)
Знайти сторінки із… «усіма цими словами»:”
Знайти сторінки з… «саме цим словом або фразою»:”
Знайти сторінки з… «будь-яким із цих слів»:
Знайти сторінки з… «жодне з цих слів»:
Зовнішній вигляд. Як і власна сторінка розширеного пошуку Google, чотири варіанти слід складати вертикально, а всі текстові поля слід вирівнювати за лівим краєм.
Відповідно до власного CSS Google, кнопка «Розширений пошук» повинна бути синьою з білим текстом. Після натискання кнопки «Розширений пошук» користувач повинен перейти на сторінку результатів пошуку для заданого запиту.
Пощастило. Додайте кнопку «Мені пощастить» на головну сторінку пошуку Google. Відповідно до власної поведінки Google, натискання цього посилання має перевести користувачів безпосередньо до першого результату пошуку Google для запиту, минаючи звичайну сторінку результатів.
Естетика. CSS, який ви пишете, повинен якнайкраще відповідати власній естетиці Google.
