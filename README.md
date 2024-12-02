# Информационная система страхования

Данный проект представляет собой клиент-серверную информационную систему для управления страховыми полисами, оплатами и оценкой ущерба.

---

## GitGraph
Первым на рассмотрении будет GitGraph. С его помощью можно отобразить базовый процесс работы с разными ветками при разработке системы. Такой граф является более наглядным в сравнение с ручным разбором истории коммитов.
Пример графа для системы бронияровая представлен выше

```mermaid
gitGraph
    commit id: "Создание репозитория системы страхования"
    branch develop
    checkout develop
    commit id: "Реализация модуля управления полисами"
    branch feature/payment
    checkout feature/payment
    commit id: "Добавление модуля обработки платежей"
    commit id: "Интеграция с платежным шлюзом"
    checkout develop
    merge feature/payment tag: "Платежи завершены"
    branch feature/assessment
    checkout feature/assessment
    commit id: "Реализация модуля оценки ущерба"
    commit id: "Интеграция со службой оценки"
    checkout develop
    merge feature/assessment tag: "Оценка ущерба завершена"
    branch feature/notifications
    checkout feature/notifications
    commit id: "Добавление системы уведомлений"
    checkout develop
    merge feature/notifications tag: "Уведомления завершены"
    checkout main
    merge develop tag: "Релиз v1.0"
    commit id: "Релиз v1.0: функционал полисов, платежей и уведомлений"
```

---
## Квадрант-граф
Следующим на рассмотрении идет Квадрант-граф. Он позволяет классифицировать задачи по разным критериям, например, высокая/низкая сложность и высокий/низкий приоритет. Данный подход удобен, когда в момент разработки возникает несколько задач и команда не сразу понимает за что браться. Данный граф помогает оценить каждую задачу и сфокусировать внимание на самых важных. Пример такого графа представлен выше.

```mermaid
quadrantChart
    title Приоритеты задач системы страхования
    x-axis "Низкий приоритет" --> "Высокий приоритет"
    y-axis "Низкая сложность" --> "Высокая сложность"
    quadrant-1 "Неотложные задачи"
    quadrant-2 "Перспективные задачи"
    quadrant-3 "Малозначимые задачи"
    quadrant-4 "Риски"
    "Создание полисов": [0.9, 0.3]
    "Обработка платежей": [0.8, 0.5]
    "Оценка ущерба": [0.7, 0.7]
    "Система уведомлений": [0.5, 0.4]
    "Генерация отчетов": [0.4, 0.6]
    "Аналитика данных": [0.3, 0.8]
    "Управление клиентами": [0.8, 0.2]
    "Интеграция с внешними системами": [0.6, 0.5]
    "Составление графиков выплат": [0.3, 0.6]
    "Контроль истории полисов": [0.7, 0.4]
    "Оптимизация производительности": [0.4, 0.9]
    "Поддержка новых типов полисов": [0.2, 0.7]
    "Разработка API для партнеров": [0.6, 0.6]
    "Поддержка мобильных приложений": [0.7, 0.5]
```

---
## User Journey Diagram
Третьим по очереди, но не по значению можно выделить User Journey Diagram. Данная диаграмма позволяет оценить пользовательский опыт при взаимодействии с каждым элементом нашей системы и выявить слабые места. 

```mermaid
journey
    title Путешествие клиента в системе страхования
    section Регистрация полиса
      Выбор типа полиса: 5: Клиент
      Предоставление данных: 4: Клиент
      Создание полиса: 3: Система
    section Оплата
      Выбор способа оплаты: 4: Клиент
      Проведение платежа: 3: Платежный шлюз
      Подтверждение оплаты: 5: Система
    section Оценка ущерба
      Подача заявки: 4: Клиент
      Оценка ущерба: 3: Служба оценки
      Уведомление о результатах: 5: Система
```

---
## Mind Map
И наконец последняя диаграмма – Mind Map. Данные диаграммы можно использовать для визуализации ключевых аспектов клиент-серверной системы, которые можно сгруппировать по ролям. 

```mermaid
mindmap
  root((Система страхования))
    Клиенты
      Создание полиса
      Оплата
      Запрос оценки ущерба
      Уведомления
    Администраторы
      Управление полисами
      Генерация отчетов
      Анализ данных
    Система
      Проверка данных
      Интеграция с платежными шлюзами
      Оценка ущерба
      Отправка уведомлений
```
