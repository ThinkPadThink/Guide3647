# Гайд по сокету LGA3647
Это пока что попытка написать мануал по сокету LGA3647. Возможно из этого что-то получится, возможно я это позже удалю. 

Сокет LGA 3647

В основном данный сокет предназначен чисто под серверные системы. Однако в связи с наличием относительно недорогих инженерных образцов данный сокет может стать хорошей системой для работы. Рендер и тому подобное.


Материнские платы:

Микра:
Множество различных вариантов серверных плат для сборок. Если собирать односокет то стоит смотреть на плату X11SPi-TF ибо у неё есть полноценный x16 слот для видяхи. У той же X11SPL-F такого нет. В качестве двухсокетных можно рассматривать например X11DPH-i.

Важные особенности
на самых свежих UEFI инженерники Skylake-SP не работают. Вообще. Нужно шить старые UEFI.
На всех X11 платах сетевые порты не работают с сетями ниже 1 Гбит. Ну кроме наверно IPMI порта. 
По поводу совместимости с цпу пока ничего не знаю, дополню как нарою инфу.

ТЯН:
~~не нужны~~ Вроде как самые годные платы для ОЕМ и инжей. Лучше всего на них они работают.

Асрок:
Есть инфа что всё очень хорошо с инжами и ОЕМ. Точно есть инфа что QS Cascade Lake работают.

Асус:
Ничего не знаю кроме как C621 SAGE не работает с всеми Skylake-SP 2 степпинга.

Интел:
Существует однаплата которая точно переваривает OEM цпу, остальное не знаю.

Память:
Для Skylake-SP:
Только ECC REG другая не подойдёт и её производные LRDIMM и т.п..
Для Cascade Lake: 
Тоже самое + Optane DC memory.

Охлад: 

Для данного сокета требуется своё охлаждение обычные башни с других сокетов не подойдут.
К слову говоря цпу по факту монтируется сначала на сам пятак системы охлаждения, а потом уже крепится и прижимается к сокету. Своего зажима у сокета нет, используется только охлаждение.
