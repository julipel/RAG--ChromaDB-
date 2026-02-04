# Инструкция по настройке нового репозитория

## Текущий статус

✅ Проект отвязан от старого репозитория `git@github.com:MrGAN12009/5-7.git`

## Создание нового репозитория на GitHub

### Шаг 1: Создайте новый репозиторий на GitHub

1. Перейдите на https://github.com/new
2. Заполните данные:
   - **Repository name**: например, `rag-assistant-v2` или `rag-telegram-bot`
   - **Description**: описание вашего проекта
   - **Visibility**: выберите Public или Private
   - **НЕ** инициализируйте репозиторий (не добавляйте README, .gitignore или лицензию)

### Шаг 2: Подключите новый репозиторий к локальному проекту

Выполните следующие команды в терминале:

```bash
# Добавьте новый remote (замените URL на ваш новый репозиторий)
git remote add origin git@github.com:ВАШ_USERNAME/НАЗВАНИЕ_РЕПОЗИТОРИЯ.git

# Или если используете HTTPS:
# git remote add origin https://github.com/ВАШ_USERNAME/НАЗВАНИЕ_РЕПОЗИТОРИЯ.git

# Проверьте, что remote добавлен
git remote -v
```

### Шаг 3: Закоммитьте текущие изменения

```bash
# Добавьте все файлы
git add .

# Создайте коммит
git commit -m "Initial commit: RAG assistant with Telegram bot and database logging"

# Или более детальное описание:
# git commit -m "feat: Add Telegram bot integration, database logging, and vector store
# 
# - Added Telegram bot with /start, /help, /stats, /logs commands
# - Implemented SQLite database logging for all interactions
# - Created vector_store.py wrapper for easier vector store management
# - Added document loading from docs/ folder
# - Updated main.py to support Telegram bot mode"
```

### Шаг 4: Отправьте код в новый репозиторий

```bash
# Отправьте код в новую ветку main
git push -u origin main

# Или если хотите использовать другую ветку:
# git checkout -b develop
# git push -u origin develop
```

## Проверка

После выполнения команд проверьте:

1. Перейдите на страницу вашего нового репозитория на GitHub
2. Убедитесь, что все файлы загружены
3. Проверьте, что `.env` и `logs.db` не попали в репозиторий (они в .gitignore)

## Старый репозиторий

Старый репозиторий `git@github.com:MrGAN12009/5-7.git` останется без изменений и будет содержать старую версию проекта.

## Дополнительные команды

### Если нужно переименовать ветку:
```bash
git branch -M main  # Переименовать текущую ветку в main
```

### Если нужно создать новую ветку для разработки:
```bash
git checkout -b develop
git push -u origin develop
```

### Если нужно добавить несколько remote (для работы с обоими репозиториями):
```bash
# Старый репозиторий как backup
git remote add old-origin git@github.com:MrGAN12009/5-7.git

# Новый репозиторий как основной
git remote add origin git@github.com:ВАШ_USERNAME/НОВЫЙ_РЕПОЗИТОРИЙ.git

# Теперь можно отправлять в оба:
# git push origin main      # в новый
# git push old-origin main  # в старый (если нужно)
```

