В данном прооекте приведён пример разработки Telegram-бота Афоня, в котором будет реализован следующий функционал:
- Бот возвращает цену на определённое количество валюты (евро, доллар или рубль).
- При написании бота используется библиотека pytelegrambotapi.
- Человек должен отправить сообщение боту в виде <имя валюты, цену которой он хочет узнать> <имя валюты, в которой надо узнать цену первой валюты> <количество первой валюты>.
- При вводе команды /start или /help пользователю выводятся инструкции по применению бота.
- При вводе команды /values должна выводиться информация о всех доступных валютах в читаемом виде.
- Для получения курса валют необходимо использовать API и отправлять к нему запросы с помощью библиотеки Requests. API использовался из информационного портала Cryptocompare.
- Для парсинга полученных ответов используется библиотека JSON.
- При ошибке пользователя (например, введена неправильная или несуществующая валюта или неправильно введено число) вызывать собственно написанное исключение APIException с текстом пояснения ошибки.
- Текст любой ошибки с указанием типа ошибки должен отправляться пользователю в сообщения.
Для отправки запросов к API описать класс со статическим методом get_price(), который принимает три аргумента и возвращает нужную сумму в валюте:
- имя валюты, цену на которую надо узнать, — base;
- имя валюты, цену в которой надо узнать, — quote; 
- количество переводимой валюты — amount.
- Токен Telegram-бота храниться в специальном конфиге ( использовуется .py файл).
- Все классы спрятаны в файле extensions.py.
