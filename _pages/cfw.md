---
permalink: /cfw.html
title: Кастомные прошивки
author_profile: true
---
{% include toc title="Разделы" %}

В данный момент под кастомной прошивкой понимается официальная прошивка с рядом патчей, которые позволяют запускать не подписанный код и добавляют в прошивку ряд уникальных функций, например {% include abbr/lfs.txt abbr="LayeredFS" %}. Наиболее важными можно считать Atmosphere, из которой отпочковались RajNX, ReiNX и SX OS. Последняя, так же как и остальные, базируется на исходных кодах первой и является более дружественной к пользователю. Однако, она не бесплатная. 
Использование прошивки в её текущем виде совершенно легально (до тех пор, пока вы не начинаете пиратить, поскольку прошивка разворачивается в оперативной памяти приставки и не меняет никакие файлы официальной прошивки в хранилище. 

Установка кастомной прошивки может варьироваться в зависимости от неё самой и версии вашего текущего системного ПО

## Atmosphere
[Github](https://github.com/Atmosphere-NX/Atmosphere){:target="_blank"}

Atmosphere - open source проект. Она состоит из пяти основных модулей, каждый из которых наделён своими функциями:

* **Fusée** - загрузчик первого этапа. Он отвечает за запуск и проверку второго этапа (кастомный TrustZone) и package2 (ядро и системные модули), а так же за патчинг их по мере необходимости (**реализован**) 
* **Exosphère** - изменённый TrustZone, необходимый для запуска Secure Monitor (**реализован**)
* **Thermosphère** - модуль, обеспечивающий поддержку EmuNAND (**реализован**)
* **Stratosphère** - изменённые системные модули. Будет что-то типа Rosalina на 3DS, что позволит расширить возможности ядра и предоставит новые функции (**частично реализован**)
* **Troposphère** - патчи для реализации запланированных функций кастомной прошивки. Уровень взаимодействия с приложениями (**не реализован**)

Позволяет устанавливать игры в формате NSP, устанавливать к ним обновления, DLC. 

{% spoiler Плюсы %}
+ Бесплатная
+ Постоянно развивается 
+ Умеет запускать образы eShop-игр 
+ Поддерживает {% include abbr/lfs.txt abbr="LayeredFS" %}
+ Поддерживает {% include abbr/emunand.txt abbr="EmuNAND" %}, в том числе и переключение между несколькими
+ С открытым исходным кодом
+ Модульная архитектура (благодаря модулям осуществим разгон, например, и эмуляция amiibo)
+ Наиболее защищённая
+ Работает на всех версиях системного ПО
+ Умеет перезагружаться в hekate без проброса пейлоада (то есть после перезагрузки вы сразу попадаете в hekate или Atmosphere) и правильно выключаться 
{% endspoiler %}

{% spoiler Минусы %}
+ Не умеет монтировать XCI, но умеет устанавливать 
{% endspoiler %}

{% spoiler Установка Atmosphere %}

#### Что понадобится 

* Умение [вводить консоль в режим восстановления (RCM)](fusee-gelee#%D1%87%D0%B0%D1%81%D1%82%D1%8C-i---%D0%B2%D1%85%D0%BE%D0%B4-%D0%B2-rcm){:target="_blank"}
* Свежая версия {% include abbr/kefir_addr.txt %}

#### Инструкция

##### Подготовительные работы 

1. Выключите Switch и вставьте его карту памяти в ПК 
1. Установите `.7z`-архив {% include abbr/kefir_addr.txt %}, согласно инструкции в репозитории, если ещё не делали этого
1. `payload.bin` из `.7z`-архива {% include abbr/kefir_addr.txt %} - это {% include abbr/hekate.txt abbr="hekate" %}, этот пейлоад нужно будет пробрасывать при использовании [Fusée Gelée](fusee-gelee){:target="_blank"}. 
1. Вставьте карту в консоль

##### Запуск Atmosphere 
{% include inc/launch-cfw.txt %}

Если после входа в прошивку приставка не видит карту и требует обновить прошивку для её работы, либо просто зависает в чёрном экране после логотипа Nintendo, то на вашей приставке не установлены драйвера exFAT! Отформатируйте карту памяти в [FAT32](http://customfw.xyz/format_sd){: target="blank_"}. 
{: .notice--warning}

В {% include abbr/hekate.txt abbr="hekate" %} по-умолчанию настроен автозапуск. То есть при запуске приставки меню {% include abbr/hekate.txt abbr="hekate" %} не будет отображаться, а запустится сразу прошивка. Для перехода в меню {% include abbr/hekate.txt abbr="hekate" %} зажмите (VOL-) во время появления сплеш-скрина.
{: .notice--info}

{% endspoiler %}

{% spoiler Запуск Atmosphere %}
{% include inc/launch-cfw.txt %}

Если после входа в прошивку приставка не видит карту и требует обновить прошивку для её работы, либо просто зависает в чёрном экране после логотипа Nintendo, то на вашей приставке не установлены драйвера exFAT! Отформатируйте карту памяти в [FAT32](http://customfw.xyz/format_sd){: target="blank_"}. 
{: .notice--warning}

В {% include abbr/hekate.txt abbr="hekate" %} по-умолчанию настроен автозапуск. То есть при запуске приставки меню {% include abbr/hekate.txt abbr="hekate" %} не будет отображаться, а запустится сразу прошивка. Для перехода в меню {% include abbr/hekate.txt abbr="hekate" %} зажмите (VOL-) во время появления сплеш-скрина.
{: .notice--info}
{% endspoiler %}

___

## SX OS
[Официальный сайт](https://sx.xecuter.rocks/){:target="_blank"}

Коммерческая операционная система, созданная китайскими разработчиками на основе исходных кодов Atmosphere. Распространяется в двух комплектациях: 

* **SX OS Pro** - физический релиз. Включает в себя лицензию на ОС, замыкатель и {% include abbr/dongle.txt abbr="донгл" %}, с помощью которого можно запустить SX OS из режима восстановления автономно, то есть без использования ПК или смартфона. Разумеется, для каждого запуска требует наличия донгла в консоли. 

* **SX OS** - распространяется исключительно в виде лицензии. Для запуска требуется войти в RCM с помощью ПК или смартфона. 

Помимо платной версии есть ещё и бесплатная, дающая исключительно доступ к Homebrew. 

{% spoiler Плюсы %}
+ Умеет запускать образы eShop-игр 
+ Поддерживает {% include abbr/lfs.txt abbr="LayeredFS" %}
+ Поддерживает {% include abbr/emunand.txt abbr="EmuNAND" %}
+ Встроенный установщик NSP
+ Монтирование образов XCI
+ Встроенный HBL
+ Умеет устанавливать игры с USB-носителя и на USB-носитель 
+ Поддерживает читы
{% endspoiler %}

{% spoiler Минусы %}
+ Стоит денег 
+ Полностью закрытая
+ Не поддерживает работу с несколькими EmuNAND
+ В версии до 1.3 содержала в себе бриккод, шифрующий eMMC при попытке взлома прошивки. Сейчас его уже удалили, но осадок остался. 
+ Основана на коде Atmosphere, что нарушает лицензию последней (строго этический момент, на работу это, разумеется, не влияет)
+ Не поддерживает модули (благодаря модулям осуществим разгон, например, и эмуляция amiibo)
+ Редко обновляется
+ С новыми версиями системного ПО умеют работать **только** beta-версии прошивки
+ Не умеет правильно выключать приставку и перезагружаться в систему
	* Имеется ввиду, что после перезагрузки вам так же придётся прокидывать пейлоад, а после выключения приставка застрянет в [AutoRCM](autorcm){: target="blank_"}, либо снова включится
{% endspoiler %}

{% spoiler Установка SXOS %}
##### Подготовительные работы

1. Выключите Switch и вставьте его карту памяти в ПК 
1. Установите `.7z`-архив {% include abbr/kefir_addr.txt %}, согласно инструкции в репозитории, если ещё не делали этого
1. `payload.bin` из `.7z`-архива {% include abbr/kefir_addr.txt %} - это {% include abbr/hekate.txt abbr="hekate" %}, с её помощью мы будем запускать прошивку через [Fusée Gelée](fusee-gelee){:target="_blank"}. 
1. Вставьте карту в консоль

##### Первый запуск  и активация SX OS

При первом запуске прошивки на карте памяти будет создан уникальный для каждой консоли файл `license-request.dat` на основе которого будет сгенерирована лицензия. 
{: .notice--info}

Вам не нужно активировать или покупать лицензию для создания emunand!
{: .notice--warning}

{% include inc/launch-cfw.txt %}

Если после входа в прошивку приставка не видит карту и требует обновить прошивку для её работы, либо просто зависает в чёрном экране после логотипа Nintendo, то на вашей приставке не установлены драйвера exFAT!. Отформатируйте карту памяти в [формат FAT32](http://customfw.xyz/format_sd){: target="blank_"}. 
{: .notice--warning}

В {% include abbr/hekate.txt abbr="hekate" %} по-умолчанию настроен автозапуск. То есть при запуске приставки меню {% include abbr/hekate.txt abbr="hekate" %} не будет отображаться, а запустится сразу прошивка. Для перехода в меню {% include abbr/hekate.txt abbr="hekate" %} зажмите (VOL-) во время появления сплеш-скрина.
{: .notice--info}

1. Приставка должна загрузиться в загрузчик SX OS
	* Если загрузка зависла на белом экране, или в любом другом месте, перегрузите консоль, удерживая кнопку (POWER) 15 секунд и повторите запуск снова
1. Нажмите "**Boot Custom FW**"
1. Нажмите "**Continue**"
1. Вставьте карту памяти приставки в ПК
1. Перейдите на [сайт активации SX OS](https://sx.xecuter.rocks/sxos-license.html){:target="_blank"}
1. Нажмите кнопку "**Browse**" и выберите сгенерированный `license-request.dat`
1. Введите ключ активации
1. Нажмите "**Retrieve License**" и выберите в качестве места сохранения корень карты памяти приставки
1. Удалите файл `license-request.dat`
1. Верните карту памяти обратно в консоль
1. Нажмите "**Back**" -> "**Options**" -> "**Power Off**"
{% endspoiler %}

{% spoiler Запуск SXOS %}
#### Обычный запуск SX OS

{% include inc/launch-cfw.txt %}
1. Приставка должна загрузиться в SX OS (по умолчанию приставка грузится в EmuNAND, если он не отключён в загрузчике)
	* Если загрузка зависла на белом экране, или в любом другом месте, перегрузите консоль, удерживая кнопку (POWER) 15 секунд и повторите запуск снова
{% endspoiler %}

## Обратите внимание

Если вы запустили прошивку в {% include abbr/emunand.txt abbr="EmuNAND" %} в первый раз, не забудьте выполнить рекомендации по смене имени на "EmuNAND" и по смене темы на противоположную той, с которой вы загрузились, как это было описано в инструкции по созданию [EmuNAND](emunand){: target="blank_"}.
Если вы не уверены, что EmuNAND работает, просто перезагрузите приставку и убедитесь, что загрузился {% include abbr/sysnand.txt abbr="SysNAND" %}. На это будет указывать другая цветовая схема, а так же иное имя пользователя. 

___

[Закрыть страницу](javascript:window.close();)
{: .notice--success}