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

![commits_4](https://raw.githubusercontent.com/AndruBot/notes/master/4.png)

Дальше можно спокойно работать, как будто последнего коммита никогда и не существовало

