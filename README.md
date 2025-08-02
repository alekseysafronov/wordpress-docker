
```markdown
# WordPress в Docker + Git/GitHub

Проект представляет собой **WordPress**, развернутый в **Docker**, с интеграцией **Git/GitHub** для удобной разработки и контроля версий.

---

## 🚀 Быстрый старт

1. **Клонируйте репозиторий**:
   ```bash
   git clone https://github.com/ваш-username/wordpress-docker.git
   cd wordpress-docker
   ```

2. **Запустите Docker-контейнеры**:
   ```bash
   docker-compose up -d
   ```

3. **Откройте WordPress в браузере**:
   - Адрес: [http://localhost:8000](http://localhost:8000)
   - Данные для входа в админку создаются при первой установке.

---

## 📂 Структура проекта

```
wordpress-docker/
├── docker-compose.yml    # Конфигурация Docker
├── .gitignore           # Игнорируемые файлы
├── wp-content/          # Папка тем, плагинов (синхронизируется с Git)
│   ├── plugins/
│   ├── themes/
│   └── uploads/         # Медиафайлы (исключены из Git)
└── README.md            # Этот файл
```

---

## ⚙️ Настройка

### Переменные окружения
Создайте файл `.env` (на основе `.env.example`, если есть) и укажите:
```env
MYSQL_ROOT_PASSWORD=ваш_пароль
WORDPRESS_DB_PASSWORD=wordpress
```

### Доступ к базе данных
- **Хост БД**: `db` (в Docker-сети)
- **Пользователь**: `wordpress`
- **Пароль**: Указан в `.env` или `docker-compose.yml`.

---

## 🔄 Управление контейнерами

- **Запуск**:
  ```bash
  docker-compose up -d
  ```

- **Остановка** (без удаления данных):
  ```bash
  docker-compose down
  ```

- **Полная очистка** (включая данные БД):
  ```bash
  docker-compose down --volumes
  ```

---

## 💻 Работа с Git/GitHub

### Основные команды
```bash
# Добавить изменения
git add .

# Закоммитить
git commit -m "Описание изменений"

# Отправить в GitHub
git push origin main
```

### Что исключено из Git?
- Папка `wp-content/uploads/` (медиафайлы)
- Файлы `.env` (конфиденциальные данные)
- Временные файлы Docker

---

## 🛠 Дополнительные инструменты

### WP-CLI
Запуск команд WordPress через контейнер:
```bash
docker-compose run --rm wp-cli wp plugin list
```

### Xdebug
Для отладки PHP можно добавить конфигурацию в `docker-compose.yml`.

---

## 📜 Лицензия
MIT (или укажите свою).

---

## 📌 Контакты
- Автор: [Ваше имя](https://github.com/ваш-username)
- Проект на GitHub: [wordpress-docker](https://github.com/ваш-username/wordpress-docker)
```

---

### Как использовать?
1. Скопируйте этот текст в файл `README.md` в вашем проекте.
2. Замените `ваш-username` на ваш GitHub-аккаунт.
3. Добавьте свои данные (лицензия, контакты, описание).

Этот файл поможет другим разработчикам быстро разобраться в вашем проекте!