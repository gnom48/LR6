# Лабораторная работа №6

**Выполнил:** студент группы 4517 Иванов Е.С.
**Дата:** 25.09.2026

## Цель работы
изучение базовых возможностей системы управления версиями, опыт работы с Git Api, опыт работы с локальным и удаленным репозиторием.

## Ход работы

### 1. Создание аккаунта на GitHub

Скипаем (аккуант уже был)
![Я](images/me.png)

### 2. Форк репозитория

Сделана личная копия репозитория
https://github.com/Kurtyanik/LR6/ через кнопку **Fork**.

![Fork](images/fork.png)

### 3. Установка и настройка Git

Скипаем (уже стоял)

### 4. Клонирование репозитория
```bash
git clone https://github.com/gnom48/LR6.git
cd LR6
```

### 5. Добавление файла через интерфейс GitHub

Файл `file.txt` создан через кнопку **Add file → Create new file** и закоммичен.
Изменения подтянуты локально:

```bash
git pull origin branch1
```

### 6. История операций
Просмотр истории по всем веткам:

```bash
git log --all --graph --decorate --oneline
```
![Изменения](images/changes.png)

### 7. Просмотр последних изменений
```bash
git log --stat -n 3
```

8. Слияние с master и разрешение конфликта
```bash
git checkout master
git merge branch1
```
Конфликт разрешён вручную в VS Code, затем:

```bash
git add .
git commit -m "Merge: порешали конфликт"
```

### 9. Удаление побочной ветки
```bash
git branch -d branch1
```

### 10. Несколько коммитов и откат
Серия изменений:

```bash
git add .
git commit -m "Дописали mergefile.txt"
...
git add .
git commit -m "Наследили в file.txt"
```

Откат последнего коммита:

```bash
git reset --hard HEAD~1
```

### 11. Ветка для отчёта
```bash
git checkout -b report
```

...

## Лог команд (без вывода)

```bash
git clone https://github.com/gnom48/LR6.git
cd LR6
git checkout branch1
git status
git pull origin branch1
git log --all --graph --decorate --oneline
git log --stat -n 3
git checkout master
git merge branch1
git status
git add mergefile.txt
git status
git commit -m "Merge: конфликт порешали"
git branch -d branch1
git add mergefile.txt
git commit -m "Дописали mergefile.txt"
git add file.txt
git commit -m "Наследили в file.txt"
git reset --hard HEAD~1
git checkout -b report
git add .
git commit -m "Начали оформлять отчет"
git add .
git commit -m "Продолжили оформлять отчет"
```

### 15. Форматированный вывод лога

```bash
git log --pretty=format:"%h - %ad - %an : %s" --date=short
f05fe9c - 2026-09-25 - gnom48 : Продолжили дополнять оформлять отчет
b5b8b4a - 2026-09-25 - gnom48 : Продолжили оформлять отчет
cdbb11d - 2026-09-25 - gnom48 : Начали оформлять отчет
1056637 - 2026-09-25 - gnom48 : Дописали mergefile.txt
3a358be - 2026-09-25 - gnom48 : Merge: конфликт порешали
4b78266 - 2026-09-25 - gnom48 : Create file.txt
921f53b - 2020-11-21 - Kurtyanik : Обновление информации
0f9f50d - 2020-11-21 - Kurtyanik : Заполнил файл
c08a654 - 2020-11-21 - Kurtyanik : Файл создан пустым
3c6e913 - 2020-11-21 - Kurtyanik : Initial commit
```

### Финал

Сделал pull request через интерфейс GitHub, чтобы слить report в master
