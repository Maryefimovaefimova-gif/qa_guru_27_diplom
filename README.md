🎓 Дипломный проект: Автоматизация тестирования
Playwright + Python + Allure + GitHub Actions
🚀 Быстрый старт
1. Установка
# Клонирование репозитория
git clone <URL-адрес репозитория>
cd Playwright_python_inzhenerka

# Создание виртуального окружения
python -m venv venv

# Активация виртуального окружения
venv\Scripts\activate  # Windows
source venv/bin/activate  # Linux/Mac

# Установка зависимостей
pip install -r requirements.txt
playwright install chromium
2. Настройка окружения
# Создайте .env файл на основе шаблона
cp .env.example .env

# Отредактируйте .env файл, указав актуальные данные:
# - BASE_URL (URL тестируемого приложения)
# - EMAIL (логин тестового пользователя)
# - PASSWORD (пароль)
3. Запуск тестов
# Все тесты
pytest

# Только smoke-тесты
pytest -m smoke

# Только E2E-тесты
pytest -m e2e

# Конкретный тест
pytest tests/test_auth.py::test_successful_login

# Запуск на другом окружении (переопределение BASE_URL)
BASE_URL=https://stage.topklik.online/ pytest
4. Просмотр Allure отчета локально
# Генерация и открытие отчета
allure serve allure-results
