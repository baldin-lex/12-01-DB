# Домашнее задание к занятию 12.1. «Базы данных» - Балдин Алексей

### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.
#
### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

### <ins>Решение:</ins>

1. `- ФИО сотрудника - фамилия имя и отчество сотрудника предприятия. Тип данных: VARCHAR` 

2. `- Оклад  - заработная плата сотрудника. Тип данных: DECIMAL/NUMERIC`

3. `- Должность  - должность сотрудника, занимаемая в подразделении. Тип данных: VARCHAR`

4. `- Тип подразделения - отдел, в котором работает сотрудник предприятия. Тип данных: VARCHAR`

5. `- Дата найма - дата париема сотрудника на работу в предприятие. Тип данных: DATE`

6. `- Адрес филиала - территориальное месторасположение филиала предприятия. Тип данных: VARCHAR`

7. `- Проект на который назначен - название проекта, в развитии которого сотрудник принимает участие. Тип данных: VARCHAR`
#
Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).
#
### <ins>Решение:</ins>
```SQL
CREATE TABLE worker (
  worker_id primary_key,
  last_name VARCHAR(30),
  first_name VARCHAR(20),
  patronymic VARCHAR(30),
  date_of_em DATE,
  position_id NUMERIC,
  division_id NUMERIC,
  salary DECIMAL/NUMERIC,
  address_id NUMERIC,
  project_id NUMERIC
)

CREATE TABLE salary (
  salary_id primary_key,
  pay_off NUMERIC
)

CREATE TABLE position (
  position_id primary_key,
  division_id NUMERIC
)

CREATE TABLE division (
  division_id primary_key,
  departament VARCHAR(30),
  type VARCHAR(20)
)

CREATE TABLE date_of_em (
  date_of_em primary_key,
  date DATE
)

CREATE TABLE address (
  address_id primary_key,
  country VARCHAR(30),
  city VARCHAR(30),
  street VARCHAR(30),
  building NUMERIC
)

CREATE TABLE project (
  project_id primary_key,
  project_name VARCHAR(30)
)
```
## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
