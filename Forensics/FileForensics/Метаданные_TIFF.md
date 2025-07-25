## 1. УСТРОЙСТВО TIFF

Файлы формата TIFF начинаются с 2х байт:
0x4D 0x4D, если байтовый порядок в файле Big-endian, либо 0x49 0x49 в противном случае.
После идут 2 байта обозначающие версию формата обычно 0x2A 0x00 (0x00 0x2A)
Далее идут 4 байта обозначающие смещение до первого IFD, после идут IFD.

***все смещения считаются от начала файла***

## 2. IFD

IFD представляет из себя структуру содержащую метаданные. Он начинается с 2 байт обозначающих количество тегов, а заканчивается 4 байтами обозначающими смещение до следующего IFD (или 0 если это последний IFD).
После 2-х байт начала IFD идут TIFF теги.

## 3. TIFF-теги

TIFF тег представляет из себя следующую структуру:
- 2 байта - числовой идентификатор тега (тип тега)
- 2 байта - тип условных единиц в которых измеряются данные
- 4 байта - количество условных единиц данных в теге
- 4 байта - смещение до данных (или сами данные если они помещаются в 4 байта)

## 4. Типы условных единиц данных

Типы условных единиц обозначаются числами:
- 1 - UNSIGNED BYTE (размер условной единицы - 1 байт)
- 2 - ASCII-строка (размер условной единицы - 1 байт)
- 3 - UINT16 (размер условной единицы - 2 байта)
- 4 - UINT32 (размер условной единицы - 4 байта)
- 5 - UNSIGNED RATIONAL (2 UINT32 - числетель и знаменатель) (размер условной единицы - 8 байт)
- 6 - BYTE (размер условной единицы - 1 байт)
- 7 - UNDEFINED (обычно это строка с преамбулой о кодировке) (размер условной единицы - 1 байт)
- 8 - INT16 (размер условной единицы - 2 байта)
- 9 - INT32 (размер условной единицы - 4 байта)
- 10 - RATIONAL (размер условной единицы - 8 байт)
- 11 - FLOAT (размер условной единицы - 4 байта)
- 12 - DOUBLE (размер условной единицы - 8 байт)