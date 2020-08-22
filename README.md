# Как удалить коммит/откатить ветку на несколь коммитов назад

Бывают ситуации когда необходимо срочно откатить ветку в репозитории на несколько коммитов назад, а последние пару коммитов удалить

Как это сделать проще всего я покажу на примере тестового репозитория и SourceTree.

![commits_1](https://raw.githubusercontent.com/AndruBot/notes/master/1.png)

Чтобы "удалить" из ветки master последний коммит придется немного нарушить правила хорошего тона при работе с git'ом

Для начала откатываемся до нужного коммита с помощью "Reset master to this commit"

И получаем такую картину

![commits_2](https://raw.githubusercontent.com/AndruBot/notes/master/2.png)

Локальная ветка master отстает он remote ветки на 1 коммит

Дальше заходим в консоль, где находится наш проект, и вводим команду

```console
git push origin master --force
```

В консоле мы увидим примерно такое сообщение

![commits_3](https://raw.githubusercontent.com/AndruBot/notes/master/3.png)

А в SourceTree последний коммит "исчезнет"

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/10.png)

Дальше можно спокойно работать, как будто последнего коммита никогда и не существовало

# Как вернуть "удаленный коммит"

Можно ли вернуть удаленный коммит обратно в ветку? 

Конечно можно!

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/11.png)

Все что было в git'e, остается в git'e!

чтобы это сделать нам потребуется ввести в консоли команду

```console
git reflog
```

и мы увидим такую картину

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/12.png)

в консоли мы можем увидеть полный список коммитов нашего проекта, и мы также видим скрытый коммит

для того чтобы вернуть его в ветку нам потребуется сделать ```cherry pick```

запоминаем хэш коммита который мы хотим вернуть, и вводим в консоль команду

```console
git cherry-pick HASH
```

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/13.png)

После этого коммит появляется в локальной ветку

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/14.png)

Дальше мы просто делаем push, и коммит снова появляется у нас в репозитории!

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/15.png)

Нужно помнить!
Когда вы делаете cherry-pick у вас могут появиться конфликты, их придется разрешить перед тем как запушить изменения в репозиторий!




