#  Краткий список команд Git

- Все настройки, которые относится к Git
>git config --list --show-origin

## ГЛОБАЛЬНЫЕ НАСТРОЙКИ

- Глобальное имя пользователя
>git config --global user.name "myName"

- Глобальная почта пользователя
>git config --global user.email my@gmail.com

## СОЗДАНИЕ РЕПОЗИТОРИЯ

- переходим в папку будущего репозитория 
- вызываем Git Bash
- иницилизируем репозиторий:
>git init

- переходим на https://github.com/
- создаём новый репозиторий
- копируем его адрес `{url}`

- Связываем локальный и удаленный репозиторий:
>git remote add origin {url}


## КОПИРОВАНИЕ с удалённгого репозитория
>git clone {url}

## СОХРАНЕНИЕ ИЗМЕНЕНИЙ

Статус файлов в репозитории:
>git status

Файлы для сохранения: 
>git add {список файлов}
- или:
>git add . (сохранить все файлы в текущей директории)

Сохранение файлов:
>git commit -m "здесь коментарий"

История комитов:
>git log

Возврвщение к предыдущей версии:
>git checkout {хеш}

## СОХРАНЕНИЕ ИЗМЕНЕНИЙ В УДАЛЕННЫЙ РЕПОЗИТОРИЙ
>git push {url} master
- или:
>git push origin master

## СОХРАНЕНИЕ/СКАЧИВАНИЕ ИЗМЕНЕНИЙ ИЗ УДАЛЕННОГО РЕПОЗИТОРИЯ
>git pull {имя} {ветка}
- или:
>git pull origin master

## ВЕТКИ

- Список локальных веток:
>git branch

- Создание локальной ветки:
>git branch {имя ветки}

- Переключение на другую ветку:
>git checkout {имя ветки}

## СЛИЯНИЕ

- Переходим на ветку с которой делаем слияние (на основную):
>git checkout master
- делаем слияние с {имя ветки}:
>git merge {имя ветки}

## СЛИЯНИЕ способ - 2 -

- перенос всех коммитов с ветки (при 'merge' они не переносятся):
>git rebase {имя ветки} 

## ЗАПРОС НА СЛИЯНИЕ (Pull/Merge Request)

- Создаём на своём репозитории ветку с нашими изменениями
- На https://github.com/ заходим в "Pull Request" и жмакаем "New pull request"
- указываем из какой ветки в какую делаем 'merge'
- добавляем коментарий и описание(по желанию)
- создаём запрос на слияние
- после полученного разрешения делаем слияние "Merge pull request"

## Cherry Pick (применение любого отдельного коммита к другой ветке)

- переключаемся на ветку в которую переносим коммит
- переносим коммит:
>git cherry-pick {хеш}

## Git Revert ( отмена коммита )

>git revert {хеш}
- если открылся редактор, то можно выйти - ':wq'
- в результае коммит не удален и его можно найти ('git log') и вернуть

## Git Reset ( раскоммичивает изменения из переданных коммитов )
- ! здесь {хеш} - коммита который должен остаться, до него все последние удаляются

### с параметром --soft (мягкий Reset)
- выводит коммиты в индекс (как при команде 'git add .' до коммита):
>git reset --soft {хеш}

### с параметром --hard (жесткий Reset)
- полностью удаляет коммиты:
>git reset --hard {хеш}

## Дополнительные материалы

### [Статья "... 30 команд ..."](https://rufri.ru/30-osnovnyh-komand-git-dlja-upravlenie-repozitorijami-github/)
### [Док-я на Git](https://git-scm.com/book/ru/v2/%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-Git)
### [Интерактивный онлайн-курс](https://learngitbranching.js.org/?locale=ru_RU)