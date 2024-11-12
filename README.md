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

Введите путь к директории для сканирования: /home/danya/Base64/

Файл: /home/danya/Base64/main.c | Хэш: 1cd59c8a58b668c3387ed97a3d7707cbce2b54d61aa2a4e2a3c28df49dab89d3

Файл: /home/danya/Base64/CMakeLists.txt | Хэш: 24b277e965ffb092b1a1f7b73a9ab74e3ce6d7a3eb8630f3bb56262abaafe99d

Файл: /home/danya/Base64/cov.info | Хэш: e9863803563a08fc2eafe09848c44b29a921ae04ea9a486a46a9cb110b1098b3

Файл: /home/danya/Base64/base64.h | Хэш: afcd8077b2ac42b2f714a082aca3e51fa42dbd3acc976a46f6d1bf20cdb6f91a

Файл: /home/danya/Base64/.git/config | Хэш: e4c23166baabd94a2d1ddcb6401c808f2fc917d95232a91e6c6a82787003cc81

Файл: /home/danya/Base64/.git/description | Хэш: 85ab6c163d43a17ea9cf7788308bca1466f1b0a8d1cc92e26e9bf63da4062aee

Файл: /home/danya/Base64/.git/logs/refs/remotes/origin/HEAD | Хэш: f055fda1b750755d1396a2d6c55b7dce62147fa7d6840b00336f3e1fad0aad13

Файл: /home/danya/Base64/.git/logs/refs/heads/master | Хэш: f055fda1b750755d1396a2d6c55b7dce62147fa7d6840b00336f3e1fad0aad13

Файл: /home/danya/Base64/.git/logs/HEAD | Хэш: f055fda1b750755d1396a2d6c55b7dce62147fa7d6840b00336f3e1fad0aad13

Файл: /home/danya/Base64/.git/index | Хэш: 6a31b7c9a5a5f4a5bce360e9ee647c4a597ec273a5ab825570db3b8f308e48e9

Файл: /home/danya/Base64/.git/hooks/fsmonitor-watchman.sample | Хэш: e0549964e93897b519bd8e333c037e51fff0f88ba13e086a331592bf801fa1d0

Файл: /home/danya/Base64/.git/hooks/post-update.sample | Хэш: 81765af2daef323061dcbc5e61fc16481cb74b3bac9ad8a174b186523586f6c5

Файл: /home/danya/Base64/.git/hooks/commit-msg.sample | Хэш: 1f74d5e9292979b573ebd59741d46cb93ff391acdd083d340b94370753d92437

Файл: /home/danya/Base64/.git/hooks/prepare-commit-msg.sample | Хэш: e9ddcaa4189fddd25ed97fc8c789eca7b6ca16390b2392ae3276f0c8e1aa4619

Файл: /home/danya/Base64/.git/hooks/pre-rebase.sample | Хэш: 4febce867790052338076f4e66cc47efb14879d18097d1d61c8261859eaaa7b3

Файл: /home/danya/Base64/.git/hooks/applypatch-msg.sample | Хэш: 0223497a0b8b033aa58a3a521b8629869386cf7ab0e2f101963d328aa62193f7

Файл: /home/danya/Base64/.git/hooks/update.sample | Хэш: 8d5f2fa83e103cf08b57eaa67521df9194f45cbdbcb37da52ad586097a14d106

Файл: /home/danya/Base64/.git/hooks/push-to-checkout.sample | Хэш: a53d0741798b287c6dd7afa64aee473f305e65d3f49463bb9d7408ec3b12bf5f

Файл: /home/danya/Base64/.git/hooks/pre-applypatch.sample | Хэш: e15c5b469ea3e0a695bea6f2c82bcf8e62821074939ddd85b77e0007ff165475

Файл: /home/danya/Base64/.git/hooks/pre-merge-commit.sample | Хэш: d3825a70337940ebbd0a5c072984e13245920cdf8898bd225c8d27a6dfc9cb53

Файл: /home/danya/Base64/.git/hooks/pre-receive.sample | Хэш: a4c3d2b9c7bb3fd8d1441c31bd4ee71a595d66b44fcf49ddb310252320169989

Файл: /home/danya/Base64/.git/hooks/pre-push.sample | Хэш: ecce9c7e04d3f5dd9d8ada81753dd1d549a9634b26770042b58dda00217d086a

Файл: /home/danya/Base64/.git/hooks/pre-commit.sample | Хэш: f9af7d95eb1231ecf2eba9770fedfa8d4797a12b02d7240e98d568201251244a

Файл: /home/danya/Base64/.git/refs/remotes/origin/HEAD | Хэш: cdc65e67690c4c6475174e5ec662b70655246a2f3924354778835ab3be70aa76

Файл: /home/danya/Base64/.git/refs/heads/master | Хэш: fab29edd94905ee8852b30bc7e926e1c1f5b12ac552a463f09ca6045ad343899

Файл: /home/danya/Base64/.git/info/exclude | Хэш: 6671fe83b7a07c8932ee89164d1f2793b2318058eb8b98dc5c06ee0a5a3b0ec1

Файл: /home/danya/Base64/.git/HEAD | Хэш: f6f2b945f6c411b02ba3da9c7ace88dcf71b6af65ba2e0d89aa82900042b5a10

Файл: /home/danya/Base64/.git/objects/pack/pack-f87fc11f1ecc3aa60db6f9d0f2a85a8105e6a635.pack | Хэш: 
eb5ae3cd6fa9fc42d894d808da808534f853d86c0c835680c9d33092f3c687ff

Файл: /home/danya/Base64/.git/objects/pack/pack-f87fc11f1ecc3aa60db6f9d0f2a85a8105e6a635.idx | Хэш: fbbc9dcb419b9fdfa44471fccddff9ff69e21ac6b7b408d1707e726cfab6c32a

Файл: /home/danya/Base64/.git/packed-refs | Хэш: 95356c8f3b229e83da388e180cead6805099af705ef649dcad24f0b3b5b655ca

Файл: /home/danya/Base64/base64.c | Хэш: 8c6f7bf30e5576b652d28f85a341d8fd26cffa0642c02ec050da64f60eed0ae7

Файл: /home/danya/Base64/build/CMakeCache.txt | Хэш: cbdb734e995f7b346854836c254dca5e96730078d150816cd11796968da6a6a3

Файл: /home/danya/Base64/build/cmake_install.cmake | Хэш: bd09f42ff532b8da0983c4a6856e11d12447dee7d13592257ac41359de77fcf7

Файл: /home/danya/Base64/build/Makefile | Хэш: 8e91e47a1143f97148a300ce6ad01c13571abe9d337112b00965b3b826bf0c3a

Файл: /home/danya/Base64/build/CMakeFiles/CMakeOutput.log | Хэш: 96b71edcd3cc0bea4a84a048ab4766bfb4e62131ba5a9aa8c2751fecae21f331

Файл: /home/danya/Base64/build/CMakeFiles/progress.marks | Хэш: 1121cfccd5913f0a63fec40a6ffd44ea64f9dc135c66634ba001d10bcf4302a2

Файл: /home/danya/Base64/build/CMakeFiles/cmake.check_cache | Хэш: a26189e394421da57f45706a07713c5720acd200a41711b0c0c590c3c63371c4

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/base64.c.o | Хэш: c44d9e927f79bcd903eceb65926958a536be6d838daa93e00d232f8414274379

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/base64.c.gcno | Хэш: 56231ed09a100e2539636984cec8fbf0a673cd637f7676fcff9c09811a9e0179

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/DependInfo.cmake | Хэш: d08abf1a7ef95055eac463a30b93d97e3bb20a6c422129fd2ec5e353b9736e9f

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/compiler_depend.internal | Хэш: 5bb2d0ace569307547fa9a7cb3affc1ff772d3f086f4ddeb602621642d3d51fb

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/cmake_clean.cmake | Хэш: 908b3a402a2b3dcfe4b0400c724cf7b9e898bf10aad7b34352c898c04a8ffee6

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/base64.c.gcda | Хэш: 52f9ef56180d95a9c465bb3ca7ef07c04487b5e801f6d6cfc3bd510f2fb2aaa7

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/depend.make | Хэш: 73d911aea1a06e8459c1121ae37b7a1be259608baae7fec9e0f627b047b05db3

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/progress.make | Хэш: 5959d6b34b734ea4147141355111615d395cb6ee769773c8d08c38e777847af5

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/compiler_depend.ts | Хэш: 9f0965de557702fe9b1141e8cff7087f8bd69efe113f1069d6d18a603e31f40f

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/link.txt | Хэш: 0f33d98bdd1e6f6642d200bdc1733ba89c730590900c28c256a9bc4d89c86bf3

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/main.c.o.d | Хэш: 27593ae9806bb8c9d22a99ed1d501efb1a39f3a05eec7dd8cc0b94ce5fef5b99

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/main.c.gcno | Хэш: 382e912598f38a584056ae9102171c82c1c78de044351e3aad56fea4f763ddc8

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/main.c.o | Хэш: 4e1cb0899e48bb0b5fcd0723386aef5a2425f679f7201923c0261c71a3bb2e91

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/compiler_depend.make | Хэш: f5a8553debd9c4c7e6be41e81e8ea6ae34607fa8a22bd41c42852a576b23536f

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/flags.make | Хэш: 4a41d24b2b1076eee166fadeae4f2c381dd2bf4cb520a654cf028213544517b3

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/build.make | Хэш: b6335565dd16db803af4bed282a2f4584abebc030895c966297b6fa148d08abb

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/main.c.gcda | Хэш: 571af2221ab778a3266a417f18d72659fdcfcaf63e1911d1259616cceafaad65

Файл: /home/danya/Base64/build/CMakeFiles/Base64.dir/base64.c.o.d | Хэш: c9e52325065bcd2f09955b06f76d2c423c3d8684d91d14590ee43d0d6cc5b613

Файл: /home/danya/Base64/build/CMakeFiles/CMakeDirectoryInformation.cmake | Хэш: 82bbbdf3858babc336901b30b63f5bd6d29e6bd01a60fd8a84db05aaafbe1a7a

Файл: /home/danya/Base64/build/CMakeFiles/Makefile.cmake | Хэш: e6a1f671afd62b099a7ca252264384ffbd36db31997578e5813ff2e7fb06ebb9

Файл: /home/danya/Base64/build/CMakeFiles/TargetDirectories.txt | Хэш: 8d1e2697e531fed989c351045b8446bdbe5ad034bc38094c8d5f89f392bf1d53

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CMakeCXXCompiler.cmake | Хэш: 97998831688b39f7b3be865402e8a51948a757a1ed6e039feab2a2b34e2dbfd0

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CMakeDetermineCompilerABI_C.bin | Хэш: 2e9552bf0c7f5c3b6ac839ce1e7bbf3eb656959a099ab62874fd6d36baeb47f6

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CompilerIdCXX/a.out | Хэш: d9105a255d0b337e43567b0232d069d4882370e64e27d982da5db060522a0dcb

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CompilerIdCXX/CMakeCXXCompilerId.cpp | Хэш: 04001e87fc8cef78e4674853ace8963fd70b0abf302be451e2971f9899ad664e

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CMakeDetermineCompilerABI_CXX.bin | Хэш: a742ca65a61bab6091c36af8cd1dc43ce1ddc2922d3bce3d4d0efb809bf16b7b

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CMakeCCompiler.cmake | Хэш: 72b723d98fc2ff971b2fdaf323d7a4aa14b517a215cb19a547e82143171c0b8a

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CMakeSystem.cmake | Хэш: e61d90a2234b8c8bfb1208693c54df6fc7fff638e195af199b1a603a340566e6

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CompilerIdC/a.out | Хэш: 56be65677a1ced1d4ea6cbaa20ee55a870011e01ac42efd94b9d0bbb9ca2d765

Файл: /home/danya/Base64/build/CMakeFiles/3.25.1/CompilerIdC/CMakeCCompilerId.c | Хэш: d935d5133e8d5b88e5c4873925a8233b6aeb73d3963575f3e9b1e8cc91b7fd87

Файл: /home/danya/Base64/build/CMakeFiles/Makefile2 | Хэш: a58175edf1b02a3f46c4c9ea49d9fc4c27552fb8cf5f5483c467f0e54253b408

Файл: /home/danya/Base64/build/Base64 | Хэш: ca7a045360724f9b1277f829cf262d89bf3655fc848b6c1d386013341dfd68f0

Файл: /home/danya/Base64/.gitignore | Хэш: cbfb2f3659aec6c0b969872627e15ad2683e2cee8302c88df7f5ed42468951bd

Файл: /home/danya/Base64/README.md | Хэш: d40fd5a37ae3c153948448b06a546af033928d3fcba46fa3152d80685da554ed

Файл: /home/danya/Base64/cov_data/snow.png | Хэш: 53c50fc490fcf2ad290819b05f8033b1cbdad698e230bdcbac63564942c34723

Файл: /home/danya/Base64/cov_data/index-sort-l.html | Хэш: a1d63ada28f2ed59bae91ee6c61319deee82c5412137abf7835346a40cbae746

Файл: /home/danya/Base64/cov_data/updown.png | Хэш: a851165a175f4ca2649a4e30291192dd71131ea02a93cf46464953e74c1c5f0c

Файл: /home/danya/Base64/cov_data/index-sort-f.html | Хэш: 51c8d09bfdbb6dd2f46f8a691c10ee2f08827a0ce2994543b31587f840502e7a

Файл: /home/danya/Base64/cov_data/ruby.png | Хэш: a2332ef8c44727042b0ab36628aaf562b0d5b0df43c6fa73c5191dfac50ec7be

Файл: /home/danya/Base64/cov_data/gcov.css | Хэш: b95f92a29fdcac529f3526d0f174f526761760503a9b463383684f7fe23e55ad

Файл: /home/danya/Base64/cov_data/glass.png | Хэш: 936a969e16ba5de4db2c9bcacd197b22a276e3d636335ba7f347da4009fc9cc5

Файл: /home/danya/Base64/cov_data/Base64/index-sort-l.html | Хэш: 14234faf14d8c20b0781d560bf249a5df289fe1c666e707424c6923faecc4681

Файл: /home/danya/Base64/cov_data/Base64/main.c.func.html | Хэш: 76780415a9cd803aec968f46b6ac244faa88e46929d0b8680f14419f63101888

Файл: /home/danya/Base64/cov_data/Base64/index-sort-f.html | Хэш: a5ce4b57338b8a472a7f107cab7c0c29b00fd94a7adb40e0971b90087314651b

Файл: /home/danya/Base64/cov_data/Base64/main.c.gcov.html | Хэш: db9ffb0371beeceab58ea80d9867727a4df3f88a718d463ce384cf0ccf441497

Файл: /home/danya/Base64/cov_data/Base64/base64.c.gcov.html | Хэш: 22277b373834f0c56e54340d619a1e925c77e766cf8129ef594ac7d7dee14e53

Файл: /home/danya/Base64/cov_data/Base64/base64.c.func.html | Хэш: 322415cdee1b6a1e915e0dd24934eb4e3a88164f178cf256ec35af0afda9c38c

Файл: /home/danya/Base64/cov_data/Base64/base64.c.func-sort-c.html | Хэш: 51e882b863415f24d3ff10bbd579be4e668ca34d536e6dece2752bd2e0790791

Файл: /home/danya/Base64/cov_data/Base64/index.html | Хэш: 66d8550e6cc16b800f14e13a2e4d4605f745eba9bd295b487f202e25ebb41f91

Файл: /home/danya/Base64/cov_data/Base64/main.c.func-sort-c.html | Хэш: 586f2df035a80f60de7d2ad32e074fe584d034c941f4f6523e6400acb4ddcfab

Файл: /home/danya/Base64/cov_data/emerald.png | Хэш: 8479273af3556e10f0feb96d8ac24fbd9615b0d887437c0f85f8ef6638e56b83

Файл: /home/danya/Base64/cov_data/amber.png | Хэш: dff576889b1ebdb619eeb69f12d503f7c431d5ff321838624b804ea5bda86fcb

Файл: /home/danya/Base64/cov_data/index.html | Хэш: ad1f9d8331cbd5e0df84ff26d0637b3b21c6fc8862e8ad3b0628aaf04bd8d9f6


## Лабораторная работа 2 Фаззинг AFLplusplus
Скачиваем AFLplusplus c репозитория 

![image](https://github.com/user-attachments/assets/4b1475f5-6d07-42e7-9d7c-ba2da6389135)

Перейдем в  скаченный файл 

![image](https://github.com/user-attachments/assets/07a10433-7d4f-473c-abc2-1e69f2955bf7)


И соберем проект с помощью make 

![image](https://github.com/user-attachments/assets/240d7976-a420-41e1-bc3c-f5285133725d)


Для фаззинга был выбран проект  https://github.com/elzoughby/Base64.git

Скопируем с репозитория 

```git clone https://github.com/elzoughby/Base64.git```


Теперь пересоберем проект с afl-gcc

```mkdir build```

```cd build``` 

```CC=/home/danya/AFLplusplus/afl-gcc CXX=/home/danya/AFLplusplus/afl-g++ cmake .. ```

```CC=/home/danya/AFLplusplus/afl-gcc CXX=/home/danya/AFLplusplus/afl-g++ cmake  -- build . ```


![изображение](https://github.com/user-attachments/assets/a0951a81-88e5-442f-8f08-9a2b0a415eb1)

![изображение](https://github.com/user-attachments/assets/8b07f653-1d96-4a6a-aadb-cb1bebebdf36)


Создадим корпуса

![изображение](https://github.com/user-attachments/assets/791ffbf6-602e-4a41-9b3e-fd87eb0a8e73)


Запускаем фаззинг

```~/AFLplusplus/afl-fuzz  -i /home/danya/dir -o /home/danya/out -- ./Base64 decode @@```

![изображение](https://github.com/user-attachments/assets/271139f8-acdc-4785-bdff-e8fe0fdcfa8b)

![изображение](https://github.com/user-attachments/assets/115bd0a2-b061-4d4a-8af6-2c930791ad0d)


Посмотрим результаты работы находятся в папке ~/out/default/

![изображение](https://github.com/user-attachments/assets/cd94f9db-530b-44ec-aea2-f533da1a6383)

Выведем статистику

![изображение](https://github.com/user-attachments/assets/e1cd49b4-f30a-4fd1-851b-b8f74a5f18e6)



## Лабораторная работа 3 
установим утилиту 

```sudo apt install lcov```

![image](https://github.com/user-attachments/assets/92ab2b9d-149c-4cce-a7d4-12469758f184)

Пересоберем проект для покрытия:

```
CC="gcc --coverage" CXX="g++ --coverage" cmake ..

CC="gcc --coverage" CXX="g++ --coverage" cmake --build .
```

![изображение](https://github.com/user-attachments/assets/ad1166cd-3155-4466-992c-a72971473429)

```find . -name "*.gcda"```

![изображение](https://github.com/user-attachments/assets/20155064-b84a-4865-abb0-e8b2d87f8c74)

Просмотрим корпуса 

![изображение](https://github.com/user-attachments/assets/e09999f2-8b52-481c-b127-b4746d6aa74f)


С помощью корпусов соберем покрытие:

```for file in /home/danya/out/default/queue/*; do ./Base64 encode $file; done```

![изображение](https://github.com/user-attachments/assets/89543c6c-6dbe-45a4-862e-c3b1eff097e4)

```
sudo lcov -o cov.info -c -d .
genhtml -o cov_data cov.info
```

![изображение](https://github.com/user-attachments/assets/de560942-ad76-427b-b075-bb86ef5bbd44)

![изображение](https://github.com/user-attachments/assets/6ae83bb7-a3fb-4965-9f42-f8d627c9a73b)

