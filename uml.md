# BPMN Диаграмма для менеджера в Web FSM-приложении

```mermaid
flowchart TD
    %% Основной процесс для менеджера по управлению торговым оборудованием
    
    %% Начало процесса
    Start([Начало]) --> Process1

    %% Блок добавления оборудования
    subgraph AddEquipment [Добавление нового оборудования]
        Process1([Заполнение данных о новом оборудовании])
        Decision1{Данные корректны?}
        Process1 --> Decision1
        Decision1 -- Да --> SaveData([Сохранение данных в БД])
        Decision1 -- Нет --> Correction([Корректировка данных])
        Correction --> Process1
        SaveData --> EndAdd
    end
    EndAdd([Окончание добавления оборудования]) --> Process2

    %% Блок редактирования информации об оборудовании
    subgraph EditEquipment [Редактирование информации об оборудовании]
        Process2([Поиск оборудования для редактирования])
        EditData([Редактирование данных оборудования])
        Decision2{Данные корректны?}
        Process2 --> EditData --> Decision2
        Decision2 -- Да --> SaveEdit([Сохранение изменений])
        Decision2 -- Нет --> CorrectionEdit([Корректировка данных])
        CorrectionEdit --> EditData
        SaveEdit --> EndEdit
    end
    EndEdit([Окончание редактирования]) --> Process3

    %% Блок работы с отчетами
    subgraph Reports [Работа с отчетами]
        Process3([Выбор параметров отчета])
        GenerateReport([Генерация отчета])
        ViewReport([Просмотр отчета])
        Process3 --> GenerateReport --> ViewReport
    end
    ViewReport --> EndReports
    EndReports([Окончание работы с отчетами])

    %% Конец процесса
    EndReports --> End([Конец])
