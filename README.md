# Домашнее задание к занятию "`Базы данных, их типы`" - `Дунаев Дмитрий`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

*Решение* Хороший вариант - использвоать реляционную базу данных SQL, например MySQL, или PostgreSQL. Такие базы имеют
раз четкую структуру данных, также имеется механизм обеспечения целостности. Использование SQL позволяет 
формировать аналитические отчеты и  на их основе формировать прогнозы. 

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

*Решение* В этом случае, лучше использовать не реляционные базы данных. Для них характерно хранение больших объёмов
неструктурированной информации, а также высокая гибкость, например, добавление новых типов данных.
NoSQL базы лучше поддаются масштабированию, а также обеспечивают более высокую скорость обработки данных, чем SQL. 
Можно использовать, например MongoDB или Apache Cassandra.

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

*Решение* Для создания БД по четким корпоративным требованиям с простой и понятной структурой подойдет реляционная БД,
например та же MySQL или PostgreSQL.

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

*Решение* При решении задач по логистике могут хорошо подойти базы данных на основе графов, например такие, 
как Neo4j, DGraph, DataStax. Графовые БД хорошо подходят для решения задач на основе связей, так как
используют набор методов, направленных на изучение связей между сущностями.

*Приведите ответ в свободной форме.*

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

*Приведите ответ в свободной форме.*

---

### Решение 2.

Транзакция для пополнения баланса телефона может быть проведена по следующим шагам:

1. Проверка доступности счета абонента;
2. Блокировка счета пользователя на момент проведения операции;
3. Выполнение операции пополнения баланса;
4. Фиксирование изменения в базе данных для обеспечения целостности транзакции;
5. Разблокировка счета абонента после успешного завершения транзакции;
6. Отправка подтверждения об успешном завершении транзакции.

При использовании автоплатежа в начале алгоритма добавляется шаг по проверке достаточного количества средств на счете для оплаты.

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

*Приведите ответ в свободной форме.*

---

### Решение 3.

1. Жестко структурированный формат храниения данных;
2. мощный язык запросов, позволяет выполнять сложные запросы;
3. SQL язык хорошо стандартизирован и имеет множество инструментов для работы с ним;
4. транзакционная безопасность - ACID-транзакции, обеспечивающие надежность и целостность;
5. имеют встроенные механизмы для обеспечения безопасности, аутентификации;

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

*Приведите ответ в свободной форме.*

---

### Решение 4.

Для большого количества вычислений можно рассмотреть инструменты и связки с СУБД, созданные для распределенных вычислений,
такие как hadoop (HDFS), Apache Spark, Cassandra, MongoDB.