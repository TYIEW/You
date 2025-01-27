<p align="center">
    <img src="https://repository-images.githubusercontent.com/558609537/280063f1-bec4-49aa-bf56-054cdb00f8d3" alt="YouTube Music Download Bot" width="640">
</p>

<p align="center">
    <a href="https://www.python.org/downloads/release/python-3110/">
        <img src="https://img.shields.io/badge/python-v3.11-informational" alt="python version">
    </a>
    <a href="https://pypi.org/project/aiogram/2.23.1/">
        <img src="https://img.shields.io/badge/aiogram-v2.23.1-informational" alt="aiogram version">
    </a>
    <a href="https://pypi.org/project/environs/9.5.0/">
        <img src="https://img.shields.io/badge/environs-v9.5.0-informational" alt="environs version">
    </a>
    <a href="https://pypi.org/project/moviepy/1.0.3/">
        <img src="https://img.shields.io/badge/moviepy-v1.0.3-informational" alt="moviepy version">
    </a>
    <a href="https://pypi.org/project/pytube/12.1.0/">
        <img src="https://img.shields.io/badge/pytube-v12.1.0-informational" alt="pytube version">
    </a>
    <a href="https://github.com/psf/black">
        <img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-black.svg">
    </a>
    <a href="https://github.com/rin-gil/YoutubeMusicDownloadBot/actions/workflows/tests.yml">
        <img src="https://github.com/rin-gil/YoutubeMusicDownloadBot/actions/workflows/tests.yml/badge.svg" alt="Code tests">
    </a>
    <a href="https://github.com/rin-gil/YoutubeMusicDownloadBot/actions/workflows/codeql.yml">
        <img src="https://github.com/rin-gil/YoutubeMusicDownloadBot/actions/workflows/codeql.yml/badge.svg" alt="Code tests">
    </a>
    <a href="https://github.com/rin-gil/YoutubeMusicDownloadBot/blob/master/LICENCE">
        <img src="https://img.shields.io/badge/licence-MIT-success" alt="MIT licence">
    </a>
</p>

<p align="right">
    <a href="https://github.com/rin-gil/YoutubeMusicDownloadBot/blob/master/README.md">
        <img src="https://raw.githubusercontent.com/rin-gil/rin-gil/main/assets/img/icons/flags/united-kingdom_24x24.png" alt="En">
    </a>
    <a href="https://github.com/rin-gil/YoutubeMusicDownloadBot/blob/master/README.ua.md">
        <img src="https://raw.githubusercontent.com/rin-gil/rin-gil/main/assets/img/icons/flags/ukraine_24x24.png" alt="Ua">
    </a>
</p>

## YouTube Music Download Bot

Бот для загрузки музыки с YouTube. Рабочая версия доступна по ссылке [@YT_upl_Bot](https://t.me/YT_upl_Bot)

### Возможности

* Поиск музыки на YouTube
* Скачивание найденных видео в формате .mp3

### Установка

```
git clone https://github.com/rin-gil/YoutubeMusicDownloadBot.git
cd YoutubeMusicDownloadBot
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
mv .env.dist .env
```

### Настройка и запуск

* Зарегистрируйте нового бота у [@BotFather](https://t.me/BotFather) и скопируйте полученный токен
* Вставьте токен бота в файл .env
* Запуск бота через файл bot.py `python bot.py`

### Ограничения

* Бот скачивает только музыку (аудиофайл .mp3)
* Бот не скачивает живые трансляции
* Плейлист не скачивается полностью, скачивается только один элемент
* Бот не скачивает клипы продолжительностью больше 20 минут
* Название для аудиофайла формируется из названия видео на YouTube. Поскольку в названии могут содержаться нежелательные символы, не поддерживаемые файловой системой, из названия убираются все символы, кроме букв, цифр, пробелов, знаков '_' и '-', длина названия обрезается до 100 символов

### Локализация

* С версии 1.1.0 в бот добавлена локализация для английского, украинского и русского языка
* Для добавления перевода на свой язык, сделайте следующее:
  1. перейдите в папку с ботом
  2. активируйте виртуальное окружение:

     `source venv/bin/activate`
  3. создайте файл перевода на ваш язык, где **{language}** - код языка по стандарту [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)

     `pybabel init --input-file=tgbot/locales/tgbot.pot --output-dir=tgbot/locales --domain=tgbot --locale={language}`
  4. переведите строки в файле **locales/{language}/LC_MESSAGES/tgbot.po**
  5. скомпилируйте перевод командой:

     `pybabel compile --directory=tgbot/locales --domain=tgbot`
  6. перезапустите бота
* При изменениях строк для перевода в коде, вам нужно будет полностью пересоздать и скомпилировать файлы 
  перевода для всех локализаций:
  1. извлечь строки для перевода из кода:

     `pybabel extract --input-dirs=./tgbot --output-file=tgbot/locales/tgbot.pot --sort-by-file --project=YoutubeMusicDownloadBot`
  2. создать файлы перевода для всех локализаций:

     `pybabel init --input-file=tgbot/locales/tgbot.pot --output-dir=tgbot/locales --domain=tgbot --locale={language}`
  3. скомпилировать переводы:

     `pybabel compile --directory=tgbot/locales --domain=tgbot`
* Более подробно об этом можно прочитать в примере из документации [aiogram](https://docs.aiogram.dev/en/latest/examples/i18n_example.html)
  
### Разработчики

* [Ringil](https://github.com/rin-gil)

### Лицензия

Проект YouTubeMusicDownloadBot распространяется по лицензии [MIT](https://github.com/rin-gil/YoutubeMusicDownloadBot/blob/master/LICENCE)