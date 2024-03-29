# Sparce - первая задача в курсе UNIX

Вальц Илья кб-401

## Тестирование

Для проверки работы используется скрипт `runme.sh`. 
Этот скрипт создает файл А, далее создается разряженный файл В с помощью программы `main.c`. 
Файлы А и В архивируются в A.gz и B.gz.
Файл B.gz распаковывается и на его основе с помощью `main.c` создается файл C.
На основе файла А создается файл D с помощью `main.c`, но берется размер блока равный 100 байт.
По всем файлам статистика выводится в файл result.txt и в терминал.

## Компоненты

- `f_maker.py` - генерирует файл A размером 4 * 1024 * 1024 + 1 с 1 по смещениям 0, 10000, конец файла
- `main.c` - программа по созданию разряженных файлов. В качестве аргументов принимает файлы для записи и чтения и размер блока, если на вход подается только один файл, то чтение производится с stdin
- `runme.sh` - скрипт для тестирования программы
