# Домашнее задание к занятию 1.  «Введение в виртуализацию» - Филатов А. В.

#### Это задание для самостоятельной отработки навыков и не предполагает обратной связи от преподавателя. Его выполнение не влияет на завершение модуля. Но мы рекомендуем его выполнить, чтобы закрепить полученные знания.  Все вопросы, возникающие в процессе выполнения заданий, пишите в учебный чат или в раздел "Вопросы по заданиям" в личном кабинете.

### Цели задания
1. Научиться запускать виртуальную машину в Yandex Cloud с минимальным расходом ресурсов.
2. Попрактиковаться в выборе платформы  и системы управления виртуализации для решения требуемых задач.

### Инструкция к выполению

1. Для выполнения задачи 1 ознакомьтесь с [инструкцией](https://github.com/netology-code/devops-materials/blob/master/cloudwork.MD) по экономии облачных ресурсов и затем выполните задачу 1 по шагам.
2. Своё решение к задачам 2,3,4 загрузите  в ваш ЛК.
   
## Задача 1

Ознакомьтесь с [инструкцией ](https://github.com/netology-code/devops-materials/blob/master/cloudwork.MD) по экономии облачных ресурсов.


1. Создайте через web-интерфейс Yandex Cloud - VPC и виртуальную машину из инструкции конфигурации "эконом-ВМ" с публичным ip-адресом. В пункте "Выбор образа/загрузочного диска" выберите вкладку "Cloud Marketplace" , щелкните "Посмотреть больше", найдите образ "Yandex Cloud Toolbox".
2. Убедитесь, что вы можете подключиться к консоли ВМ через ssh, используя публичный ip-адрес. Убедитесь, что на ВМ установлен Docker с помощью команды ```docker --version```(команду выполните от имени root пользователя) !
3. Узнайте в инструкции Яндекс, какие еще инструменты предустановлены в данном образе.
4. Оставьте ВМ работать, пока она не выключится самостоятельно! Опция "прерываемая" выключит ее не позже чем через 24 часа. 
5. Для наглядности подождите еще 1 сутки.
6. Перейдите по [ссылке ](https://console.cloud.yandex.ru/billing?section=accounts). Выберите свой платежный аккаунт. Перейдите на вкладку детализация (фильтр "По продуктам") и оцените график потребления финансов.
7. Удалите ВМ или пользуйтесь ею при выполнении последующих домашних заданий курса обучения.

---


## Задача 2

Выберите один из вариантов платформы в зависимости от задачи. Здесь нет однозначно верного ответа так как все зависит от конкретных условий: финансирование, компетенции специалистов, удобство использования, надежность, требования ИБ и законодательства, фазы луны.

Тип платформы:

- физические сервера;
- паравиртуализация;
- виртуализация уровня ОС;

Задачи:

- высоконагруженная база данных MySql, критичная к отказу;
- различные web-приложения;
- Windows-системы для использования бухгалтерским отделом;
- системы, выполняющие высокопроизводительные расчёты на GPU.

Объясните критерии выбора платформы в каждом случае.

## Задача 3

Выберите подходящую систему управления виртуализацией для предложенного сценария. Опишите ваш выбор.

Сценарии:

1. 100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований. Преимущественно Windows based-инфраструктура, требуется реализация программных балансировщиков нагрузки, репликации данных и автоматизированного механизма создания резервных копий.
2. Требуется наиболее производительное бесплатное open source-решение для виртуализации небольшой (20-30 серверов) инфраструктуры на базе Linux и Windows виртуальных машин.
3. Необходимо бесплатное, максимально совместимое и производительное решение для виртуализации Windows-инфраструктуры.
4. Необходимо рабочее окружение для тестирования программного продукта на нескольких дистрибутивах Linux.

## Задача 4

Опишите возможные проблемы и недостатки гетерогенной среды виртуализации (использования нескольких систем управления виртуализацией одновременно) и что необходимо сделать для минимизации этих рисков и проблем. Если бы у вас был выбор, создавали бы вы гетерогенную среду или нет?

### Правила приема

Домашнее задание выполните в файле readme.md в GitHub-репозитории. В личном кабинете отправьте на проверку ссылку на .md-файл в вашем репозитории.

## Решение 1
![create-vm.png](https://github.com/v1us1885/hw-05-virt-01-basics/blob/master/create-vm.png)
- **Yandex Cloud Toolbox:**
  - интерфейс командной строки Yandex Cloud;
  - Terraform — инструмент для управления облачной инфраструктурой от компании Hashicorp;
  - Packer — инструмент для сборки образов виртуальных машин от компании Hashicorp;
  - Pulumi — инструмент для управления облачной инфраструктурой с использованием традиционных языков программирования;
  - Helm — менеджер пакетов для Kubernetes;
  - kubectl — инструмент командной строки для управления кластерами Kubernetes;
  - gRPCurl — инструмент командной строки для взаимодействия с серверами gRPC;
  - jq — JSON-процессор командной строки;
  - yq — YAML-, JSON- и XML-процессор командной строки;
  - Docker — платформа для разработки контейнерных приложений;
  - Git — система контроля версий;
  - tree — утилита для просмотра дерева директорий;
  - tmux — терминальный мультиплексор.

## Решение 2

### Выбор платформы в зависимости от задач   
### 1. Высоконагруженная база данных MySQL, критичная к отказу
- **Оптимальный выбор:** Физические сервера
  - **Производительность:** Высокая, благодаря прямому доступу к аппаратным ресурсам.
  - **Надежность:** Меньше слоев абстракции снижает риск сбоев.
  - **Доступность:** Возможность настройки кластеров для обеспечения высокой доступности.

### 2. Различные web-приложения
- **Оптимальный выбор:** Виртуализация уровня ОС (контейнеры)
  - **Гибкость:** Быстрая развертка и масштабирование приложений.
  - **Эффективность использования ресурсов:** Минимизация издержек на аппаратные ресурсы.
  - **Управление:** Упрощение управления зависимостями и версиями приложений.

### 3. Windows-системы для использования бухгалтерским отделом
- **Оптимальный выбор:** Паравиртуализация
  - **Совместимость:** Эффективная поддержка операционных систем, требующих определённых драйверов.
  - **Безопасность и управление:** Обеспечение изоляции и управление доступом.
  - **Снижение затрат:** Уменьшение физического количества серверов и операционных расходов.

### 4. Системы, выполняющие высокопроизводительные расчёты на GPU
- **Оптимальный выбор:** Физические сервера
  - **Производительность:** Полный доступ к физическим GPU для максимальной производительности.
  - **Совместимость оборудования:** Точная настройка аппаратного обеспечения под задачи.
  - **Масштабируемость:** Легкость добавления дополнительных ресурсов.

## Решение 3
### Рекомендации по выбору системы управления виртуализацией
### 1. 100 виртуальных машин на базе Linux и Windows, Windows-based инфраструктура
**Рекомендация:** Microsoft Hyper-V

- **Почему:** Hyper-V интегрируется с Windows инфраструктурой, поддерживает Linux и Windows VM, и предлагает функции балансировки нагрузки, репликации данных и автоматизации создания резервных копий.
- **Преимущества:** Встроен в Windows Server, легко масштабируется и поддерживает множество гостевых ОС.
- **Дополнительно:** Можно использовать System Center для расширенного управления и автоматизации.

### 2. Производительное бесплатное open source-решение для небольшой инфраструктуры
**Рекомендация:** Proxmox VE

- **Почему:** Proxmox VE — это бесплатное и open source решение, поддерживающее KVM виртуализацию для Linux и Windows, с возможностями кластеризации, резервного копирования и восстановления.
- **Преимущества:** Встроенная поддержка репликации, балансировки нагрузки и резервного копирования через удобный веб-интерфейс.

### 3. Бесплатное и производительное решение для виртуализации Windows-инфраструктуры
**Рекомендация:** Oracle VM VirtualBox

- **Почему:** VirtualBox — бесплатное, мультиплатформенное решение с поддержкой Windows как хостовой и гостевой ОС.
- **Преимущества:** Легкая настройка и идеальная совместимость для разработки и тестирования в смешанных ОС-средах.

### 4. Рабочее окружение для тестирования на нескольких дистрибутивах Linux
**Рекомендация:** Docker

- **Почему:** Docker позволяет быстро настраивать и изолировать тестовые среды для различных Linux дистрибутивов, что идеально для программного тестирования.
- **Преимущества:** Быстрый запуск, упрощенное управление зависимостями и поддержка множества Linux дистрибутивов через официальные образы.

## Решение 4
### Возможные проблемы и недостатки гетерогенной среды виртуализации
### Проблемы

1. **Сложность управления**
   - Управление разнообразными системами виртуализации может усложняться из-за различий в их интерфейсах, API и возможностях, что увеличивает время на обучение и управление.

2. **Высокие затраты**
   - Поддержание нескольких платформ может увеличить затраты на лицензирование, техническое обслуживание и обучение персонала.

3. **Проблемы совместимости**
   - Взаимодействие между различными системами виртуализации может приводить к проблемам с совместимостью, особенно при миграции виртуальных машин между различными платформами.

4. **Безопасность и уязвимости**
   - Управление безопасностью в гетерогенной среде может быть более сложным, так как требуется поддерживать разные стандарты безопасности и обновления для каждой системы.

5. **Резервное копирование и восстановление**
   - Интеграция систем резервного копирования может быть сложной, что увеличивает риск потери данных при отсутствии унифицированной стратегии бэкапа.

### Минимизация рисков и проблем

1. **Стандартизация процессов**
   - Разработка стандартных операционных процедур для всех используемых платформ помогает уменьшить сложность управления.

2. **Обучение и сертификация**
   - Инвестиции в обучение технического персонала улучшают понимание и эффективность управления различными платформами.

3. **Использование инструментов управления мультиплатформенностью**
   - Применение инструментов, поддерживающих управление несколькими системами виртуализации, сокращает затраты и сложность.

4. **Унифицированные политики безопасности**
   - Применение единых политик безопасности на всей инфраструктуре обеспечивает последовательность и уменьшает риски.

5. **Централизованное резервное копирование**
   - Использование решений, поддерживающих бэкап с нескольких платформ, помогает обеспечивать целостность данных.

### Личное мнение о создании гетерогенной среды

Если бы у меня был выбор, я бы предпочел избегать создания гетерогенной среды виртуализации там, где это возможно, стремясь упростить управление, снизить затраты и повысить безопасность и надежность. Сокращение сложности часто более важно, чем потенциальные преимущества использования множества платформ, особенно в средах с ограниченными ресурсами.
