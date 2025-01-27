# Статусы

## Создать / Изменеть статус

Статус можно создать для класса [контент][4], [клиент][6], [подписка][7]

![Создать / Изменеть статус](https://file.modx.pro/files/c/b/3/cb3ecdc9d4d1213b6257ffeb778674f3.png)

Для создании статусы необходимо задать название и выбрать класс. Указать флаг активности и разрешения.
Дефолтные статусы:

- `новый` - задается при создании
- `активен` - характеризует активность
- `неактивен` - характеризует неактивность

Возможно создание статусов для реализации своей логики работы компонента.
Наличие разрешающих статусов у вышеперечисленных сущностей разрешает, в противном случае запрещает доступ к контенту.

## Смена статуса

Сменить статус можно из админки сайта, либо задействовав какой либо обработчик.
Пример автоматической смены статусов через `cron` можно посмотреть в папке `core/components/payandsee/cron/`, файлах:

- `{1.php}` - выборка разрешающих **подписок** сроком действия менее 3-х дней и перевод их в статус **Скоро неАктивна**
- `{2.php}` - выборка разрешающих **просроченных подписок** и перевод их в статус **неактивна**

[4]: /components/payandsee/interface/content
[6]: /components/payandsee/interface/clients
[7]: /components/payandsee/interface/subscriptions
