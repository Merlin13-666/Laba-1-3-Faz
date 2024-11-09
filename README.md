# Laba-1-3-Faz
## Лабораторная работа 1 Контрольная сумма 

Создадим файл и напишем скрипт
#!/bin/bash

\# Функция для вычисления хэша файла
calculate_hash() {
    local file_path=$1
    if [[ -f "$file_path" ]]; then
        sha256sum "$file_path" | awk '{print $1}'
    else
        echo "Ошибка: Файл $file_path не найден или недоступен"
    fi
}

\# Рекурсивное сканирование директории
recursive_hash_scan() {
    local directory=$1
    find "$directory" -type f | while read -r file; do
        file_hash=$(calculate_hash "$file")
        if [[ -n "$file_hash" ]]; then
            echo "Файл: $file | Хэш: $file_hash"
        fi
    done
}

read -p "Введите путь к директории для сканирования: " directory_to_scan
recursive_hash_scan "$directory_to_scan"

Результаты запуска скрипта
![image](https://github.com/user-attachments/assets/7840571a-a9af-4fb2-b094-a85b720be2cd)

## Лабораторная работа 2 Фаззинг AFLplusplus
Скачиваем AFLplusplus c репозитория 
![image](https://github.com/user-attachments/assets/4b1475f5-6d07-42e7-9d7c-ba2da6389135)

Перейдем в  скаченный файл 
![image](https://github.com/user-attachments/assets/07a10433-7d4f-473c-abc2-1e69f2955bf7)


И соберем проект с помощью make 
![image](https://github.com/user-attachments/assets/240d7976-a420-41e1-bc3c-f5285133725d)


Для фаззинга был выбран проект git clone https://github.com/SJTUJohnClass/Minivim.git

Скопируем с репозитория 
![image](https://github.com/user-attachments/assets/f8420e85-849e-4c79-af9c-4ab0c8795f86)


Теперь пересоберем проект с afl-gcc
![image](https://github.com/user-attachments/assets/8ffb994d-c53e-4e96-9345-e40a5f73e57c)

Собираем проект с помощью make
![image](https://github.com/user-attachments/assets/b5331102-54c3-469e-a335-a3bba6cb0fab)

Создадим корпус
![image](https://github.com/user-attachments/assets/72442c10-547f-4866-94ff-f43e4f157759)
Запускаем фаззинг
![image](https://github.com/user-attachments/assets/8b960d7c-9d9b-452a-a489-748f5e665bc8)

minivim работает не корректно!

берем другой проект ( текстовый редактор kilo ) 
https://github.com/antirez/kilo/tree/master

собираем проект для фаззинга 
![image](https://github.com/user-attachments/assets/2de835c9-4843-4890-8dfb-6af5b8d6372b)

Cоздаем тестовые файлы для входа (корпуса)
![image](https://github.com/user-attachments/assets/633013d5-eb43-457c-9873-e411dd9ff32b)

Запускаем проект
![image](https://github.com/user-attachments/assets/d00399e4-5d63-4a30-ba1f-8fd664ec8f24)
![image](https://github.com/user-attachments/assets/f8c1c540-8123-4a4d-b091-56fd351d38a9)

все итоги работы фаззинга записаны в файл outdd
![image](https://github.com/user-attachments/assets/e15088f4-af59-4a2e-aaa1-c6f0ea28387f)

Результаты проведенного фаззинга можно посмотреть 
![image](https://github.com/user-attachments/assets/6ca95156-d2db-4124-a6f9-fae52bfb7cc9)

## Лабораторная работа 3 
установим утилиту 
![image](https://github.com/user-attachments/assets/92ab2b9d-149c-4cce-a7d4-12469758f184)

Собираем проект с параметром --coverage, чтобы получить kilo.gcno
![image](https://github.com/user-attachments/assets/c08b89e1-7b26-4a71-8be3-c947a1fa4fb4)

выполним покрытие и приведем его в порядок 
![image](https://github.com/user-attachments/assets/8778b301-ed4f-49e9-9e5a-0ed1d0cafcdd)

Получим покрытие 
![image](https://github.com/user-attachments/assets/c2d94093-6d98-45c2-bcec-2661239800f1)
![image](https://github.com/user-attachments/assets/ab6660b7-ea9e-4b3e-826a-aad1c20586d0)


