# Домашнее задание к занятию 10.2 «Кластеризация»


### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c Шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и вашу фамилию и имя
   - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
   - для корректного добавления скриншотов воспользуйтесь инструкцией ["Как вставить скриншот в шаблон с решением"](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
   - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.

Желаем успехов в выполнении домашнего задания!

---

### Задание 1

В чём различие между SMP- и MPP-системами?

Система MPP не разделяет ресурсы.
Система SMP использует общую память, транзакции обрабатываются несколькими процессорами , поэтому ее эффективность немного лучше, чем у MPP.

---

### Задание 2

В чём отличие сильно связанных и слабо связанных систем?

Основное различие между слабосвязанной и тесно связанной многопроцессорной системой заключается в том, что слабосвязанная система имеет распределенную память, тогда как тесно связанная система имеет общую память.

---

### Задание 3

Какие преимущества отличают кластерные системы от обычных серверов?

1. Надежность
2. Производителбность
3. Мастштабируемость
4. Соотношение цена/качество

---

### Задание 4

Приведите примеры типов современных кластерных систем.

1. HA
2. Кластеры с балансировкой нагрузки
3. Вычистительные кластеры

---

### Задание 5

Где используют сервис Kafka, rabitMQ?

Кафка станет отличным решением, если вам нужен фреймворк для хранения, чтения, повторного чтения и анализа потоковых данных. Ее сильная сторона – обработка и анализ данных в реальном времени. Инструмент идеально подходит для постоянного хранения сообщений или для регулярно проверяемых систем.

Разработчики используют RabbitMQ для обработки высокопроизводительных и надежных фоновых заданий, а также для интеграции и взаимодействия внутри приложений и между ними. Инструмент применяется для выполнения сложной маршрутизации к консьюмерам и интеграции нескольких приложений и служб с нетривиальной логикой маршрутизации.
RabbitMQ идеально подходит для веб-серверов, которым требуется быстрый запрос-ответ. Этот инструмент распределяет нагрузку между рабочими приложениями при высокой нагрузке (более 20 000 сообщений в секунду) и может обрабатывать фоновые задания или длительные задачи, такие как преобразование PDF, сканирование файлов или масштабирование изображений.

---

## Задания со звёздочкой*
Эти задания дополнительные. Их можно не выполнять. На зачёт это не повлияет. Вы можете их выполнить, если хотите глубже разобраться в материале.

---

### Задание 6*

Исследуйте построение кластера на основе rabbitMQ: https://github.com/ypereirareis/docker-rabbitmq-ha-cluster. 
Используя docker-compose, соберите инфраструктуру. Исследуйте её работы.

Ответьте на вопросы.

- На каких компонетах развёрнут кластер?
- Назначение компонентов кластера.
- 
PHP - consumer и producer
HAProxy - балансировщик, который принимает запросы от producer и передает в зависимости от нагруженности определенному consumer'у
RabbitMQ - Брокер сообщений
Docker - система где реализован кластер

- Какие тесты можно провести для анализа работы кластера?
Останавливал контейнеры.
![image](https://user-images.githubusercontent.com/106932460/217883132-ea9673c2-d77e-4ae8-aa0f-67ae79db665e.png)
![image](https://user-images.githubusercontent.com/106932460/217884795-44e249d4-7015-4f0e-8aab-86c73a6891d0.png)


![image](https://user-images.githubusercontent.com/106932460/217882431-d12597a1-7f3d-4121-a396-8a8a4090c181.png)
![image](https://user-images.githubusercontent.com/106932460/217883064-0e6574f3-1e7a-461c-8d00-90810d0c3a52.png)

*Приведите в пример скриншоты работающей системы и ответы на вопросы.*

![image](https://user-images.githubusercontent.com/106932460/217279898-26b19205-dd52-4158-bf44-22853e78346d.png)
![image](https://user-images.githubusercontent.com/106932460/217292133-06b24645-75c7-4e59-b045-07c0d43f3dc8.png)

Что-то получается

![image](https://user-images.githubusercontent.com/106932460/217880405-43d2767f-1951-4b24-81fc-1a0dbb060528.png)

С PHP не получилось, взял скрипты из интернета написанные на Python, получается они consumer и producer

![image](https://user-images.githubusercontent.com/106932460/217880719-66e85917-3c84-402f-abdf-108897626730.png)




