# СТЕКЛООЧИСТИТЕЛИ / ДАТЧИК ДОЖДЯ И СВЕТА

### Сервисное положение стеклоочистителей в меню Swing
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper - Menuesteuerung Frontwischer: Активировать
→ Применить
```

### Парковка дворников при выключенном зажигании

!!! note ""
    Решает проблему с остановкой дворников на пол пути посредине стекла при выключении зажигания.
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper:
- Wischer stop bei KL15 aus: Деактивировать
→ Применить
```

### Дополнительный взмах передних стеклоочистителей (дотирка капель)
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Rear Window Wiper - Traenenwischen Heck: Активировать
Windshield wiper - Traenenwischen Front Status: Активировать
→ Применить
```

### Изменение чувствительности датчика света
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Assistance light functions-Lichtsensorempfindlichkeit → normal (нормально) изменить на "non sensitive" (не чувствителен)
→ Применить
```

### Отключение омывателя фар
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper-SRA Waschzeit → 2300 ms заменить на 0
→ Применить
```

### Увеличение интервала и времени срабатывания омывателей фар

Параметр, отвечающий на какой раз омывания стекла сработают фароомыватели.  
Если сменить стандартные “9” на 1 - то сработают каждый раз.  
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper-Anzahl Betaetigungen Frontwaschanlage pro SRA Aktivierung → вводим «15»
→ Применить
```

Параметр, отвечающий за время удержания подрулевого рычажка омывания лобового стекла, чтобы сработали омыватели фар
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper — SRA Verzoegerungszeit → меняем стандартные 0 мс на, к примеру, 1500 мс (1,5 сек)
→ Применить
```

Сколько секунд будут работать фароомыватели
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper — SRA Waschzeit → стандартное значение 600 мс.
→ Применить
```

### Отключение срабатывания заднего стеклоочистителя при включении заднего хода
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Rear Window Wiper-Komfortwischen Heck → not active
→ Применить
```
либо посредством меню магнитолы

### Автоматическое включение заднего дворника

!!! note ""
    Задний дворник начинает срабатывать при продолжительной непрерывной работе передних дворников на 2 скорости.
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Rear Window Wiper - Automatisches Heckwischen: Активировать
→ Применить
```

### Положение размораживания дворников
``` yaml title="логин-пароль: 31347"
Блок 09 → Адаптация:
Windshield wiper - Frontwischer Abtauposition → Abtauposition temperaturunabhaengig Referenzwischen 
→ Применить
```