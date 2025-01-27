---
title: mscZone
description: Расчет стоимости доставки для minishop2
logo: https://modstore.pro/assets/extras/msczone/logo-lg.jpg
author: vgrish
modstore: https://modstore.pro/packages/delivery/msczone

dependencies: miniShop2
---

# mscZone

Компонент реализует расчет стоимости доставки по точкам доставки (зонам) в зависимости от величины тарифной ставки и свойства заказа (в комплекте работает с полем weight - вес заказа) для miniShop2.

## Конфигурация зон доставки

Дает возможность добавлять, редактировать любое кол-во зон доставки.

![Конфигурация зон доставки](https://file.modx.pro/files/c/3/e/c3e8d58b91f753edd4fc55b39b96784b.png)

- имя зоны
- описание зоны

## Список точек доставки

Дает возможность добавлять, редактировать любое кол-во точек доставки с привязкой к определенной зоне, а также возможность указать адрес и описание точки.

![Список точек доставки](https://file.modx.pro/files/6/6/7/667ae6ea4b705cf4ffec98b9d7f43066.png)

- наименование точки
- принадлежность к зоне
- адрес
- описание
- активность

## Конфигурация свойств

Дает возможность указать свойство заказа, а так же единицу измерения свойства.

![Конфигурация свойств](https://file.modx.pro/files/5/1/5/515e402f457356a4ec734fb7ee31af29.png)

## Тарифы по зонам

Дает возможность указать интервал значений свойств и стоимость доставки. Если указана стоимость за единицу значения, то к указанной стоимости доставки будет добавленна стоимость единицы значения.

![Тарифы по зонам](https://file.modx.pro/files/e/5/4/e549ae6d0ace8aebb2f545e1e6040930.png)

## Сниппет msOrderZone

Брат близнец - [msOrder][2]. Добавлено подключение кастомных скриптов и вывод сообщений.

## Сниппет msOrderSpot

Сниппет для вывода списка точек доставки.

![Сниппет msOrderSpot](https://file.modx.pro/files/7/7/c/77cc20d260821a00a0eaa2ac111acd2c.png)

### В miniShop2 :: Настройки :: Варианты доставки

- Активировать вариант доставки
- Назначить необходимые варианты оплаты

### Настройки системы :: miniShop2

- Класс обработчик заказа - `mscdOrderHandler`

## Необходимо

Для правильного расчета стоимости доставки товара

- Каждому товару задать вес

[2]: /components/minishop2/snippets/msorder
