# Гайд по сокету LGA3647

 ![](https://github.com/ThinkPadThink/Guide3647/blob/master/XeonPlatinum.png?raw=true)
 
*Специально для Зионотреда на борде 2ch.hk/hw*

*Для написания этого гайда использовались различные источники информации.*

*__При копировании информации обязательно указывайте оригинальный источник.__* 

*Если у вас есть что добавить можете воспользоваться __Pull Request__  и я это тогда добавлю в гайд. Хуйцы и прочее я конечно же добавлять не буду.*



**Описание:**

Сокет чисто серверный и для рабочих станций. Ну за исключением Xeon W. Интересен только тем что инженерники(ES и QS) дешёвые. 

# Процессоры:

# Skylake-SP:

Существуют инженерные степпинги (ES), QS, Final OEM и Final Retail.

**ВНИМАНИЕ, не рекомендую приобретать процессоры с шиной Omni-Path, они не совместимы со многими материнскими платами(физически не установить), имеют дохуя гемора и шина не поддерживается уже самой Intel.**

**Внимание 2:** про более ранние степпинги мне ничего не известно.

## ES2 Stepping (A2/B0/L0)

Это инженерный степпинг процессоров, в CPU-Z/HWInfo64/Aida64 нормально они не определяются, а примерно так **Genuine Intel CPU 0000**. Xeon Gold/Silver/Bronze в CPU-Z могут распозноваться вообще как Core X Series под сокет 2066, причём как QS. 

По ES2 расклад такой: работают только на платах SuperMicro X11 (не все платы поддерживают и со старыми биосами 1.0 и 2.0 либо свежим 3.0 но модифицированным) и в брендовых серверах и рабочих станциях(но это не точно, инфа двоякая) Hewlet-Packard Enterprise (HPE) Для некоторых процессоров (например для Xeon Gold 5117F) требуется биос 1.01, на 1.10 уже не работают. Важно, для ASUS C621E SAGE, серверных плат Z11 серии и для Supermicro X11DPi-N есть модбиос который поддерживает большинство ES2 B0 цпу. Поддержка: QL1F QL1G QL1H QL1J QL1K QL1L QL1M QL27 QLH0 QLH2 QLQ9, вероятнее всего это многие ES2 Xeon Gold/Silver/Bronze цпу. Не поддерживается QL2K aka Xeon Platinum. 

Основная таблица по Xeon Skylake-SP ES 
 ![](https://github.com/ThinkPadThink/Guide3647/blob/master/xeon%20skylake%20es.jpg?raw=true)
 
 Дополнительная таблица по Xeon Skylake-SP ES 
 ![](https://github.com/ThinkPadThink/Guide3647/blob/master/xeon%20bronze%20es.jpg?raw=true)

## QS Stepping (H0/M0/U0)

Это предрелизные образцы процессоров, чаще всего уже нормально определяются в CPU-Z/HWinfo64/Aida64 но имеют преписку ES, по большей части их можно считать как финальными процессорами. Совместимы со всеми платами Supemicro, TYAN, intel, ASUS (даже с WS C621E SAGE), ASROCK, Gigabyte, HPE, Lenovo, скорее всего также совместимы с Fujitsu. Возможно не совместимы с платамы под XEON W-3175 (ASUS Dominus Extreme и подобное)


## Final OEM Stepping (B1/....)

Данные процессоры предназначены для поставок по OEM каналам производителям брендовых сервером либо по спец. заказам крупным покупателям(Google, Amazon, Microsoft), совместимы они толтко с некоторыми материнскими платами, которые указаны в табличке. Для каких-то цпу требуется определённый микрокод. Например для "народного" Xeon Platinum P-8136 требуется микрокод B1, более подробно я укажу всё в табличке.

Таблица совместимости по Xeon Skylake-SP OEM
 ![](https://github.com/ThinkPadThink/Guide3647/blob/master/xeon%20oem.jpg?raw=true)

## Final Retail 

Данные цпу предназначены уже для конечной продажи. Совместимы уже со всеми платами.


# Cascade Lake-SP:

## All Stepping(A0/H0/M0/U0)

 Полной информации нет по степпингам пока нет. Но из того что известно: Требуется обновлённый UEFI/BIOS иначе не запустится, с большой вероятностью не запустятся на всех платах от самой Intel. Есть версии с суффиксом "M" цпу, например 8276M и "L", например тот же 8276L, разница в поддерживаемых объёмах оперативно памяти. M - до 2 тб памяти. L - поддерживают до 4.5 тб памяти.

Таблица совместимости по Xeon Cascade lake-SP ES
 ![](https://github.com/ThinkPadThink/Guide3647/blob/master/xeon%20cascade%20lake.jpg?raw=true)


# Материнские платы:

**Supermicro:**

Множество различных вариантов серверных плат для сборок. Если собирать односокет то стоит смотреть на плату X11SPi-TF ибо у неё есть полноценный x16 слот для видяхи. У той же X11SPL-F такого нет. В качестве двухсокетных можно рассматривать например X11DPH-i. Плат дохуя, поэтому что-то конкретное не посоветую. Смотрите сами. 

Важные особенности плат Supermicro X11 3647:

На самых свежих UEFI/BIOS ES Skylake-SP могут не работать. Вообще. Нужно шить старые версии UEFI/BIOS;

На всех X11 платах сетевые порты не работают с сетями ниже 1 Гбит/с. Ну кроме наверно IPMI порта;

Внимательно смотрите на ограничения по TDP. 


**TYAN ~~не нужны~~:**

Никакой информации нет, хорошие серверные платы.

**ASROCK:**

ES и OEM Skylake-SP работают из коробки. Так же работают из коробки QS и возможно ES Cascade Lake-SP;

На некоторых платах можно гнать CPU по шине (правда возможно не на всех платах). Полная информация тут [Группа TheSellHard VK](https://vk.com/thesellhard?w=wall-70826500_132664);

В РФ данные платы практически не продаются, проще всего купить их на TaoBao/EBAY/NewEgg.


**Asus:**

На распиаренной ASUS C621 SAGE ES не работают. Про серверные платы ничего не знаю.


**Intel:**

Существует однаплата которая точно переваривает OEM CPU, остальное не знаю.


# Память:

Для Skylake-SP:
Только ECC REG и её производные LRDIMM и т.п.. Обычная UDIMM не подходит!

Для Cascade Lake: 
ECC REG и её подтипы + Optane DC memory.


# Охлаждение: 

Для данного сокета требуется своё охлаждение обычные башни с других сокетов не подойдут. Так же существуют несколько типов крепления охлада, узкий и квадратный(Narrow и Square). По подробнее можно прочитать здесь [Servethehome](https://www.servethehome.com/narrow-square-ilm-socket-lga-3647-heatsink-differences/)

**Крепления:** 

![](https://github.com/ThinkPadThink/Guide3647/blob/master/3647_mount.png?raw=true)

**Установленные CPU в рамки для крепления Narrow и Square:**
![](https://github.com/ThinkPadThink/Guide3647/blob/master/Socket-LGA-3647-Narrow-and-Square-CPU-mounted%20(1).jpg?raw=true)


**Установка CPU:**

На данном сокете нет прижимного механизма для CPU. По факту вы устанавливаете сначала CPU в специальную рамку которую вы крепите к самой системе охлаждения и только потом устанвливаете СО в сокет и прикручиваете строго по нумерации. 


# Сравнение чипсетов сокета LGA3647:

[Смотрите на сайте ARK Intel](https://ark.intel.com/content/www/ru/ru/ark/products/series/98470/intel-c620-series-chipsets.html)

# Общие примечания:

На некоторых платах например у той же Supermciro заместо SATA портов распаивают крупные Mini-SAS порты для sata hdd/ssd/odd устройств, для них может понадобиться кабель SFF-8087(Internal MiniSAS) to 4 SATA **(На счёт этого кабеля не уверен на 100%, возможно я не прав)** либо SFF-8643(Internal MiniSAS HD) to 4 SATA, либо SFF-8654(SlimSAS) to 4 SATA. Фото ниже:

**SFF-8087 to 4 SATA:**

![](https://github.com/ThinkPadThink/Guide3647/blob/master/sff%20to%20sata.jpg?raw=true)
 
 **SFF-8643 to 4 SATA:**

![](https://github.com/ThinkPadThink/Guide3647/blob/master/sff8643tosata.jpg?raw=true)
 
 **SFF-8654 to 4 SATA:**
 
![](https://github.com/ThinkPadThink/Guide3647/blob/master/SLIMSAS.jpg?raw=true)

# Ссылки:
- [Гайд по сокету LGA2011-3](https://github.com/ThinkPadThink/Guide2011-3);
- [Гайд о том как покупать на Ebay](https://github.com/pepe-i-shim/thinkpad-from-ebay);
- [ARK Intel - информация по Финальным ЦПУ Интела](https://ark.intel.com/content/www/ru/ru/ark.html);
- [CPU World - огромная база данных по ЦПУ, есть и информация по инженерным образцам и ОЕМ ](http://www.cpu-world.com).
