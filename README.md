# Домашнее задание к занятию 12.1. «Базы данных» - Балдин

---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

#### *- ФИО сотрудника - фамилия имя и отчество сотрудника предприятия. Тип данных: VARCHAR* 

#### *- Оклад  - заработная плата сотрудника. Тип данных: DECIMAL/NUMERIC*

#### *- Должность  - должность сотрудника, занимаемая в подразделении. Тип данных: VARCHAR*

#### *- Тип подразделения - отдел, в котором работает сотрудник предприятия. Тип данных: VARCHAR*

#### *- Дата найма - дата париема сотрудника на работу в предприятие. Тип данных: DATE*

#### *- Адрес филиала - территориальное месторасположение филиала предприятия. Тип данных: VARCHAR*

#### *- Проект на который назначен - название проекта, в развитии которого сотрудник принимает участие. Тип данных: VARCHAR*

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

#### *Если я правильно понял, необходимо описать таблицы данной БД, используя синтаксис. Тогда:*

worker (

worker_id primary_key,

last_name VARCHAR(30),

first_name VARCHAR(20),

patronymic VARCHAR(30),

date_of_em DATE,

position_id NUMERIC,

division_id NUMERIC,

salary DECIMAL/NUMERIC,

address_id NUMERIC,
 
project_id NUMERIC,

)


salary  (

salary_id primary_key,

pay_off NUMERIC

)


position (

position_id primary_key,

division_id NUMERIC

)


division (

division_id primary_key,

departament VARCHAR(30),

type VARCHAR(20)

)


date_of_em (

date_of_em primary_key,

date DATE

)


address (

address_id primary_key,

country VARCHAR(30),

city VARCHAR(30),

street VARCHAR(30),

building NUMERIC

)


project (

project_id primary_key,

project_name VARCHAR(30)

)
