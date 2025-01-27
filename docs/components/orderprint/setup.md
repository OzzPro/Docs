# Настройка для работы с компонентом магазина

По умолчанию OrderPrint настроен на работу с MiniShop2. Если на Вашем сайте используется Shopkeeper, для использования OrderPrint необходимо изменить системную настройку opr_type ("Магазин" в разделе "orderprint") на "shk". Кроме того многие плейсхолдеры станут недоступными а появятся другие, это сделано для максимально удобной работы с тем магазином к которому Вы привыкли, к примеру в шаблоне строки таблицы товаров для MS2 доступен плейсхолдер `[[+thumb]]`, которого просто нет в SHK, зато для него можно использовать ТВ image значение которой попадет в плейсхолдер `[[+tv_add.image]]`. Это значит что в шаблонах нужно будет заменить теги спецефичные для MS2 тегами SHK.

![Настройка для работы с компонентом магазина](https://file.modx.pro/files/d/3/0/d304fe6fba31836932c5078552067505.png)

## Документы

- название
- описание
- основной шаблон - имя чанка, который будет использоваться как шаблон всего документа
- шаблон строки таблицы товаров - имя чанка, который будет использоваться для вывода отдельного товара в таблицу со списком покупок в заказе, если не указать то таблица формироваться не будет
- доступен для пользователей - если установить ДА то пользователи получат доступ для того чтобы распечатать свои заказы в виде данного документа прямо из фронтэнда сайта.
- альбомная ориентация - ДА/НЕТ
- отступы - поля документа через запятую, начиная с верхнего.

![Документы - 1](https://file.modx.pro/files/b/1/1/b117448eccebd86514aa2777edd1aab6.png)

Вы можете создавать любое количество документов, все они будут доступны для использования сразу после сохранения.

Чтобы напечатать документ достаточно просто на вкладке "Заказы" кликнуть по интересующему Вас заказу правой кнопкой мыши и в выпадающем меню выбрать нужный документ.

![Документы - 2](https://file.modx.pro/files/3/c/3/3c3a98c4cdae9b9d6b5a2b67211b0b6b.png)

### Параметры

Помимо данных полученных из заказа и параметров системы в шаблонах документов Вы можете использовать также и дополнительные параметры OrderPrint-а. Это полезно если, к примеру, нужно выводить в документ данные, которых нет нигде в системе (ИНН, имя руководителя, имя курьера или название банка, всё что угодно).

Перейдя на вкладку "Параметры" Вы сможете управлять дополнительными параметрами, изменять, удалять, создавать сколько угодно новых. Каждый такой параметр имеет следующие поля:

- ключ - ключ параметра, подобно ключам системных настроек. Если создан параметр с ключом mycustomkey, его значение можно будет выводить в шаблонах документов так `[[+mycustomkey]]`
- значение
- описание

![Параметры](https://file.modx.pro/files/0/b/7/0b78713cb7d1faad3032a043ba2168d4.png)

### Вывод ссылок для печати во фронтэнде

Для того чтобы вывести ссылки пользователям сайта в компонент включен сниппет orderPrint. Доступны следующие параметры:

| Параметр    | По умолчанию                | Описание                                    |
| ----------- | --------------------------- | ------------------------------------------- |
| **tpl**     | `orderPrint.LinkTpl`        | имя чанка в который будут выводится ссылки. |
| **orderId** |                             | id заказа                                   |
| **docs**    | все доступные для фронтэнда | перечисленные через запятую id документов.  |
