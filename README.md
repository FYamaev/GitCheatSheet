# Шпаргалка по работе с Git  
## Базовые команды в консоли  
### Навигация  
- `pwd` (от англ. ***p****rint ****w****orking ********directory*, «показать рабочую папку») — покажи, в какой я папке;  
- `ls` (от англ. ***l****ist ****d****irectory ****c****ontents*, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;  
- `ls -a` покажи также скрытые файлы и папки, названия которых начинаются с символа `.`;  
- `cd first-project` - (от англ. ***c****hange ****d****irectory*, «сменить директорию») — перейди в папку `first-project`;  
- `cd first-project/html` — перейди в папку ``html, которая находится в папке `first-project`;  
- `cd ..` — перейди на уровень выше, в родительскую папку;  
- `cd ~` — перейди в домашнюю директорию (`/Users/Username`);  
- `cd /` — перейди в корневую директорию.

### Работа с файлами и папками
**Создание**  
- `touch index.html` (англ. *touch*, «коснуться») — создай файл `index.html` в текущей папке;
- `touch index.html style.css script.js` — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
- `mkdir second-project` (от англ. ***m****ake ****d****irectory*, «создать директорию») — создай папку с именем `second-project` в текущей папке.

**Копирование и перемещение**  
- `cp file.txt ~/my-dir` (от англ. ***c****o****p****y*, «копировать») — скопируй файл в другое место;
- `mv file.txt ~/my-dir` (от англ. ***m****o****v****e*, «переместить») — перемести файл или папку в другое место.

**Чтение**  
- `cat file.txt` (от англ. *con****cat****enate and print*, «объединить и распечатать») — распечатай содержимое текстового файла `file.txt`.

**Удаление**
- `rm about.html` (от англ. ***r****e****m****ove*, «удалить») — удали файл `about.html`;
- `rmdir images` (от англ. ***r****e****m****ove ****dir****ectory*, «удалить директорию») — удали папку `images`;
- `rm -r second-project` (от англ. ***r****e****m****ove*, «удалить» + ***r****ecursive*, «рекурсивный») — удали папку `second-project` и всё, что она содержит.

### Полезные возможности
- Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (`&&`).  
- У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (`↑`) и вниз (`↓`).  
- Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать `Tab`. Если файл или папка есть в текущей директории, командная строка допишет путь сама.  
- Например, вы находитесь в папке `dev`. Начните вводить `cd first` и дважды нажмите `Tab`. Если папка `first-project` есть внутри `dev`, командная строка автоматически подставит её имя. Останется только нажать `Enter`.


## Работа с репозиториями
- `git init` (от англ. ***init****ialize* — «инициализировать») - сделать папку Git-репозиторием;  
- `rm -rf .git` - "разгитить" папку, удалить скрытую подпапку `.git`.

**Синхронизация локального и удалённого репозиториев**  
- `git remote add origin https://github.com/<Username>/<Reponame>` (от англ. *remote*, «удалённый» + *add*, «добавить») — привяжи локальный репозиторий к удалённому с URL `https://github.com/<Username>/<Reponame>`;  
- `git remote -v` (от англ. *verbose*, «подробный») — проверь, что репозитории действительно связались;  
- `git push -u origin main` (от англ. *push*, «толкать») — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием `origin`.

**Подготовка файла к коммиту**  
- `git add todo.txt` (от англ. *add*, «добавить») — подготовь файл `todo.txt к коммиту;  
- `git add --all` (от англ. *add*, «добавить» + *all*, «всё») — подготовь к коммиту сразу все файлы, в которых были изменения, и все новые файлы;  
- `git add .` — подготовь к коммиту текущую папку и все файлы в ней.

**Создание и публикация коммита**  
- `git commit -m "Комментарий к коммиту."` (от англ. *commit*, «совершать», фиксировать» + ***m****essage*, «сообщение») — сделай коммит и оставь комментарий, чтобы было проще понять, какие изменения сделаны;  
- `git push` (от англ. *push*, «толкать») — добавь изменения в удалённый репозиторий.

**Просмотр информации о коммитах**  
- `git log` (от англ. *log*, «журнал [записей]») — выведи подробную историю коммитов;  
- `git log --oneline` (от англ. *log*, «журнал [записей]» + *oneline*, «одной строкой») — покажи краткую информацию о коммитах: сокращённый хеш и сообщение.

**Просмотр состояния файлов**  
- `git status` (от англ. *status*, «статус», «состояние») — покажи текущее состояние репозитория.

**Добавление изменений в последний коммит**  
- `git commit --amend --no-edit` (от англ. *amend*
, «исправить») — добавь изменения к последнему коммиту и оставь сообщение прежним;  
- `git commit --amend -m "Новое сообщение"` — измени сообщение к последнему коммиту на Новое сообщение.

**«Откат» файлов и коммитов**  
- `git restore --staged hello.txt` (от англ. *restore*, «восстановить») — переведи файл `hello.txt` из состояния `staged` обратно в `untracked` или `modified`;  
- `git restore hello.txt` — верни файл `hello.txt` к последней версии, которая была сохранена через `git commit` или `git add`;  
- `git reset --hard b576d89` (от англ. *reset*, «сброс», «обнуление» + *hard*, «суровый») — удали все незакоммиченные изменения из staging и «рабочей зоны» вплоть до указанного коммита.

**Просмотр изменений**  
- `git diff` (от англ. *difference*, «отличие», «разница») — покажи изменения в «рабочей зоне», то есть в `modified`-файлах;  
- `git diff a9928ab 11bada1` — выведи разницу между двумя коммитами;  
- `git diff --staged` — покажи изменения, которые добавлены в `staged`-файлах.

## Навигация по коммитам. Статусы файлов
### Хэш
- Хеш — основной идентификатор коммита, обычно это короткая (40 символов в случае SHA-1) строка, которая состоит из цифр 0—9 и латинских букв A—F (неважно, заглавных или строчных).  
- Git хранит хэш и таблицу соответствий `хеш → информация о коммите`в служебных файлах в скрытой папке `.git` репозитория проекта.  

### HEAD
- Файл `HEAD` (англ. «голова», «головной») — один из служебных файлов папки `.git`. Он указывает на коммит, который сделан последним (то есть на самый новый).  
- Внутри `HEAD` — ссылка на служебный файл: `refs/heads/master` (или `refs/heads/main` в зависимости от названия ветки), в котором содержится хеш последнего коммита.  
В команды Git, в качестве параметра хэш коммита можно указывать `HEAD` - будет использоваться последний коммит.

### Статусы
- `untracked` (англ. «неотслеживаемый») - новые файлы в Git-репозитории помечаются как `untracked`, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём;  
- `staged` (англ. «подготовленный») - после выполнения команды `git add` файл попадает в **staging area** (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии `staged`;  
- `tracked` (англ. «отслеживаемый») - в него попадают файлы, которые уже были зафиксированы с помощью `git commit`, а также файлы, которые были добавлены в staging area командой `git add`;  
- `modified` (англ. «изменённый») - содержимое файла отличается от последней сохраненной версии.

**Схема смены статусов.**  
```mermaid
graph LR;
	untracked -- "git add" --> staged;
	staged -- "git commit" --> tracked/comitted;
```

### Ошибки в коммитах
- `git restore --staged <file>` - переведёт файл из `staged` обратно в `modified` или `untracked`.  
- `git reset --hard <commit hash>` - «откатит» историю до коммита с хешем `<hash>`. Более поздние коммиты потеряются!  
- `git restore <file>` - «откатит» изменения в файле до последней сохранённой (в коммите или в staging) версии.

### Изменения в файлах
- `git diff` (от англ. ***diff****erence* — «отличие», «разница»).