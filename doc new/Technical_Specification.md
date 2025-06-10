# Техническая спецификация

## Общее описание
ToolsWorld — это WPF-приложение, реализующее бизнес-логику для управления магазином инструментов.  
Платформа: .NET Framework 4.7+  
БД: MS SQL Server (2016+)  

## Ключевые компоненты
| Компонент | Описание |
|----------|----------|
| **UI**   | WPF-приложение с MVVM-архитектурой, XAML-интерфейсами |
| **Бизнес-логика** | Обработка продаж, аналитика, фильтрация данных |
| **БД** | Entity Framework для работы с таблицами: `Products`, `Sales`, `Employees`, `Suppliers` и т.д. |

## Технические требования
- .NET Framework 4.7+
- MS SQL Server (2016+)
- WPF (C#)

## Диаграммы:
**Классы (Mermaid)**  
```mermaid
classDiagram
    class Product {
        +int Id
        +string Name
        +decimal Price
        +int StockQuantity
    }
    
    class Sale {
        +int Id
        +DateTime Date
        +decimal TotalAmount
        +Employee EmployeeId
    }

    class Employee {
        +int Id
        +string FullName
        +string Position
        +Department DepartmentId
    }

    Product --> Sale : "1..N"
    Employee --> Sale : "1..N"
    Employee --> Department : "1"
