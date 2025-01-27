# Установка и настройка

Начать пользоваться пакетом очень просто.

## Основная настройка

- После установки компонента, в бекенде нужно зайти либо на страницу компонента, либо на страницу товара, к которому хотим привязать купон и выбрать вкладку `Промо-коды` и создать промо-код.
- На странице вызова сниппета `msCart` вызвать сниппет `mspcForm` **обязательно некешированно**: `{'!mspcForm' | snippet}` или `[[!mspcForm]]`. Лучше всего вызывать в чанке вывода корзины, чтобы при отсутствии товаров в корзине поле ввода не отображалось. Можно несколько раз, например, до и после корзины.
- Чтобы цена, при применении купона в корзине, для каждого товара менялась динамически, надо сделать действия описанные ниже.

### Динамическая смена цены товара после применения купона

#### miniShop2 v2.4

1. В  чанке `tpl.msCart` вызов цены обрамить в селектор `span.price span`.

    То бишь, вместо:

    ```fenom
    <span>{$product.price}</span> {'ms2_frontend_currency' | lexicon}
    ```

    примерно так:

    ```fenom
    <span class="price"><span>{$product.price}</span> {'ms2_frontend_currency' | lexicon}</span>
    ```

2. Чуть ниже вызов старой (зачёркнутой) цены обрамить в селектор `span.old_price span`.

    Вместо:

    ```fenom
    {if $product.old_price?}
      <span class="old_price">{$product.old_price} {'ms2_frontend_currency' | lexicon}
    {/if}
    ```

    примерно так:

    ```fenom
    <span class="old_price" style="{if !$product.old_price}display:none;{/if}">
      <span>{$product.old_price}</span> {'ms2_frontend_currency' | lexicon}
    </span>
    ```

#### miniShop2 v2.2

1. В чанке `tpl.msCart.row` вызов цены обрамить в селектор `span.price span`:

    ```modx
    <span class="price"><span>[[+price]]</span> [[%ms2_frontend_currency]]</span>[[+old_price]]
    ```

2. В быстрый плейсхолдер `old_price` (это то, что в чанке `tpl.msCart.row` в самом низу) вызов старой (зачёркнутой) цены обрамить в селектор `span.old_price span`:

    ```modx
    <!--minishop2_old_price
    <span class="old_price"><span>[[+old_price]]</span> [[%ms2_frontend_currency]]</span>-->
    ```

### Вывод суммы скидки

[![](https://file.modx.pro/files/4/f/4/4f4ee223deb3b63c55574620e8c1795e.png)](https://file.modx.pro/files/4/f/4/4f4ee223deb3b63c55574620e8c1795e.png)

Можно вывести скидку по промо-коду в любом месте страницы, где вызывается сниппет `mspcForm`, используя конструкцию типа:

```modx
<div class="mspc_discount_amount" style="display: none;">
  Скидка по промо-коду: <span>0</span> [[%ms2_frontend_currency]]
</div>
```

::: warning
Для вывода и обновления суммы скидки используется селектор `span.mspc_discount_amount span`. Именно туда записывается сумма скидки без указания валюты.
:::
