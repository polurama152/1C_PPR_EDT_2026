# Запуск проекта 1С (EDT) на GitHub с нуля

Краткая инструкция по инициализации Git-репозитория и первому push.

## 1. Подготовка в EDT

1. Откройте проект в EDT.
2. Выполните **Team → Share Project → Git**.
3. EDT создаст репозиторий и файл `.gitignore`.

## 2. Создание репозитория на GitHub

1. На GitHub создайте новый репозиторий (без README, .gitignore и лицензии).
2. Скопируйте HTTPS-ссылку:
  ```
   https://github.com/ваш_логин/имя_репозитория.git
  ```

## 3. Настройка remote в EDT

1. **Team → Remote → Configure Push URI**.
2. Вставьте скопированную ссылку.
3. Рекомендуется переименовать remote в `origin` (через командную строку или EDT).

## 4. Аутентификация (важно!)

GitHub **не принимает** обычный пароль с 2021 года.

Используйте **Personal Access Token (PAT)**:

1. GitHub → Settings → Developer settings → Personal access tokens → Generate new token (classic).
2. Выберите права `repo`.
3. Скопируйте токен.
4. При push в EDT укажите:
  - Username: ваш GitHub-логин
  - Password: скопированный PAT

## 5. Переименование ветки (master → main)

На GitHub по умолчанию главная ветка — `main`.

Выполните в терминале (в папке проекта):

```bash
git branch -m master main
git push -u origin main
```

Или через EDT: **Team → Branches → Rename Branch**.

## 6. Первый push

- **Team → Push**
- При первом пуше EDT создаст ветку `main` и настроит upstream.

## 7. Рекомендуемый .gitignore

Добавьте в `.gitignore` (если ещё нет):

```gitignore
# EDT / 1C
.metadata/
bin/
*.log
*.tmp
*.bak
*.epf
*.erf
```

