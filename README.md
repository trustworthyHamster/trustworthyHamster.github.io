# landings-site

Личный сайт с лендингами: **https://trustworthyhamster.github.io**

Хостинг — GitHub Pages. Репозиторий публичный, поэтому на страницах не должно быть
паролей, токенов, личных данных и документов.

## Структура

```
index.html              — страница-указатель со списком всех лендингов
sosiski-guide/
└── index.html          — сам лендинг, ссылка: /sosiski-guide/
```

Каждый лендинг — отдельная папка с файлом `index.html`.
Адрес страницы совпадает с именем папки.

## Как добавить новый лендинг

1. Создать папку, например `travel-checklist/`.
2. Положить в неё `index.html` (стили и скрипты — прямо в файле, без сборки).
3. Добавить ссылку на него в корневой `index.html`.
4. Задеплоить (см. ниже).

## Как задеплоить изменения

```powershell
$git = "C:\Program Files\Git\cmd\git.exe"
$repo = "projects\landings-site"

& $git -C $repo add .
& $git -C $repo commit -m "Добавлен лендинг travel-checklist"
& $git -C $repo push
```

Через 30–60 секунд после `push` страница обновится. Адрес не меняется.

## Инструменты

- git: `C:\Program Files\Git\cmd\git.exe`
- gh (GitHub CLI): `C:\Program Files\GitHub CLI\gh.exe`
- Аккаунт GitHub: `trustworthyHamster`
- Идентичность коммитов задана локально в репозитории:
  `trustworthyHamster` / `trustworthyHamster@users.noreply.github.com`

Важно: в PowerShell этого компьютера заблокированы `npm.ps1` и другие `.ps1`-скрипты
(Execution Policy), поэтому `gh` и `git` вызываются по полному пути к `.exe`.

## Проверка состояния

```powershell
& "C:\Program Files\GitHub CLI\gh.exe" auth status
& "C:\Program Files\GitHub CLI\gh.exe" api repos/trustworthyHamster/trustworthyHamster.github.io/pages
```
