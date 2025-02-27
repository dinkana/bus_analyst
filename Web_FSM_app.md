# Проект создания web-приложения для управления торговым оборудованием (FSM)

Цель проекта — создание нового web-приложения FSM для учета и управления торговым оборудованием, которое позволит систематизировать данные об оборудовании, оптимизировать работу техников и улучшить управление процессами технического обслуживания.

## Оглавление
1. [Анализ существующих данных о торговом оборудовании](#анализ-существующих-данных-о-торговом-оборудовании)
2. [Основные функции учетного блока торгового оборудования](#основные-функции-учетного-блока-торгового-оборудования)
3. [Классификация торгового оборудования](#классификация-торгового-оборудования)
4. [Требования к web FSM-приложению](#требования-к-web-fsm-приложению)
    - [Учет оборудования](#учет-оборудования)
    - [Управление пользователями и ролями](#управление-пользователями-и-ролями)
    - [Отчетность и мониторинг](#отчетность-и-мониторинг)
    - [Интеграция с другими системами](#интеграция-с-другими-системами)
    - [Управление данными](#управление-данными)
5. [Нефункциональные требования](#нефункциональные-требования)
6. [Бизнес-требования](#бизнес-требования)
7. [Технические требования](#технические-требования)
8. [Системы, взаимодействующие с приложением](#системы-взаимодействующие-с-приложением)
9. [Поток данных и архитектура](#поток-данных-и-архитектура)
10. [Глоссарий](#глоссарий)

---

## Анализ существующих данных о торговом оборудовании
На текущий момент данные о торговом оборудовании собираются и хранятся в реляционной базе данных SQL. Эти данные включают:
- Основные сведения: название, модель, серийный номер, номер инвентарной карточки.
- Техническая информация: дата приобретения, стоимость, состояние, технические характеристики.
- Локационные данные: текущее местоположение, ответственный сотрудник.
- История обслуживания: информация о проведённых ремонтах и техническом обслуживании.

Использование данных: база данных о торговом оборудовании используется для повышения эффективности техобслуживания, сокращения времени простоя оборудования, мониторинга состояния и планирования ремонтов.

## Основные функции учетного блока торгового оборудования
- Основные характеристики оборудования — название, производитель, серийный номер и т.д.
- Состояние оборудования — текущий статус (включено/выключено, работает/не работает).
- Производительность — показатели, такие как скорость, память.
- Журнал неисправностей — информация о проблемах и сбоях.
- Учет технического обслуживания и периферийных устройств.

## Классификация торгового оборудования
Торговое оборудование классифицируется на основе:
- По назначению
- По функционалу
- По товарному профилю
- По конструкции
- По месту расположения

## Требования к web FSM-приложению

### Учет оборудования
- Добавление нового оборудования с указанием его характеристик
- Редактирование и удаление записей об оборудовании
- Учет данных о производительности оборудования
- Журнал учета неисправностей и сбоев в работе оборудования

### Управление пользователями и ролями
- Создание и управление пользователями с различными ролями

### Отчетность и мониторинг
- Генерация отчетов о состоянии оборудования и финансовых операциях

### Интеграция с другими системами
- Поддержка импорта и экспорта данных в форматах CSV и Excel
- Интеграция с системами управления складом, BI-платформой

### Управление данными
- Поддержка ETL для управления данными из различных источников

## Нефункциональные требования
- **Производительность**: высокая скорость доступа к данным, поддержка масштабируемости
- **Надежность и доступность**: работоспособность не менее 99% времени
- **Интерфейс и удобство использования**: простой и интуитивно понятный интерфейс
- **Безопасность**: защита данных от несанкционированного доступа
- **Поддержка и совместимость**: поддержка Windows 7+ и баз данных PostgreSQL, MS SQL

## Бизнес-требования
- Автоматизация учета оборудования
- Простота и доступность данных
- Интеграция для комплексного анализа
- Экономическая эффективность

## Технические требования
- **Архитектура и стек технологий**: Node.js, PostgreSQL/Microsoft SQL Server
- **Интеграция**: поддержка REST API, файлов CSV/Excel
- **База данных и хранение данных**: поддержка ETL
- **Мониторинг и поддержка**: сбор данных для мониторинга производительности

## Системы, взаимодействующие с приложением
- Системы управления складом
- Системы учета продаж
- BI-платформа
- Система управления ремонтом

## Поток данных и архитектура
- Сбор данных из различных источников
- Использование ETL-процессов для обработки данных
- Агрегирование данных в корпоративном хранилище
- Формирование витрин данных и их визуализация через BI-платформу

## Глоссарий
- **FSM (Field Service Management)** — система управления выездными сервисными работами.
- **FMCG (Fast Moving Consumer Goods)** — товары повседневного спроса.
- **API (Application Programming Interface)** — интерфейс программирования приложений.
- **JSON (JavaScript Object Notation)** — текстовый формат обмена данными.
- **SQL (Structured Query Language)** — декларативный язык программирования для управления данными.
- **PostgreSQL** — объектно-реляционная система управления базами данных.
- **Microsoft SQL Server** — система управления реляционными базами данных от Microsoft.
- **XML (eXtensible Markup Language)** — расширяемый язык разметки.
- **ETL (Extract, Transform, Load)** — процесс управления данными, который включает извлечение, трансформацию и загрузку данных.
- **BI-платформа (Business Intelligence)** — платформа для аналитики и визуализации данных.
