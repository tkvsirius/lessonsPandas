# PY_Pandas_10

Учебный мини-проект с ноутбуком `module_10.ipynb`.

## 1. Структура
```
PY_Pandas_10/
  module_10.ipynb
  requirements.txt
  data/
```
Папка `data/` предназначена для входных данных (необязательные файлы и большие сырые данные можно исключать через .gitignore — см. шаблон).

## 2. Быстрый старт (Windows / macOS / Linux)
Рекомендуется из корня проекта.

### 2.1 Создать виртуальное окружение
Windows (PowerShell):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```
macOS / Linux (bash/zsh):
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2.2 Обновить pip и установить зависимости
```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```
Если команда `pip` не доступна, используйте:
```bash
python -m pip install -r requirements.txt
```

### 2.3 Запуск Jupyter (вариант через VS Code)
1. Открой VS Code в папке проекта.
2. Активируй venv (см. выше).
3. Открой `module_10.ipynb` — выбери интерпретатор из `.venv`.

CLI запуск (если нужен классический ноутбук):
```bash
python -m pip install jupyter
jupyter notebook
```

## 3. Кроссплатформенность
Файл `requirements.txt` фиксирует версию `pandas==2.3.2`. На macOS имя команды обычно `python3`. Если есть различия версий Python (например, 3.13 vs 3.12), рекомендовано использовать одинаковую минорную версию для воспроизводимости.

Проверка версии:
```bash
python -V   # или python3 -V
```

## 4. Работа с Git и GitHub
### 4.1 Инициализация локального репозитория
```bash
git init
git add .
git commit -m "Initial commit: notebook and setup"
```

### 4.2 Создание удалённого репозитория
1. Зайди на https://github.com/new
2. Введи имя репо `PY_Pandas_10` (можно другое)
3. НЕ добавляй README, .gitignore и LICENSE (они уже есть локально)
4. Создай репозиторий

### 4.3 Привязка и отправка (HTTPS)
```bash
git remote add origin https://github.com/<YOUR_USER>/<REPO>.git
git branch -M main
git push -u origin main
```

### 4.4 Привязка и отправка (SSH)
(Требует настроенный SSH-ключ)
```bash
git remote add origin git@github.com:<YOUR_USER>/<REPO>.git
git branch -M main
git push -u origin main
```

Проверка remotes:
```bash
git remote -v
```

## 5. Обновление зависимостей
После установки новых пакетов:
```bash
pip install <package>
pip freeze > requirements.lock
```
Оставляй `requirements.txt` минимальным (только необходимые библиотеки) — сейчас там только pandas. Дополнительно можешь хранить полный снепшот в `requirements.lock`.

## 6. Альтернатива: pyproject.toml
Для более сложных проектов можно перейти на Poetry или Hatch:
```bash
pip install poetry
poetry init
poetry add pandas
```
Это создаст управляемое окружение и файл зависимостей с блокировкой.

## 7. Данные
Крупные / бинарные файлы (CSV > ~50MB) можно вынести из Git или использовать Git LFS:
```bash
git lfs install
git lfs track "data/*.csv"
```
Не забывай коммитить добавленный `.gitattributes`.

## 8. Типичные проблемы
| Проблема | Решение |
|----------|---------|
| pip не находится | Используй `python -m pip`, проверь PATH |
| Jupyter не видит venv | Переустанови ipykernel: `python -m pip install ipykernel` |
| Конфликт версий pandas | Удалить venv и пересоздать |

## 9. Лицензия
Добавь файл `LICENSE` при необходимости (MIT / Apache-2.0 и т.д.).

---
Готово. Можно пушить. Если нужно — помогу автоматизировать создание тега или GitHub Actions.
