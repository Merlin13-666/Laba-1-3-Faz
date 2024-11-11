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


Для фаззинга был выбран проект  https://github.com/elzoughby/Base64.git

Скопируем с репозитория 
git clone https://github.com/elzoughby/Base64.git


Теперь пересоберем проект с afl-gcc

mkdir build 
cd build 
CC=/home/danya/AFLplusplus/afl-gcc CXX=/home/danya/AFLplusplus/afl-g++ cmake ..
CC=/home/danya/AFLplusplus/afl-gcc CXX=/home/danya/AFLplusplus/afl-g++ cmake  -- build . 

![изображение](https://github.com/user-attachments/assets/a0951a81-88e5-442f-8f08-9a2b0a415eb1)

![изображение](https://github.com/user-attachments/assets/8b07f653-1d96-4a6a-aadb-cb1bebebdf36)


Создадим корпус
![image](https://github.com/user-attachments/assets/72442c10-547f-4866-94ff-f43e4f157759)

Запускаем фаззинг
~/AFLplusplus/afl-fuzz  -i /home/danya/dir -o /home/danya/out -- ./Base64 decode @@

![изображение](https://github.com/user-attachments/assets/271139f8-acdc-4785-bdff-e8fe0fdcfa8b)

![изображение](https://github.com/user-attachments/assets/889e458f-5a07-4188-950e-507a77705592)

Посмотрим результаты работы находятся в папке ~/out/default/
![изображение](https://github.com/user-attachments/assets/cd94f9db-530b-44ec-aea2-f533da1a6383)

Выведем статистику

![изображение](https://github.com/user-attachments/assets/e1cd49b4-f30a-4fd1-851b-b8f74a5f18e6)



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


