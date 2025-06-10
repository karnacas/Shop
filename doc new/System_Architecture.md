# Архитектура системы

## Слои приложения:
1. **Представление (UI)**: WPF-интерфейс, XAML.
2. **Бизнес-логика**: Обработка данных (CRUD, аналитика).
3. **Доступ к данным**: Entity Framework + SQL Server.

## Компоненты:
```mermaid
graph TD
    A[UI] --> B[Business Layer]
    B --> C[Data Access Layer]
    C --> D[(SQL Server)]
