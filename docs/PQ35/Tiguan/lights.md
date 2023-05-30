# ОСВЕЩЕНИЕ

###  Чувствительность датчика света 
Можно оптимально настроить чувствительность датчика света. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Подблок RLS → Длинное кодирование:
Байт 1 – Бит 0-7 → выбираем нужное значение, либо указываем вручную. 
```
Чем ниже значение, тем в более тёмное время будут включаться фары.   
Рекомендуемый диапазон: …0707, 0808, 0909, 0A10, 0B11, 0C12, 0D13, 0E14, 0F15, 1016, 1117, 1218, 1319, 1420, 1521, 1622, 1723…  

### Включение аварийной сигнализации при экстренном торможении 
Срабатывает при резком (аварийном) торможении в виде частого моргания стоп-сигналами или указателями поворотов (аварийной сигнализацией).  
Есть 2 варианта работы: A – через стоп-сигналы, B – через указатели поворотов
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
(A) Байт 16 – Бит 1: Деактивировать
(B) Байт 16 – Бит 2: Активировать 
```

!!! warning ""
    При одновременной активации обоих вариантов, экстренная аварийная сигнализация работать не будет! 

### Подсветка пространства ног при открытии двери 
Если через MFA+ настроена невысокая яркость подсветки ног, то при открытии двери подсветка становится ярче. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация: 
27 канал → вводим значение от 0 до 200 (0 – 100%) → сохранить 
```

### Режим Highway 
Данная функция при длительном движении на скорости свыше 140 км/ч, автоматически включает ближний свет и габаритные огни, так называемый европейский режим Highway.  
При движении на скорости ниже 140 км/ч более 2 минут, режим автоматически отключается. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Подблок RLS → Длинное кодирование:
Байт 0 – Бит 0: Активировать 
```

### Выключение ДХО при включенном ручном тормозе 
Пока автомобиль стоит на ручном тормозе – ДХО выключены, как только «ручник» снят – ДХО включаются. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 11 – Бит 0: Активировать
```
У кого 0 бит скрыт, то можно шестнадцатеричное значение C0 заменить на C1. 

### Комфортный указатель поворота 
Комфортный указатель поворота (он же режим автобана) включает повторители поворотов на определённое количество морганий при лёгком прикосновении к подрулевому рычагу управления поворотниками, не фиксируя этот самый рычаг в положении «включен». 
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация: 
31 канал → вводим значение количества морганий (от 1 до 5) → сохранить 
```

### Работа стоп-сигналов на не заведённом авто 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 16 – Бит 6: Активировать 
```

### Отключение ПТФ при моргании дальним светом 
При включении дальнего света временно отключаются ПТФ. Если «мигать» дальним, то получаются неплохие стробоскопы. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 14 – Бит 2: Активировать 
```

### Салонное освещение при открытии двери багажника 
По умолчанию, при открытии двери багажника, в салоне загорается свет (при условии установленного переключателя салонного освещения в положение «свет при открытых дверях»).  
При открытии двери багажника лампочка подсветки багажного отделения включается. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 20 – Бит 1: Деактивировать 
```

### Активация стоп-сигналов на крышке багажника 
Данная кодировка проверена на рестайле и дорестайле ТОЛЬКО с галогенными фарами (NO XENON!). 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 18: меняем значение AA на 2F (только не C0!) 
```
На ксеноне возможно с помощью VAS 5054a, VAS PC и модифицированного скрипта для работы со световой конфигурацией от ŠkodaPilot:   
Ведомые функции → Skoda V19.47 → Octavia 2004 → 2011 (B) → Седан → CDAB 1,8 л TFSI / 112 кВт → Центральный коммутационный блок → J519 – Конфигурация освещения, параметрирование → адрес 3088 → меняем значение 21 на 29. 

### Активация ДХО через ПТФ с регулировкой яркости 
Только для тех, у кого нет штатного ксенона и светодиодных модулей в фаре Для активации ПТФ вместе с ДС: 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 14 – Бит 1: Активировать 
```
Чтобы отключить ДС: 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 15 – Бит 6: Деактивировать 
```
Убавить яркость ПТФ при включенном ДХО (60% накала от 55 Вт, т.е. 33 Вт): 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 24 – Бит 0-6 → 60 
```

### Функция Coming Home 
Функция Coming Home оставляет включенными фары ближнего света (или ПТФ) и габаритные огни не некоторое время после закрытия машины, как бы освещая Вам дорогу до дома. 

!!! note "2 варианта работы"
    A – через ближний свет;  
    B – через ПТФ.  
!!! note "2 варианта срабатывания"
    C – после открытия водительской двери;  
    D – после выключения зажигания.  
!!! note "2 варианта управления"
    E – автоматический (активируется по датчику света);  
    F – ручной (необходимо после выключения зажигания «моргнуть» дальним светом).
     
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
A) Байт 17 – Бит 5: Активировать 
B) Байт 17 – Бит 3: Активировать 
C) Байт 12 – Бит 0: Активировать 
D) Байт 12 – Бит 0: Активировать  
E) Байт 12 – Бит 2: Активировать 
F) Байт 12 – Бит 2: Активировать  
```
Время работы функции
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация: 
23 канал → вводим значение времени работы (в секундах, от 10 до 60 с шагом 10) → сохранить 
```

### Функция Leaving Home 
Функция Leaving Home включает фары ближнего света и габаритные огни не некоторое время после открытия машины со штатного брелка, как бы освещая Вам дорогу до автомобиля.   
Также полезно во время поисков машины в тёмное время суток на забитой парковке. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 17 – Бит 6: Активировать 
```
Время работы функции
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация: 
24 канал → вводим значение времени работы (в секундах, от 10 до 60 с шагом 10) → сохранить 
```

### Подсветка поворотов с помощью ПТФ (Corner) 
Функция Corner работает только на скорости до 40 км/ч и совместно с ближним светом.   
Есть 2 варианта: A – включение в зависимости от положения датчика руля; B – включение в зависимости от положения датчика руля и включенных повторителей поворотов. 
``` yaml title="логин-пароль: 31347"
Блок 09 → Кодирование → Длинное кодирование:
Байт 14 – Бит 0: Активировать 
Байт 14 – Бит 7: Активировать 
A) Байт 17 – Бит 0: Деактивировать 
B) Байт 17 – Бит 0: Активировать 
```