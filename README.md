<a name="readme-top"></a>  

<div align="center">

  <h1 align="center">Команда Megamen</h1>

  <p align="center">
    <h3>Репозиторий для хакатона «Цифровой прорыв. Сезон: Искусственный интеллект»
    <br />
    Кейс от Министерства внутренних дел Российской федерации - «Распознавание образа огнестрельного оружия».<h3>
    <br />
    <a href="https://github.com/mireaMegaman/perm_hack/issues">Сообщить об ошибке</a>
    ·
    <a href="https://github.com/mireaMegaman/perm_hack/issues">Предложить улучшение</a>
  </p>
</div>

**Содержание:**
1. [Проблематика кейсодержателя](#title1)
2. [Описание решения](#title2)
3. [Развертка приложения](#title3)
4. [Демонстрация работы](#title4)


## <a id="title1">Часть 1. Проблематика кейсодержателя</a>
Задание от Министерства внутренних дел Российской Федерации состояло в следующем: 
было необходимо **создать приложения для распознавания образа огнестрельного оружия на фотографии и видео**.

Приложение может использоваться для:
* содействие оперативной работе специальных служб;
* обеспечение безопасности, особенно в зонах повышенной опасности.

Важными особенностями при обучении модели команда выделяет:
* повышение разрешения фотографии (при необходимости);
* точное определение оружия (или его силуэта) на фотографии.


<p align="right">(<a href="#readme-top"><i>Вернуться наверх</i></a>)</p>

## <a id="title2">Часть 2. Краткое описание решения</a>

**Используемый стек технологий**
![изображение](https://github.com/mireaMegaman/perm_hack/assets/100156578/3b67c511-8f9f-4794-b6d4-41aca5e9c3f2)


**Общая схема решения**
![изображение](https://github.com/mireaMegaman/perm_hack/assets/100156578/4786df02-04a0-4ab5-8ec3-8d202bbd37c8)


**За основу решения ML части были выбраны модели:**
* Ансамбль моделей YoloV8 (схема предикта ансамбля схематично он изображена ниже);
  ![изображение](https://github.com/mireaMegaman/perm_hack/assets/100156578/a1dc99a2-fdcc-483f-85b0-9ea4371d7ed5)

* DE⫶TR: End-to-End Object Detection;

**Для демонстрационного приложения были выбраны:**
*  Flutter - для сборки мультиплатформенного приложения, с возможностью **развития** из десктопного варианта и в мобильную среду разработки;

*  FastAPI - в качестве внутренней серверной части, для обеспечения быстрого и эффективного взаимодействия ML моделей с приложением;


**Развитие и масштабируемость:**



<p align="right">(<a href="#readme-top"><i>Вернуться наверх</i></a>)</p>

## <a id="title3">Часть 3. Развертка приложения</a>

**Запуск приложения с помощью одного файла**
Благодаря особенности работы фреймворка Flutter есть возможность собрать финальное приложение на разные платформы заранее. 
Таким образом для быстрого тестирования можно запустить собранное заранее приложение. <br>
Для этого перейдите в [аналогичную директорию](https://github.com/mireaMegaman/perm_hack/)
на вашем устройстве и запустите файл ```mmt_fl_scr.exe```.

**Развертка приложения на Flutter.**
Если же вы хотите посмотреть на приложение в debug-режиме:
```
$ git clone -b beta https://github.com/flutter/flutter.git
```
в конец файла ```~/.bashrc``` добавить 
```
export PATH=<путь к каталогу>/flutter/bin:$PATH
export ANDROID_HOME=/<путь к каталогу>/android-sdk-linux
export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
```
и проверить правильность установки с помощью
```
$ flutter doctor
```

Для запуска приложения - перейдите к файлу ```./mmt_fl/lib/main.dart``` и запустите его в режиме ```Run and Debug```

**Развертка FastApi-сервера:**

Альтернативный способ запуск FastAPI на локальном хосте (для проверки моделей, без приложения):
В Visual Studio Code (Windows) через терминал последовательно выполнить следующие команды:
```
python -m venv venv
venv/Scripts/activate
```
```
cd BackEnd
pip install -r requirements.txt
```
После установки зависимостей:
```
cd ..
uvicorn BackEnd.main:app
```

<p align="right">(<a href="#readme-top"><i>Вернуться наверх</i></a>)</p>

## <a id="title4">Часть 4. Демонстрация работы решения</a>

Ознакомиться с подробным роликом тестирования приложения можно на нашем канале: https://www.youtube.com/channel/UC5qC_I5o2aatXDSxTHbjxzg

<p align="right">(<a href="#readme-top"><i>Вернуться наверх</i></a>)</p>
