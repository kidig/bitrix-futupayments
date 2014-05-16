cdbitrix-futupayments
===================

Bitrix-модуль для приёма оплаты с пластиковых карт через Futubank.com

Установка на сервер
===================

Скачайте и распакуйте архив: 

    https://github.com/Futubank/bitrix-futupayments/archive/master.zip

Скопируйте каталог futubank из архива в каталог

    /var/www/bitrix/modules/sale/payment

или, для Windows:

    C:\Program Files\BitrixEnvironment\www\bitrix\modules\sale\payment

Скопируйте файл futupayments.php в каталог 
   
   /var/www

...или, для Windows:

   C:\Program Files\BitrixEnvironment\www

Убедитесь, что по адресу

   http://вашсайт/futupayments.php

теперь показывается строчка «It works!»:

   ![success_url и fail_url](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/itworks.png)


Настройки в личном кабинете Futubank.com
========================================

Зайдите в личный кабинет http://secure.futubank.com, выберите свой магазин (или создайте новый) и перейдите в раздел «Уведомления».

Отметьте пункт «Уведомления с помощью POST-запросов» / «на выбранную страницу вашего сайта» и укажите там ссылку

    http://вашсайт/futupayments.php

![success_url и fail_url](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/cb.png)


Настройки на вашем сайте
========================

В панели администрирования вашего сайта на вкладке «Администрирование» выберите раздел:

    Магазин → Настройки → Платежные системы

и нажмите кнопку «Добавить платежную систему»:

![Добавить платежную систему](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/add-ps.png)

Заполните форму «Параметры платежной системы»:
   
   ![Параметры платёжной системы](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/ps-params.png)

   * название: Futubank.com
   * активность: отмечено
   * сортировка: 1
   * описание: «Оплата банковской картой через Futubank.com»

Нажимте кнопку «Применить» и перейдите на вкладку «Типы плательщиков» -> «Физическое лицо».
Заполните основные поля формы «Обработчик для типа плательщика»:

   ![Физическое лицо](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/ph1.png)

   * применяется для данного типа плательщика: отмечено
   * название: Futubank.com
   * обработчик: Futubank.com (futubank)
   * кодировка: utf-8

Чуть ниже, в разделе «Свойства обработчика» укажите merchant_id и secret_key:

   ![merchant_id и secret_key](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/ph2.png)

Эти значения уникальны для каждого магазина, посмотреть их можно в личном кабинете Futubank (https://secure.futubank.com) в разделе «Готовые модули»:

   ![merchant_id и secret_key](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/mods.png)

Можно указать адреса страниц, которые будут показываться в случае успешного и неуспешного платежа:

   ![success_url и fail_url](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/urls.png)

Не забудьте сохранить сделанные изменения:

   ![success_url и fail_url](http://raw.githubusercontent.com/Futubank/futubank/master/static/bitrix/save.png)

Теперь попробуйте создать заказ в магазине и оплатить его через Futubank.
